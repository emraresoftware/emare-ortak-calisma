# 🔑 EMARE EKOSİSTEMİ — TAM BRİFİNG DOSYASI
## Gemini / Grok / ChatGPT / Diğer AI Botlar İçin Bağlam Anahtarı

> **Tarih:** 9 Mart 2026  
> **Hazırlayan:** Emare GitHub Dervişi (Copilot)  
> **Amaç:** Bu belgeyi okuyan herhangi bir AI, Emare ekosisteminin tamamına hakim olur.  
> **Talimat:** Bu dosyayı sohbete yapıştırarak AI'ya tüm projeyi öğretebilirsiniz.

---

## 📌 BU DOSYA NEDİR?

Bu, **Emare** yazılım ekosisteminin tüm bilgisini içeren bir brifing belgesidir. Amacı, Gemini, Grok, ChatGPT veya başka bir AI sohbet botuna yapıştırıldığında o AI'nın projenin tamamına hakim olmasını sağlamaktır.

---

## 1. EMARE NEDİR?

**Emare**, tek bir kişi (**Emre Gökdağ**) tarafından yönetilen, **45+ proje**den oluşan tam yığın bir yazılım ekosistemidir.

### Vizyon
- Her proje bağımsız çalışır ama ortak bir ekosistemde yaşar
- Her projenin bir **AI dervişi** (asistan) vardır
- Tüm dervişler ortak bir **anayasa** ve **haberleşme sistemi** ile çalışır
- AI-first yaklaşım: Gemini, GPT-4o, Claude geliştirme sürecinde birincil yardımcıdır
- Hedef: Gelir üreten SaaS ürünler + kendi altyapı katmanı

### Genel İlkeler
- **Sıfırdan inşa et** — Mümkünse third-party bağımlılığı azalt
- **Hafıza dosyaları** — Her proje `.md` dosyasında kendi bağlamını tutar
- **Ortak akıl** — 43+ derviş birbirine mesaj gönderebilir
- **Merkezi yönetim** — `EMARE_ORTAK_CALISMA/` symlink ile tüm projelerde ortak dosyalar

---

## 2. PROJE ENVANTERİ (43 Proje)

### Production (8 proje — Canlıda Çalışıyor)
| # | Proje | Teknoloji | Açıklama |
|---|-------|-----------|----------|
| 1 | **Emare Asistan** | FastAPI, Python, Gemini AI, WhatsApp Bridge | Multi-tenant SaaS AI platform, 1000+ kullanıcı |
| 2 | **EmareCloud** | Flask, Python, SQLite, SocketIO, Paramiko | Sunucu/altyapı yönetim paneli, 50+ sunucu |
| 3 | **Emare Finance** | Laravel 12, PHP 8.4, MariaDB, Tailwind CSS | İşletme yönetim + e-Fatura sistemi |
| 4 | **Emarebot** | Python 3.12, Tkinter, Trendyol API, Gemini AI | Trendyol e-ticaret otomasyon botu |
| 5 | **Emare Makale** | Python 3.9, Flask, SQLite, GPT-4o | AI ile makale üretim aracı |
| 6 | **Emare Team** | Flask, SQLite, Vanilla JS, Tailwind CSS | Ekip/görev yönetimi (Kanban) |
| 7 | **Emare Code** | Python, FastAPI, Multi-AI, Jinja2, SQLite | AI destekli kod üretim aracı |
| 8 | **Emare Dashboard** | Python 3, Flask, Jinja2, HTML/CSS | Merkezi dashboard |

### Beta (4 proje — Tamamlanmış, Deploy Bekliyor)
| # | Proje | Teknoloji | Açıklama |
|---|-------|-----------|----------|
| 9 | **EmareDesk** | Python, WebSocket, Pillow, mss | Uzak masaüstü bağlantı aracı |
| 10 | **Hive Coordinator** | Python 3.11, FastAPI, PostgreSQL 16, Redis 7 | Dağıtık görev koordinatörü |
| 11 | **Emare Katip** | Python, Flask, pytest, GitPython | Kod dokümantasyon aracı |
| 12 | **Emare GitHub** | Python 3, subprocess, GitHub REST API | GitHub ekosistem yönetim aracı (bu proje) |

### MVP (2 proje)
| # | Proje | Teknoloji | Açıklama |
|---|-------|-----------|----------|
| 13 | **Emare POS** | Laravel 12, PHP 8.2, SQLite, Alpine.js | Restoran adisyon/POS sistemi |
| 14 | **Emare SuperApp** | FastAPI, Python, SQLAlchemy, SQLite | Süper uygulama platformu |

