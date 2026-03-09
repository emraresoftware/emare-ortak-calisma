# 🖥️ Emare Sunucu & Altyapı Rehberi

> **Son Güncelleme:** 7 Mart 2026  
> **Hazırlayan:** emarecloud dervişi  
> **Kapsam:** Tüm dervişlerin ihtiyaç duyduğu sunucu bilgileri, deploy prosedürleri, servis adresleri  
> **⚠️ Bu dosyadaki bilgiler günceldir — değişiklik yaparsan buraya da yansıt!**

---

## 📋 İçindekiler

1. [Sunucu Envanteri](#1-sunucu-envanteri)
2. [SSH Erişimi](#2-ssh-erişimi)
3. [Servis Adresleri & URL Haritası](#3-servis-adresleri--url-haritası)
4. [Nginx Yapılandırması](#4-nginx-yapılandırması)
5. [Veritabanları](#5-veritabanları)
6. [Deploy Prosedürleri](#6-deploy-prosedürleri)
7. [Servis Yönetimi](#7-servis-yönetimi)
8. [Port Kayıt Defteri](#8-port-kayıt-defteri)
9. [SSL / TLS](#9-ssl--tls)
10. [GitHub & Token Durumu](#10-github--token-durumu)
11. [Güvenlik Notları](#11-güvenlik-notları)
12. [Bilinen Sorunlar & Çözümler](#12-bilinen-sorunlar--çözümler)

---

## 1. Sunucu Envanteri

| Kod | IP Adresi | SSH Port | İşletim Sistemi | Rol |
|-----|-----------|----------|-----------------|-----|
| **DC-1** | `185.189.54.104` | `22` | AlmaLinux 9.6 | ecomaiq.com, API, DApp |
| **DC-2** | `77.92.152.3` | `2222` | AlmaLinux | emarecloud.tr, POS, Finans, Asistan |
| **DC-3** | *(henüz bilinmiyor)* | `22` | — | emarecloud çalışıyor (detay bekleniyor) |

### SSH Anahtarı
```
~/.ssh/id_ed25519
```

---

## 2. SSH Erişimi

```bash
# DC-1
ssh -i ~/.ssh/id_ed25519 root@185.189.54.104

# DC-2
ssh -i ~/.ssh/id_ed25519 -p 2222 root@77.92.152.3
```

> **Not:** StrictHostKeyChecking kapatmak için `-o StrictHostKeyChecking=no` ekle (otomasyon için)

---

## 3. Servis Adresleri & URL Haritası

### DC-1 (185.189.54.104)

| Servis | URL | Port | Teknoloji | Yol |
|--------|-----|------|-----------|-----|
| Soru-Cevap / ecomaiq | `https://ecomaiq.com` | 3639 | Node (PM2) | `/var/www/ecomaiq/` |
| Emare DApp | — | 3002 | Node (PM2: emare-dapp) | — |
| Emare API | — | 8000 | Python uvicorn | `/opt/emareapi/` |

### DC-2 (77.92.152.3)

| Servis | URL | Port | Teknoloji | Yol |
|--------|-----|------|-----------|-----|
| EmareCloud Panel | `https://emarecloud.tr` | 5555 | Python Gunicorn (Flask) | `/opt/emarecloud/` |
| Emare Asistan | `https://asistan.emarecloud.tr` | 8201 | Python uvicorn | `/var/www/emareasistan/` |
| Emare Finans | `https://finans.emarecloud.tr` | — | PHP-FPM Laravel | `/var/www/emarefinance/` |
| Emare POS | `https://pos.emarecloud.tr` | — | PHP-FPM Laravel | `/var/www/emarepos/pos-system/` |

---

## 4. Nginx Yapılandırması

### DC-1 — nginx config konumu
```
/etc/nginx/conf.d/ecomaiq.conf
```

**Kritik güvenlik bloğu** (ecomaiq.com — `.git` ifşa saldırısına karşı):
```nginx
location ~ /\.git {
    deny all;
    return 404;
}
```

### DC-2 — nginx config konumları
```
/etc/nginx/conf.d/emarecloud.tr.conf
/etc/nginx/conf.d/asistan.emarecloud.tr.conf
/etc/nginx/conf.d/finans.emarecloud.tr.conf
/etc/nginx/conf.d/pos.emarecloud.tr.conf
```

### nginx komutları
```bash
nginx -t                    # config test
systemctl reload nginx      # graceful reload
systemctl restart nginx     # full restart
```

---

## 5. Veritabanları

### DC-2 — MariaDB 10.5.29

| DB Adı | Kullanıcı | Şifre | Kullanan Servis |
|--------|-----------|-------|-----------------|
| `emarefinance` | `root` (local) | — | Emare Finans (Laravel) |
| `emarepos` | `emarepos` | `EmarePos2026!` | Emare POS (Laravel) |

```bash
# DC-2'de MariaDB servis durumu
systemctl status mariadb

# MySQL bağlantısı
mysql -u emarepos -pEmarePos2026! emarepos
mysql -u root emarefinance
```

> **Not:** MariaDB, 7 Mart 2026'da `systemctl enable` ile boot'ta otomatik başlayacak şekilde ayarlandı.

### DC-2 — SQLite (emarefinance)
```
/var/www/emarefinance/database/database.sqlite
```
> ⚠️ SELinux `httpd_sys_rw_content_t` context'i gerekli, yoksa readonly hatası alırsın.

### EmareCloud Panel (DC-2)
- Flask SQLAlchemy, SQLite tabanlı
- Yol: `/opt/emarecloud/instance/`
- Migration: `venv/bin/alembic upgrade head`

---

## 6. Deploy Prosedürleri

### Python Projeleri (Flask/FastAPI — DC-1, DC-2)

```bash
# 1. Kodu çek
cd /opt/emarecloud          # veya /var/www/emareasistan
git pull origin main

# 2. Bağımlılıkları güncelle
venv/bin/pip install -r requirements.txt -q

# 3. Migration
venv/bin/alembic upgrade head

# 4. Servis yeniden başlat
systemctl restart emarecloud   # veya emareasistan
```

### PHP / Laravel Projeleri (DC-2)

```bash
cd /var/www/emarefinance    # veya /var/www/emarepos/pos-system

# 1. Kodu çek (git erişimi varsa)
git pull origin main

# 2. Composer
composer install --no-dev --optimize-autoloader --no-interaction -q

# 3. Migration
php artisan migrate --force

# 4. Cache temizle & yenile
php artisan config:clear
php artisan config:cache
php artisan route:cache
php artisan view:cache

# 5. İzinler
chown -R nginx:nginx storage/ bootstrap/cache/

# 6. Nginx reload
systemctl reload nginx
```

### GitHub Push Erişimi Yoksa — rsync ile Deploy

> Mevcut token (`emrgkd`) `emraresoftware` org'una write yetkisi yok.  
> Bu durumda lokal'den sunucuya rsync kullan:

```bash
rsync -avz --progress \
  -e "ssh -i ~/.ssh/id_ed25519 -p 2222" \
  /lokal/proje/dizini/ \
  root@77.92.152.3:/var/www/hedef/dizin/
```

### İlk Kurulum — storage:link (Laravel)
```bash
# Görsel/dosya yüklemeleri için zorunlu
php artisan storage:link
```

---

## 7. Servis Yönetimi

### DC-1 Servisleri

```bash
# PM2 (Node.js)
pm2 list
pm2 restart ecomaiq-server
pm2 restart emare-dapp
pm2 logs ecomaiq-server --lines 50

# uvicorn (emareapi)
systemctl status emareapi
systemctl restart emareapi
```

### DC-2 Servisleri

```bash
# EmareCloud Panel (Gunicorn/Flask)
systemctl status emarecloud
systemctl restart emarecloud
journalctl -u emarecloud -n 50

# Emare Asistan (uvicorn)
systemctl status emareasistan
systemctl restart emareasistan
journalctl -u emareasistan -n 50

# PHP-FPM (Finans + POS için)
systemctl status php-fpm
systemctl restart php-fpm

# MariaDB
systemctl status mariadb
systemctl restart mariadb

# Nginx
systemctl status nginx
systemctl reload nginx
```

### systemd servis dosyası konumları (DC-2)
```
/etc/systemd/system/emarecloud.service
/etc/systemd/system/emareasistan.service
```

---

## 8. Port Kayıt Defteri

> Tüm portlar EmareCloud paneli üzerinden tahsis edilir: `https://emarecloud.tr/api/ports`  
> **Manuel port atama yasaktır.** `ceyiz_hazirla.py` ile yeni proje kur.

### Kritik/Rezerve Portlar

| Port | Servis | Sunucu |
|------|--------|--------|
| 5555 | EmareCloud Panel (Gunicorn) | DC-2 |
| 8000 | Emare API (uvicorn) | DC-1 |
| 3002 | Emare DApp (PM2) | DC-1 |
| 3639 | ecomaiq-server (PM2) | DC-1 |
| 8201 | Emare Asistan (uvicorn) | DC-2 |
| 8100 | Emare Finans (PHP-FPM) | DC-2 |
| 8116 | Emare POS (PHP-FPM) | DC-2 |
| 5432 | PostgreSQL | rezerve |
| 6379 | Redis | rezerve |
| 3306 | MariaDB | DC-2 |

---

## 9. SSL / TLS

### DC-1 — ecomaiq.com
- Sertifika: Let's Encrypt E8
- TLS: 1.3
- Durum: ✅ geçerli
- Yenileme: `certbot renew`

### DC-2 — emarecloud.tr ve alt domainler
- Sertifika: LE ECDSA
- Son kullanma: Haziran 2026
- Kapsam: `emarecloud.tr`, `*.emarecloud.tr`

```bash
# Sertifika durumu (DC-1 veya DC-2)
certbot certificates

# Manuel yenileme
certbot renew --dry-run    # test
certbot renew              # gerçek yenileme
```

### Cloudflare Proxy
- `emarecloud.tr` zone ID: `a72e4fe4787b786fb91d41a3491949eb`
- `ecomaiq.com` zone ID: `3fe8ad6c8f551840f7b3bcdff4b72fd4`
- SSL modu: **Full** (her iki zone için)

---

## 10. GitHub & Token Durumu

### Aktif Token
```
[GÜVENLİK: Token kaldırıldı — GitHub Secrets veya .github_token dosyasından okunmalı]
```
- Sahibi: `emrgkd` (kişisel hesap)
- `emraresoftware` org'una: **READ** yetkisi var, **WRITE** yetkisi yok
- Token konumu: sunuculardaki `.git/config` remote URL içinde

### Repo — Sunucu Eşleştirmesi

| GitHub Repo | Sunucu | Yol | Not |
|-------------|--------|-----|-----|
| `emraresoftware/soru-cevap` | DC-1 | `/var/www/ecomaiq/` | HTTPS+token |
| `emraresoftware/emareasistan` | DC-2 | `/var/www/emareasistan/` | HTTPS+token |
| `emraresoftware/emarepos` | DC-2 | `/var/www/emarepos/` | HTTPS+token |

### Deploy Key (DC-1)
- Anahtar: `/root/.ssh/ecomaiq_deploy`
- Public: `ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOTHGXLRsgsKRxmRB5HhzOixR9hKl73ubXE8no1IjDHb dc1-ecomaiq-deploy`
- Durum: ⏳ `emraresoftware/soru-cevap` reposuna henüz eklenmedi

### ⚠️ Push Sorunu
`emraresoftware` org'una push yapılamıyor — token write yetkisi yok.  
**Workaround:** rsync ile lokal → sunucu dosya kopyalama (bkz. Bölüm 6)  
**Kalıcı Çözüm:** `emraresoftware` org'una write yetkili yeni token gerekiyor.

---

## 11. Güvenlik Notları

### .git Dizini Koruması (DC-1 — ecomaiq.com)
7 Mart 2026'da `45.148.10.238` IP'li saldırgan `.git/config` dosyasına erişerek GitHub token çaldı.  
Çözüm nginx'e eklendi:
```nginx
location ~ /\.git {
    deny all;
    return 404;
}
```
> **Diğer sunucularda da bu bloğun varlığını kontrol et!**

### SELinux (AlmaLinux)

DC-2'de SELinux **Enforcing** modda çalışıyor.  
Laravel projeleri için gerekli context ayarları:

```bash
# storage ve bootstrap/cache için yazma izni
semanage fcontext -a -t httpd_sys_rw_content_t "/var/www/PROJE/storage(/.*)?"
semanage fcontext -a -t httpd_sys_rw_content_t "/var/www/PROJE/bootstrap/cache(/.*)?"
restorecon -Rv /var/www/PROJE/storage /var/www/PROJE/bootstrap/cache

# SQLite DB için
semanage fcontext -a -t httpd_sys_rw_content_t "/var/www/PROJE/database(/.*)?"
restorecon -Rv /var/www/PROJE/database
```

---

## 12. Bilinen Sorunlar & Çözümler

### SQLite readonly hatası (Laravel)
**Sebep:** SELinux → `httpd_sys_content_t` (yazma yok)  
**Çözüm:**
```bash
chown -R nginx:nginx /var/www/PROJE/database
chmod 664 /var/www/PROJE/database/database.sqlite
chmod 775 /var/www/PROJE/database
semanage fcontext -a -t httpd_sys_rw_content_t "/var/www/PROJE/database(/.*)?"
restorecon -Rv /var/www/PROJE/database
```

### Session database hatası (Laravel)
**Sebep:** `SESSION_DRIVER=database` + SQLite readonly  
**Çözüm:** `.env`'de `SESSION_DRIVER=file` yap

### Nginx 521 (ecomaiq.com)
**Sebep:** Cloudflare edge node routing farklılığı  
**Not:** Origin sağlam, kalıcı sorun değil — CF tarafından geçici

### MariaDB bağlanamıyor
**Sebep:** Servis başlatılmamış  
**Çözüm:**
```bash
systemctl start mariadb
systemctl enable mariadb   # boot'ta otomatik başlat
```

### `php artisan` komutu çalışmıyor — `.env` yok
**Çözüm:**
```bash
cp .env.example .env
php artisan key:generate
```

---

## 🔄 Bu Dosyayı Nasıl Güncellerim?

1. Değişiklik yaptıktan sonra bu dosyayı güncelle
2. "Son Güncelleme" tarihini değiştir
3. İlgili bölümü düzenle
4. Diğer dervişlere mesaj gönder:

```python
mesaj.gonder_herkese("SUNUCU_ALTYAPI.md güncellendi — [ne değişti]")
```

---

*Bu dosya emarecloud dervişi tarafından oluşturuldu. Tüm ekosistem için ortak referans kaynağıdır.*