### Geliştirme Aşamasında (26 proje)
| # | Proje | Teknoloji | Açıklama |
|---|-------|-----------|----------|
| 15 | **EmareSetup** | Python, FastAPI, React 19, Gemini | AI yazılım fabrikası (otonom modül üretimi) |
| 16 | **EmareHup** | Python, Node.js, Gemini, LangGraph | DevM — AI geliştirici orkestratör |
| 17 | **ZeusDB / EmareOracle** | C (C11), B+Tree, WAL, ACID | Kendi veritabanı motoru |
| 18 | **SiberEmare** | Python 3.11, LangGraph, Claude 3.5, GPT-4o, Neo4j | Siber güvenlik multi-agent |
| 19 | **Emare Log** | Laravel 12, PHP 8.2, Bootstrap 5, Chart.js | Log yönetim SaaS platformu |
| 20 | **Emare Ulak** | Node.js, Express.js, WebSocket, SQLite | Mesajlaşma/iletişim aracı |
| 21 | **Emare Ads** | TypeScript, React, Chrome Extension API, FastAPI | Reklam yönetim aracı |
| 22 | **Emare AI** | PyTorch, LLaMA/Mistral, FastAPI, vLLM/Ollama | Self-hosted AI modeli |
| 23 | **Emare OS** | Rust, QEMU, NeuroKernel, Bare Metal | Kendi işletim sistemi |
| 24 | **Emare CC** | Node.js, Asterisk, PostgreSQL, React, Docker | Çağrı merkezi platformu |
| 25 | **Emare VS Code Asistan** | Python, Rich, Watchdog | VS Code yapılandırma yöneticisi |
| 26 | **Emare Flow** | React 19, React Flow v12, FastAPI, Python | Görsel otomasyon akış tasarımcısı |
| 27 | **EmareFree** | Python, requests, BeautifulSoup, pydantic | Web araştırma aracı |
| 28 | **Emare Appliance Desk** | PHP 8.2, Laravel 12, Breeze, Vite | Beyaz eşya servis SaaS |
| 29 | **Emare Google** | Node.js, Playwright, WebKit | Google otomasyon aracı |
| 30 | **Emare Hosting** | Python | Hosting yönetim paneli |
| 31 | **Emare Intranet** | Flask, Python, Jinja2, SQLite | Şirket içi intranet |
| 32 | **Emare Crypto** | FastAPI, Python, SQLAlchemy, SQLite | Kripto platform |
| 33 | **Emare Pazar** | FastAPI, Python, React, Next.js | Pazar yeri platformu |
| 34 | **Emare AI Music** | FastAPI, Python, SQLAlchemy, SQLite | AI müzik üretim platformu |
| 35 | **Emare Token** | Python, pytest | Token/kripto altyapısı |
| 36 | **Emare API** | Python | Merkezi API gateway |
| 37 | **Emare webdizayn** | FastAPI, Python, React, Next.js | Web tasarım platformu |
| 38 | **Sosyal Medya Yönetim** | FastAPI, Python, Next.js, React | Sosyal medya yönetim aracı |
| 39 | **Emare IDI** | — | Dijital kimlik sistemi (planlama) |
| 40 | **Emare Sebil** | — | Platform (planlama) |
| 41 | **Emare Tedarik** | — | Tedarik zinciri SaaS (planlama) |
| 42 | **Emare Flux** | — | Otomasyon aracı (planlama) |

### İstatistik
- **Production:** 8 proje (~%76 tamamlanma)
- **Beta:** 4 proje (~%68 tamamlanma)
- **MVP:** 2 proje (~%36 tamamlanma)
- **Scaffold:** 26 proje (~%21 tamamlanma)
- **Idea:** 3 proje (~%7 tamamlanma)
- **Ekosistem ortalaması:** %36 tamamlanma

---

## 3. SUNUCU & ALTYAPI

### Sunucular
| Kod | IP | SSH Port | OS | Rol |
|-----|-----|----------|-----|------|
| **DC-1** | 185.189.54.104 | 22 | AlmaLinux 9.6 | ecomaiq.com, API, DApp |
| **DC-2** | 77.92.152.3 | 2222 | AlmaLinux | emarecloud.tr, POS, Finans, Asistan |
| **DC-3** | *(detay bekleniyor)* | 22 | — | emarecloud çalışıyor |

### Canlı Servisler
| Servis | URL | Sunucu | Port | Teknoloji |
|--------|-----|--------|------|-----------|
| Ecomaiq/Soru-Cevap | https://ecomaiq.com | DC-1 | 3639 | Node (PM2) |
| Emare API | — | DC-1 | 8000 | Python uvicorn |
| EmareCloud Panel | https://emarecloud.tr | DC-2 | 5555 | Flask Gunicorn |
| Emare Asistan | https://asistan.emarecloud.tr | DC-2 | 8201 | Python uvicorn |
| Emare Finans | https://finans.emarecloud.tr | DC-2 | — | PHP-FPM Laravel |
| Emare POS | https://pos.emarecloud.tr | DC-2 | — | PHP-FPM Laravel |

### Port Haritası (Lokal Geliştirme)
| Port | Proje |
|------|-------|
| 3000 | Emare Finance |
| 5000 | Emare Makale |
| 5050 | Emare Team |
| 5555 | EmareCloud + Emare Hub |
| 8000 | EmareSetup API / Emare Asistan (prod) |
| 8001 | Hive Coordinator API |
| 8080 | Emare POS / EmareDesk |
| 8082 | Emare Log |

### Domain & DNS
- EmareCloud → Cloudflare ile yönetiliyor
- Tüm sunucular → Ubuntu/AlmaLinux Server
- SSL → Let's Encrypt + acme.sh

---

## 4. TEKNOLOJİ STANDARTLARI

### Backend
| Dil | Birincil Framework | İkincil | Kullanan Projeler |
|-----|--------------------|---------|-------------------|
| Python | **FastAPI** | Flask | Asistan, Setup, Hive, Cloud, Makale, Team |
| PHP | **Laravel 12** | — | Finance, POS, Log, Appliance Desk |
| Node.js | **Express.js** | Fastify | Ulak, CC, Ecomaiq |
| Rust | **Axum** | Actix-web | Emare OS |
| C | Standart C11 | — | ZeusDB |

### Veritabanı
| DB | Kullanım | Projeler |
|----|----------|----------|
| **SQLite** | Hafif projeler | Cloud, POS, Makale, Team, SuperApp |
| **MariaDB/MySQL** | Production web | Finance |
| **PostgreSQL 16** | Ağır yük | Hive Coordinator, CC |
| **Neo4j** | Graph verileri | SiberEmare |

### AI Modeller
| Öncelik | Model | Kullanım |
|---------|-------|----------|
| 1 | **Gemini 1.5 Pro** | Birincil AI (maliyet/performans) |
| 2 | **GPT-4o** | Yedek (kalite) |
| 3 | **Claude 3.5 Sonnet** | Reasoning |
| 4 | **Emare AI** | Self-hosted (gelecek) |

### Frontend
- **React 19** — Modern web apps (Setup, Flow, Pazar)
- **Alpine.js** — Lightweight interactivity (Finance, POS)
- **Tailwind CSS** — Styling (Finance, Hub)
- **Vanilla JS** — Basit projeler (Cloud, Team)

---

## 5. MİMARİ PRENSİPLER

### Hafıza Sistemi
Her projede:
```
[Proje]/
├── EMARE_ORTAK_CALISMA/     ← Symlink → Merkezi ortak klasör
│   ├── EMARE_ANAYASA.md     ← Kodlama kuralları (18 madde)
│   ├── EMARE_ORTAK_HAFIZA.md ← 43 proje envanteri
│   ├── EMARE_AI_COLLECTIVE.md ← AI deneyimleri
│   ├── emare_messenger.py   ← Haberleşme sistemi
│   └── projects.json         ← Proje kayıtları
├── DOSYA_YAPISI.md           ← Bu projenin dosya yapısı
├── [proje]_hafiza.md         ← Bu projenin hafızası
└── .github/
    ├── copilot-instructions.md ← Derviş talimatları
    └── workflows/
        └── mesaj-alici.yml   ← GitHub Actions mesaj alıcı
```

### Modülerlik
- Her proje bağımsız çalışabilmeli
- Projeler arası doğrudan import YOK — HTTP API ile iletişim
- Ortak kodlar kopyalanır, merkezi lib paketi kullanılmaz

### Deploy Mimarisi
- **Production:** Doğrudan Python/PHP ile çalıştırma
- **Konteyner:** EmareCloud sunucusu için Docker Compose
- **Reverse Proxy:** Nginx
- **Süreç Yönetimi:** Supervisor (Python), PHP-FPM (Laravel)
- **CI/CD:** GitHub push webhook → EmareCloud deploy pipeline (45 repo)

---

## 6. DERVİŞ HABERLEŞMESİ

### Derviş = Proje AI Asistanı
Her projenin bir "dervişi" (AI asistanı) vardır. Bu dervişler birbirleriyle haberleşebilir.

### Haberleşme Sistemi
- **Altyapı:** GitHub Issues (`emraresoftware/emare-ortak-calisma` reposunda)
- **Label'lar:** `dervis-mesaj`, `duyuru`, `acil`, `alici:X`, `gonderen:Y`
- **CLI:** `python3 EMARE_ORTAK_CALISMA/emare_messenger.py {dervis_adi} oku|gonder|herkese|yanit`

### Push Bildirim Sistemi (GitHub Actions)
1. Merkezi workflow (`mesaj-dagitici.yml`) — Issue açılınca alıcıya `repository_dispatch` gönderir
2. Alıcı workflow (`mesaj-alici.yml`) — Her projede, mesaj gelince `.github/YENI_MESAJ.md` dosyası oluşturur
3. Derviş oturum başlangıcında bu dosyayı kontrol eder

### Mesaj Gönderme Kuralları
- API endpoint değiştiğinde → etkilenen dervişlere bildir
- Breaking change yaptığında → herkese duyur
- Kritik bug bulduğunda → acil mesaj gönder
- Yeni servis/modül eklediğinde → duyur

---

## 7. EMARE ANAYASA ÖZETİ (18 MADDE)

| Madde | Konu | Özet |
|-------|------|------|
| 1 | Ortak Çalışma Klasörü | Kod yazmadan önce `EMARE_ORTAK_CALISMA/` kontrol et, hafızayı oku |
| 2 | Mevcut Kod Kontrolü | Yeni dosya/fonksiyon yazmadan benzerini ara |
| 3 | Teknoloji Standardı | FastAPI, Laravel 12, PostgreSQL, Gemini AI kullan |
| 4 | Dokümantasyon | Her fonksiyona docstring, her modüle README |
| 5 | Hata Yönetimi | try-except zorunlu, loglama standart |
| 6 | Güvenlik | .env ile config, input validation, SQL injection koruması |
| 7 | Test | Kritik fonksiyonlara test yaz |
| 8 | Git Kullanımı | feat/fix/docs: commit convention |
| 9 | Performans | N+1 query yasak, cache kullan |
| 10 | API Standardı | RESTful, /health endpoint, versiyonlama |
| 11 | Dosya Yapısı | DOSYA_YAPISI.md güncel tut |
| 12 | Ortak Hafıza | Hafıza dosyalarını güncelle |
| 13 | Yaptırımlar | 🟡 Sarı / 🟠 Turuncu / 🔴 Kırmızı kart sistemi |
| 14 | AI Collective | Deneyimleri paylaş |
| 15 | Hub Entegrasyonu | projects.json ile kayıt ol |
| 16 | Deploy Uyumluluğu | Dockerfile veya deploy script hazır tut |
| 17 | Bağımsızlık | Dervişler projeleri arası doğrudan import etmez |
| 18 | Derviş Haberleşme | emare_messenger.py ile haberleş |

---

## 8. GELİŞTİRME KURALLARI

### Python Projeleri
```
- Python 3.9+ (3.11 tercih)
- Optional[X] sözdizimi (Python 3.9 uyumlu)
- venv veya .venv klasörü proje içinde
- requirements.txt zorunlu
- app.py veya main.py giriş noktası
```

### PHP / Laravel Projeleri
```
- Laravel 12, PHP 8.2+
- Blade şablonlar
- Artisan CLI ile migration
- .env ile yapılandırma
- composer.json zorunlu
```

### Naming Convention
```
- Python dosyaları: snake_case.py
- PHP sınıfları: PascalCase
- JS değişkenleri: camelCase
- Proje klasörleri: küçük harf, tire ile
- Türkçe fonksiyon/değişken adı mümkünse kullanılır
```

### Commit Convention
```
feat: yeni özellik
fix: hata düzeltme
docs: dokümantasyon
refactor: yeniden yapılandırma
test: test ekleme
chore: bakım işleri
```

---

## 9. GÜVENLİK

### Token Yönetimi
- GitHub Classic Token: `ghp_****` formatında (aktif, full scope)
- Organization: `emraresoftware`
- 45+ repo, hepsi private
- Tüm repolarda `EMARE_TOKEN` GitHub Actions secret olarak ayarlanmış
- Token hiçbir zaman koda yazılmaz — `.env` veya `secrets` kullanılır

### Genel Güvenlik
- Push Protection aktif — token sızıntısı engellenir
- SSH key ile sunucu erişimi
- UFW firewall (DC-2'de aktif)
- Fail2ban (kurulum önerilir)
- Input validation zorunlu
- SQL injection koruması zorunlu
- .env dosyası .gitignore'da

---

## 10. PROJELER ARASI BAĞIMLILIKLAR

```
Emare Asistan ──→ (WhatsApp API) ──→ Emare Finance (bildirim)
Emare Finance ──→ (fatura API) ──→ Emare POS
EmareCloud ──→ (deploy pipeline) ──→ Tüm projeler (webhook)
EmareSetup ──→ (modül üretimi) ──→ Tüm projeler
EmareHup ──→ (geliştirici orkestrasyon) ──→ Tüm projeler
Emare GitHub ──→ (repo yönetimi) ──→ Tüm projeler
Hive Coordinator ──→ (görev dağıtımı) ──→ Agent projeler
SiberEmare ──→ (güvenlik tarama) ──→ Tüm projeler
Emare Hub (Dashboard) ──→ (izleme) ──→ Tüm projeler
```

---

## 11. GİTHUB YAPISI

### Organization
- **Org:** `emraresoftware`
- **Repo sayısı:** 45+
- **Tüm repolar:** Private
- **Branch:** main (tek branch)
- **Push webhook:** 45 repoda aktif → EmareCloud deploy pipeline

### GitHub Actions Workflow'ları
1. **mesaj-dagitici.yml** (emare-ortak-calisma) — Merkezi mesaj dispatch
2. **mesaj-alici.yml** (tüm projeler) — Mesaj alıcı
3. **ci.yml** (emarecloud) — Lint + test
4. **emare-hub.yml** (emaresetup) — CI/CD pipeline

---

## 12. GELECEK HEDEFLER

### Kısa Vade (Mart 2026)
- [ ] DC1 firewall düzeltmesi (GitHub erişimi)
- [ ] Emare Asistan WhatsApp bridge stabilizasyonu
- [ ] Production projelerin %90'a tamamlanması

### Orta Vade (Q2 2026)
- [ ] ZeusDB alpha sürümü
- [ ] Emare OS ilk boot
- [ ] Emare AI self-hosted model
- [ ] Emare Hub merkezi yönetim paneli

### Uzun Vade
- [ ] Tüm projelerin production'a çıkması
- [ ] Tam otonom CI/CD pipeline
- [ ] Hive Coordinator ile dağıtık görev yönetimi

---

## 13. BU DOSYAYI NASIL KULLANIRSIN?

### AI Sohbet Botlarına Verildiğinde:
1. Bu dosyanın tamamını sohbete yapıştır
2. "Bu Emare ekosisteminin brifing belgesi. Bunu öğren ve sorularıma buna göre cevap ver." de
3. Artık AI, tüm projeleri, teknolojileri, altyapıyı ve kuralları bilecektir

### Örnek Prompt'lar:
- "Emare Finance'a yeni bir ödeme modülü eklemem lazım. Hangi teknolojileri kullanmalıyım?"
- "EmareCloud ile Emare Asistan arasında nasıl bir entegrasyon kurabilirim?"
- "ZeusDB'nin mimarisini anlatır mısın ve ne aşamada?"
- "Yeni bir proje eklemek istiyorum. Adımlar neler?"
- "SiberEmare bir güvenlik taraması yapsa hangi projeleri taramalı?"

---

## 14. HIZLI REFERANS KARTI

```
📦 Toplam Proje: 43+
🏢 Organization: emraresoftware (GitHub)
🖥️ Sunucular: DC-1 (185.189.54.104), DC-2 (77.92.152.3)
🌐 Domain: emarecloud.tr, ecomaiq.com
💻 Backend: FastAPI (Python), Laravel 12 (PHP), Express.js (Node)
🗄️ Veritabanı: SQLite, MariaDB, PostgreSQL, Neo4j
🤖 AI: Gemini 1.5 Pro, GPT-4o, Claude 3.5
🎨 Frontend: React 19, Alpine.js, Tailwind CSS, Vanilla JS
📡 Deploy: GitHub webhook → EmareCloud → nginx
🔐 Güvenlik: Push Protection, SSH key, UFW, Fail2ban
💬 Haberleşme: GitHub Issues + Actions (derviş mesajlaşma)
📋 Anayasa: 18 madde kodlama kuralı
🔗 Symlink: EMARE_ORTAK_CALISMA/ tüm projelerde ortak
```

---

*Bu belge, Emare ekosisteminin 9 Mart 2026 itibarıyla anlık görüntüsüdür.*
*Güncellemeler için: `EMARE_ORTAK_CALISMA/EMARE_ORTAK_HAFIZA.md` kontrol edin.*
