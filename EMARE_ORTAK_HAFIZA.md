# 🧠 Emare Ekosistemi — Ortak Hafıza Dosyası

> **Son Güncelleme:** 4 Mart 2026  
> **Versiyon:** v1.0.0  
> **Kapsam:** Tüm Emare projeleri için paylaşılan bilgi tabanı  
> **Bu dosya tüm projelerde referans alınan ortak hafızadır. Kararlar, standartlar, altyapı ve ekosistem bilgisi burada korunur.**

---

## 🏛️ ÖNEMLİ: ANAYASA VE ORTAK ÇALIŞMA KLASÖRÜ ZORUNLULUĞU

**⚠️ KOD YAZMAYA BAŞLAMADAN ÖNCE MUTLAKA KONTROL ET:**

### 📂 Ortak Çalışma Klasörü

Her projede **root seviyesinde** `EMARE_ORTAK_CALISMA/` klasörü bulunur:

```
[Proje Klasörü]/
├── EMARE_ORTAK_CALISMA/              ← İLK BURAYA BAK!
│   ├── README.md                     (Klasör rehberi)
│   ├── EMARE_ANAYASA.md             (Kodlama kuralları - 16 madde)
│   ├── EMARE_ORTAK_HAFIZA.md        (Bu dosya - 21 projenin envanteri)
│   ├── EMARE_AI_COLLECTIVE.md       (21 AI'nın deneyimleri)
│   └── projects.json                 (Proje kayıtları)
├── DOSYA_YAPISI.md                   (Bu projenin dosya yapısı)
├── [proje]_hafiza.md                 (Bu projenin hafızası)
└── ...
```

### 📖 Okuma Sırası (Anayasa Madde 1)

Kod yazmaya başlamadan önce **sırasıyla** oku:

1. ✅ **EMARE_ORTAK_CALISMA/README.md** — Ortak klasör rehberi
2. ✅ **EMARE_ORTAK_CALISMA/EMARE_ANAYASA.md** — Kodlama kuralları (16 madde)
3. ✅ **EMARE_ORTAK_CALISMA/EMARE_ORTAK_HAFIZA.md** — Bu dosya (21 proje)
4. ✅ **EMARE_ORTAK_CALISMA/EMARE_AI_COLLECTIVE.md** — 21 AI deneyimi
5. ✅ **DOSYA_YAPISI.md** — Proje dosya yapısı
6. ✅ **[proje]_hafiza.md** — Proje hafızası

**Bu kurala uymayan AI'ların kodu kabul edilmez!**

---

## 📋 İÇİNDEKİLER

1. [Emare Nedir?](#1-emare-nedir)
2. [Proje Envanteri](#2-proje-envanteri)
3. [Sunucu & Altyapı Bilgileri](#3-sunucu--altyapı-bilgileri)
4. [Ortak Teknoloji Standartları](#4-ortak-teknoloji-standartları)
5. [Geliştirme Kuralları](#5-geliştirme-kuralları)
6. [Ortak Mimari Kararlar](#6-ortak-mimari-kararlar)
7. [Güvenlik Standartları](#7-güvenlik-standartları)
8. [Deploy & CI/CD](#8-deploy--cicd)
9. [Emare Hub — Merkezi Yönetim](#9-emare-hub--merkezi-yönetim)
10. [Projeler Arası Bağımlılıklar](#10-projeler-arası-bağımlılıklar)
11. [Gelecek Hedefler](#11-gelecek-hedefler)

---

## 1. Emare Nedir?

**Emare**, tek bir kişi (Emre) tarafından yönetilen, birden fazla SaaS ürün, otomasyon aracı ve altyapı yazılımından oluşan tam yığın bir yazılım ekosistemidir.

### Vizyon
- Her projenin kendi hafızası + paylaşılan ortak hafıza ile çalışması
- AI destekli otonom geliştirme (EmareSetup, EmareHup/DevM)
- Merkezi yönetim paneli (Emare Hub) üzerinden tüm projeleri yönetme
- Gelir üreten SaaS ürünler (Finance, Cloud, Asistan) + araç katmanı

### Genel İlkeler
- **Sıfırdan inşa et:** Mümkün olduğunda third-party bağımlılığı azalt
- **Hafıza dosyaları:** Her proje kendi bağlamını `.md` dosyasında tutar
- **Ortak akıl:** Tüm projeler bu dosyayı referans alır
- **AI-first:** Gemini AI ve OpenAI tüm projelerde birincil yardımcıdır

---

## 2. Proje Envanteri

| # | Proje | İkon | Durum | Faz | %  | Kategori | Teknoloji |
|---|-------|------|-------|-----|----|----------|-----------|
| 1 | **Emare Asistan** | 🤖 | Production | production | 90% | SaaS Platform | FastAPI, Python, Gemini AI, WhatsApp Bridge |
| 2 | **EmareCloud** | ☁️ | Production | production | 80% | Infrastructure | Flask, Python, SQLite, SocketIO, Paramiko |
| 3 | **Emare Finance** | 💰 | Production | production | 80% | SaaS Platform | Laravel 12, PHP 8.4, MariaDB, Tailwind CSS |
| 4 | **Emare POS / Adisyon** | 🍽️ | Development | mvp | 35% | POS | Laravel 12, PHP 8.2, SQLite, Alpine.js |
| 5 | **EmareDesk** | 🖥️ | Ready | beta | 65% | Tool | Python, WebSocket, Pillow, mss |
| 6 | **EmareSetup** | 🏭 | Development | scaffold | 17% | Infrastructure | Python, FastAPI, React 19, Gemini |
| 7 | **EmareHup** | 🧠 | Development | scaffold | 14% | Infrastructure | Python, Node.js, Gemini, Copilot, LangGraph |
| 8 | **Emarebot** | 🛍️ | Production | production | 70% | Automation | Python 3.12, Tkinter, Trendyol API, Gemini AI |
| 9 | **ZeusDB / EmareOracle** | 🗄️ | Development | scaffold | 12% | Core Engine | C (C11), B+Tree, WAL, ACID |
| 10 | **SiberEmare** | 🛡️ | Development | scaffold | 19% | Security | Python 3.11, LangGraph, Claude 3.5, GPT-4o |
| 11 | **Emare Log** | 📡 | Development | scaffold | 14% | SaaS Platform | Laravel 12, PHP 8.2, Bootstrap 5, Chart.js |
| 12 | **Emare Makale** | 📝 | Production | production | 70% | Tool | Python 3.9, Flask 3.0, SQLite, OpenAI gpt-4o |
| 13 | **Hive Coordinator** | 👥 | Ready | beta | 75% | Infrastructure | Python 3.11, FastAPI, PostgreSQL 16, Redis 7 |
| 14 | **Emare Team** | 🏢 | Production | production | 70% | Tool | Flask, SQLite, Vanilla JS, Tailwind CSS |
| 15 | **Emare Katip** | 📋 | Ready | beta | 65% | Tool | Python, Flask, pytest, GitPython |
| 16 | **Emare Ulak** | 🔌 | Development | scaffold | 17% | Tool | Node.js, Express.js, WebSocket, SQLite |
| 17 | **Emare Ads** | 📢 | Development | scaffold | 17% | Tool | TypeScript, React, Chrome Extension API, FastAPI |
| 18 | **Emare AI** | 🤖 | Development | scaffold | 19% | Core Engine | PyTorch, LLaMA/Mistral, FastAPI, vLLM/Ollama |
| 19 | **Emare OS** | 🖥️ | Development | scaffold | 27% | Core Engine | Rust, QEMU, NeuroKernel, Bare Metal |
| 20 | **Emare Code** | 💻 | Production | production | 70% | Tool | Python, FastAPI, Multi-AI, Jinja2, SQLite |
| 21 | **Emare CC** | ☎️ | Development | scaffold | 30% | SaaS Platform | Node.js, Asterisk, PostgreSQL, React, Docker |
| 22 | **Emare VS Code Asistan** | 🔮 | Development | scaffold | 14% | Tool | Python, Rich, Watchdog |
| 23 | **Emare Flow** | 🔄 | Development | scaffold | 27% | Automation | React 19, React Flow v12, FastAPI, Python |
| 24 | **Emare SuperApp** | 📱 | Development | mvp | 37% | Platform | FastAPI, Python, SQLAlchemy, SQLite |
| 25 | **EmareFree** | 🆓 | Development | scaffold | 10% | Research Tool | Python, requests, BeautifulSoup, pydantic |
| 26 | **Emare Appliance Desk** | 🔧 | Development | scaffold | 30% | SaaS Platform | PHP 8.2, Laravel 12, Laravel Breeze, Vite |
| 27 | **Emare Flux** | ⚡ | Planning | idea | 10% | Automation | — |
| 28 | **Emare GitHub** | 🐙 | Ready | beta | 65% | Tool | Python 3, subprocess, GitHub REST API |
| 29 | **Emare Google** | 🔍 | Development | scaffold | 19% | Automation | Node.js, Playwright, WebKit |
| 30 | **Emare IDI** | 🔐 | Planning | scaffold | 10% | Security | — |
| 31 | **Emare Sebil** | 🚰 | Planning | idea | 10% | Platform | — |
| 32 | **Emare Tedarik** | 📦 | Planning | scaffold | 10% | SaaS Platform | — |
| 33 | **Emare Dashboard** | 📊 | Production | production | 70% | Infrastructure | Python 3, Flask, Jinja2, HTML/CSS |
| 34 | **Girhup** | 🌐 | Planning | idea | 0% | Tool | — |
| 35 | **Sosyal Medya Yönetim Aracı** | 📣 | Development | scaffold | 33% | Tool | FastAPI, Python, Next.js, React |
| 36 | **Emare Hosting** | 🏠 | Development | scaffold | 17% | Infrastructure | Python |
| 37 | **Emare Intranet** | 🏢 | Development | scaffold | 20% | Platform | Flask, Python, Jinja2, SQLite |
| 38 | **Emare Crypto** | 💎 | Development | scaffold | 25% | Platform | FastAPI, Python, SQLAlchemy, SQLite |
| 39 | **Emare Pazar** | 🛒 | Development | scaffold | 24% | SaaS Platform | FastAPI, Python, React, Next.js |
| 40 | **Emare AI Music** | 🎵 | Development | scaffold | 25% | Platform | FastAPI, Python, SQLAlchemy, SQLite |
| 41 | **Emare Token** | 🪙 | Development | scaffold | 27% | Core Engine | Python, pytest |
| 42 | **Emare API** | 🔗 | Development | scaffold | 24% | Core Engine | Python |
| 43 | **Emare webdizayn** | 🎨 | Development | scaffold | 23% | Platform | FastAPI, Python, React, Next.js |

### Faz Açıklamaları
- **production** → Canlıda çalışıyor, gerçek kullanıcı var (8 proje)
- **beta** → Tamamlandı, deploy bekleniyor veya son test (4 proje)
- **mvp** → Çalışır prototip mevcut (2 proje)
- **scaffold** → Temel yapı kurulmuş, geliştirme devam ediyor (26 proje)
- **idea** → Fikir/planlama aşamasında (3 proje)

### Durum Dağılımı (6 Mart 2026)
- 🟢 **Production:** 8 proje — Ortalama %76 tamamlanma
- 🔵 **Beta:** 4 proje — Ortalama %68 tamamlanma
- 🟡 **MVP:** 2 proje — Ortalama %36 tamamlanma
- 🟠 **Scaffold:** 26 proje — Ortalama %21 tamamlanma
- ⚪ **Idea:** 3 proje — Ortalama %7 tamamlanma
- **Ekosistem ortalaması:** %36 tamamlanma, 66/100 sağlık skoru

**Toplam:** 43 proje | **Son tarama:** 6 Mart 2026

---

## 3. Sunucu & Altyapı Bilgileri

### Aktif Sunucular

| Sunucu | IP | Kullanım | Projeler |
|--------|----|----------|----------|
| **Ana Sunucu** | `77.92.152.3` | Emare Asistan API + Finance Web | Asistan (8000), Finance (3000) |
| **EmareCloud Sunucu** | `185.189.54.104` | EmareCloud paneli | EmareCloud (80) |

### Port Haritası (Lokal Geliştirme)

| Port | Proje |
|------|-------|
| 5555 | EmareCloud (lokal) + **Emare Hub** |
| 8000 | EmareSetup API / Emare Asistan (prod) |
| 8001 | Hive Coordinator API |
| 8080 | Emare POS / EmareDesk |
| 8082 | Emare Log |
| 3000 | Emare Finance |
| 5000 | Emare Makale |
| 5050 | Emare Team |

### Domain & DNS
- EmareCloud → Cloudflare ile yönetiliyor
- Tüm sunucular → Ubuntu Server

---

## 4. Ortak Teknoloji Standartları

### Backend
| Dil/Framework | Projeler |
|---|---|
| **Python / Flask** | EmareCloud, Emare Makale, Emare Team, Emare Hub |
| **Python / FastAPI** | Emare Asistan, EmareSetup, Hive Coordinator |
| **PHP / Laravel 12** | Emare Finance, Emare POS, Emare Log |
| **Python (standalone)** | EmareDesk, Emarebot, SiberEmare |
| **C (C11)** | ZeusDB / EmareOracle |

### Frontend
| Teknoloji | Kullanım |
|---|---|
| **Tailwind CSS** | Emare Finance, Emare Hub dashboard |
| **Alpine.js** | Emare Finance, Emare POS, Emare Hub |
| **Vanilla JS** | EmareCloud, Emare Team, EmareDesk |
| **React 19** | EmareSetup (frontend) |
| **xterm.js** | EmareCloud (web terminal) |

### Veritabanı
| DB | Projeler |
|---|---|
| **SQLite** | EmareCloud, Emare POS, Emare Makale, Emare Team |
| **MariaDB / MySQL** | Emare Finance |
| **PostgreSQL 16** | Hive Coordinator |
| **Neo4j** | SiberEmare (graph DB) |

### AI & LLM
| Model | Projeler |
|---|---|
| **Gemini AI (Google)** | Emare Asistan (birincil), EmareSetup, EmareHup, Emarebot |
| **OpenAI GPT-4o** | Emare Makale, SiberEmare |
| **Claude 3.5 Sonnet** | SiberEmare |
| **LangGraph** | SiberEmare, EmareHup/DevM |

---

## 5. Geliştirme Kuralları

### Python Projeleri
```
- Python 3.9+ (3.11 tercih)
- type | None sözdizimi YOK — Python 3.9 uyumlu olacak şekilde Optional[X]
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

### Genel
```
- Her proje kök dizininde hafıza .md dosyası bulunur
- README.md tüm projelerde olmalı
- Git ile versiyon kontrolü
- .env dosyası .gitignore'da
- Port çakışması olmayacak şekilde portlar atanmış (bkz. Port Haritası)
```

### Naming Convention
```
- Python dosyaları: snake_case.py
- PHP sınıfları: PascalCase
- JS değişkenleri: camelCase
- Proje klasörleri: küçük harf, tire ile
```

---

## 6. Ortak Mimari Kararlar

### Hafıza Sistemi
```
Tüm projeler → Kendi hafiza.md dosyası
Tüm projeler → EMARE_ORTAK_HAFIZA.md (bu dosya) referans alır
Emare Hub → projects.json ile tüm projeleri yönetir
hub_autodetect.py → Yeni projeleri otomatik algılar
```

### Modulerlik
- Her proje bağımsız çalışabilmeli
- Projeler arası doğrudan import YOK — HTTP API ile iletişim
- Ortak kodlar kopyalanır, merkezi lib paketi kullanılmaz (bağımsızlık)

### Deployment
```
Production → Sunucu üzerinde doğrudan Python/PHP ile çalıştırma
Konteyner → EmareCloud sunucusu için Docker Compose
Reverse Proxy → Nginx (EmareCloud, Finance)
Süreç Yönetimi → Supervisor (EmareCloud)
```

### CI/CD — Webhook Otomatik Deploy (6 Mart 2026)

**45/45 GitHub reposuna push webhook eklendi.**

| Ayar | Değer |
|------|-------|
| **Webhook URL** | `https://emarecloud.tr/api/deploy/webhook/emare-deploy-secret-2025` |
| **Tetikleyici** | `push` event (her commit/merge) |
| **Hedef** | EmareCloud paneli → otomatik deploy pipeline |
| **Kuran** | Emare GitHub dervişi (`setup_webhooks.py`) |

#### Auto-Deploy Projeler (9 proje)
Push yapıldığında **otomatik deploy** tetiklenen projeler:

| Proje | ID |
|-------|----|
| Emare Asistan | `emare-asistan` |
| EmareCloud | `emarecloud` |
| Emare Finance | `emare-finance` |
| Emare POS | `emare-pos` |
| Emare AI | `emareai` |
| Emare Intranet | `emareintranet` |
| Emare Pazar | `emarepazar` |
| Emare API | `emareapi` |
| Emare webdizayn | `emarewebdizayn` |

> Diğer 34 proje: Webhook tetiklenir ama deploy **manuel onay** gerektirir.

### Loglama
- Python → `logging` + dosyaya yaz
- Laravel → `storage/logs/laravel.log`
- Emare Hub → `/tmp/hub.log` veya terminale

---

## 7. Güvenlik Standartları

### API
- JWT veya Session tabanlı kimlik doğrulama (proje bağlı)
- CORS sadece gerekli domainlere açık
- Rate limiting (production'da)
- HTTPS zorunlu (production)

### Sunucu
- SSH key tabanlı giriş
- UFW firewall aktif (EmareCloud üzerinden yönetilir)
- Root login kapalı
- Fail2ban aktif

### Kod
- `.env` dosyaları asla commit edilmez
- API anahtarları ortam değişkenlerinde
- SQL injection → ORM kullanım (SQLAlchemy, Eloquent)
- XSS → şablon escape (Jinja2, Blade)

---

## 8. Deploy & CI/CD

### EmareCloud Sunucusu (185.189.54.104)
```bash
ssh root@185.189.54.104
cd /root/emarecloud
git pull origin main
supervisorctl restart emarecloud
```

### Ana Sunucu (77.92.152.3)
```bash
ssh root@77.92.152.3
# Asistan
cd /root/asistan && git pull && supervisorctl restart asistan
# Finance
cd /root/finance && git pull && php artisan migrate --force
```

### Lokal Geliştirme
```bash
# Emare Hub başlat
cd /Users/emre/Desktop/Emare
./start_hub.sh
# http://127.0.0.1:5555

# Hub CLI
python hub_cli.py list
python hub_cli.py ping
python hub_cli.py start <proje-id>
```

---

## 9. Emare Hub — Merkezi Yönetim

**Konum:** `/Users/emre/Desktop/Emare/`  
**URL:** `http://127.0.0.1:5555`  
**Başlatma:** `./start_hub.sh`

### Dosyalar
| Dosya | Açıklama |
|---|---|
| `hub.py` | Flask backend, 15+ API endpoint |
| `hub_cli.py` | Rich terminal CLI |
| `hub_templates/index.html` | Dark theme web dashboard |
| `hub_autodetect.py` | Otomatik proje algılama motoru |
| `projects.json` | Tüm projelerin yapılandırma kayıt dosyası |
| `start_hub.sh` | Tek komutla başlatma script'i |
| `.hub_venv/` | Emare Hub Python ortamı |
| `.hub_pids.json` | Çalışan proje PID'leri |

### API Endpoint'leri
```
GET  /api/projects          → Tüm projeler
POST /api/projects          → Yeni proje ekle
PUT  /api/projects/<id>     → Proje güncelle
DELETE /api/projects/<id>   → Proje sil
GET  /api/ping/<id>         → Sunucu ping
GET  /api/ping-all          → Tüm sunucuları ping
GET  /api/git/<id>          → Git durumu
GET  /api/git-all           → Tüm projelerin git durumu
POST /api/start/<id>        → Proje başlat
POST /api/stop/<id>         → Proje durdur
GET  /api/running           → Çalışan prosesler
GET  /api/memory/<id>       → Hafıza dosyası oku
GET  /api/notes/<id>        → Notlar
POST /api/notes/<id>        → Not ekle
GET  /api/stats             → Özet istatistikler
GET  /api/browse            → macOS klasör seçici
POST /api/detect            → Klasörü tara, proje bilgilerini çıkar
POST /api/vscode-sync       → VS Code workspace güncelle
POST /api/open-vscode/<id>  → Projeyi VS Code'da aç
```

---

## 10. Projeler Arası Bağımlılıklar

```
Emare Asistan
  └─ Gemini AI API (harici)
  └─ WhatsApp Bridge (ayrı servis)

EmareCloud
  └─ EmareToken / Blockchain modülü (dahili)
  └─ LXD (sunucu üzerinde)

Emare Finance
  └─ E-Fatura API (harici)
  └─ SMS API (harici)

EmareSetup
  └─ Gemini AI / OpenAI API (harici)
  └─ ZeusDB → ileride kendi DB motoru kullanabilir

EmareHup / DevM
  └─ VS Code Copilot (harici)
  └─ LangGraph (harici)
  └─ EmareSetup ile entegrasyon planlanıyor

SiberEmare
  └─ Neo4j (lokal/sunucu)
  └─ PGVector (PostgreSQL eklentisi)
  └─ Claude 3.5 + GPT-4o (harici)

Hive Coordinator
  └─ PostgreSQL 16 (lokal)
  └─ Redis 7 (lokal)

Emare Hub (bu sistem)
  └─ Tüm projeleri yönetir, bağımlılık yok
```

---

## 11. Gelecek Hedefler

### Kısa Vadeli
- [ ] EmareSetup → EmareHup/DevM ile tam entegrasyon
- [ ] ZeusDB → ilk SQL parser (SELECT * FROM test)  
- [ ] Emare POS → production deployment
- [ ] SiberEmare → .env doldur, ilk pentest raporu üret
- [ ] Emare Log → ilk tenant kaydı ve MikroTik bağlantısı

### Orta Vadeli
- [ ] Emare Finance → v2 migrasi (multi-tenant kira modeli)
- [ ] EmareCloud → v2 Kubernetes desteği
- [ ] Emare Hub → mobil uygulama (Flutter)
- [ ] Tüm projeler → merkezi loglama sistemi

### Uzun Vadeli
- [ ] ZeusDB → Emare ekosisteminin kendi veritabanı motoru haline gelsin
- [ ] EmareSetup → tam otonom yazılım geliştirme fabrikası
- [ ] EmareCloud → halka açık SaaS ürün

---

## 12. 🖥️ Son Sohbet Özeti — 4 Mart 2026 (iMac'e Geçiş Öncesi)

> Bu bölüm VS Code Copilot sohbetinin arşivi değildir.  
> Yeni bilgisayarda hızlıca bağlam kazanmak için yazılmıştır.

### Ne yapıldı?

#### A) Emarework Worker Sistemi (v2)
`emarework/koordinasyon-sistemi/src/emare_workers.py` tamamen yeniden yazıldı:
- **80+ tech eşlemesi** eklendi (21 projenin tüm stack'i kapsandı)
- `is_running()` → local port TCP ping
- `start_locally()` → local_start_cmd çalıştırma
- `read_memory(max_lines)` → hafıza MD dosyası okuma
- `match_score()` → uzmanlık overlap skoru (overlap × 10 + priority)
- `EmareAIWorkforce.reload()` → sıcak yeniden yükleme
- `find_by_category()`, `get_by_name()`, `find_by_expertise()` eklendi
- `running_workers()` → hangi projeler çalışıyor (async)
- `find_workers_with_scores()` → skor dahil dict listesi
- `availability`: artık `production` + `ready` ikisi de aktif

#### B) project_orchestrator.py düzeltmeleri
- `orchestrator.projects` → `orchestrator.active_projects` bug'ı düzeltildi
- `get_project_status()` → `project_name` key eksikliği düzeltildi
- `_execute_task()` → sonucu worker'ın `.emarework/tasks.log` dosyasına yazar
- `cancel_project(id)` eklendi
- `retry_failed_tasks(id)` eklendi
- `get_stats()` eklendi
- İptal kontrolü: `_execute_project` döngüsünde `self._cancelled` kontrolü

#### C) Yeni API Endpoint'leri (main.py)
```
GET  /workers/running          → çalışan projeleri tespit et
POST /workers/reload           → projects.json sıcak yenile
GET  /workers/stats            → istatistik (route ordering düzeltildi)
GET  /workers/search?q=        → isimle ara
GET  /workers/category/{cat}   → kategoriye göre filtrele
GET  /workers/{id}?memory=true → hafıza snippet dahil
POST /workers/task/rank        → skor sıralamalı worker listesi
POST /projects/{id}/cancel     → projeyi iptal et
POST /projects/{id}/retry      → başarısız task'ları yeniden dene
GET  /projects/stats           → tüm projeler istatistik
```

#### D) Emare Ekosistem Yöneticisi (emare_ecosystem.py — yeni dosya)
Manuel çalıştırılan script'lerin yerini API endpoint'leri aldı:
```
GET  /emare/health                  → 21 projenin sağlık kontrolü
GET  /emare/overview                → ekosistem genel görünüm
GET  /emare/projects                → tüm projeler + health skoru
GET  /emare/projects/{id}           → tek proje detayı
POST /emare/distribute              → EMARE_ORTAK_CALISMA dağıtımı
POST /emare/symlinks/repair         → kırık symlink onarımı
POST /emare/dosya-yapisi/refresh    → DOSYA_YAPISI.md yenileme
POST /emare/task/assign             → AI worker önerisi
```

#### E) Celery Otomatik Görevler (tasks.py + celery_app.py)
- Her 5 dakika: `emare_health_check` — 21 proje otomatik izleme
- Her 30 dakika: `emare_repair_symlinks` — kırık linkler onarılıyor
- Günlük: `emare_refresh_dosya_yapisi` — tüm DOSYA_YAPISI.md güncelleme

#### F) VS Code Ayarları
- `files.autoSave: afterDelay` aktif edildi

### Emarework Çalıştırma Komutu
```bash
cd /Users/emre/Desktop/Emare/emarework/koordinasyon-sistemi
uvicorn src.api.main:app --reload --port=8001
# Swagger: http://127.0.0.1:8001/docs
```

#### G) Emare Flow — 22. Proje (4 Mart 2026, iMac Geçişi Öncesi Eklendi)
- **Konum:** `/Users/emre/Desktop/Emare/emareflow/`
- **Konsept:** n8n benzeri React Flow tabanlı görsel iş akışı otomasyonu
- **Tech:** React 19, React Flow v12, FastAPI (port 8090), SQLite, Celery+Redis, Tailwind CSS
- **Hafıza:** `emareflow/emareflow_hafiza.md`
- **Frontend start:** `cd emareflow/frontend && npm install && npm run dev` → http://localhost:5173
- **Backend start:** `cd emareflow/backend && uvicorn main:app --reload --port=8090`
- **Oluşturulan bileşenler:** `App.jsx`, `AINode`, `HttpNode`, `FinanceNode`, `AsistanNode`
- **projects.json:** emareflow kaydı eklendi (hem root hem EMARE_ORTAK_CALISMA)

### Yeni iMac'te Başlarken
1. `/Users/emre/Desktop/Emare/` klasörünü taşı (tüm projeler burada)
2. VS Code'u aç → bu workspace'i aç
3. Copilot'a şunu söyle:  
   **"EMARE_ORTAK_CALISMA klasörünü oku, kaldığın yerden devam et"**
4. İlk bakılacak dosyalar:
   - `EMARE_ORTAK_CALISMA/EMARE_ORTAK_HAFIZA.md` (bu dosya)
   - `EMARE_ORTAK_CALISMA/EMARE_ANAYASA.md`
   - `emarework/koordinasyon-sistemi/src/emare_workers.py`
   - `emareflow/emareflow_hafiza.md` (22. proje — yeni)
5. Sıradaki aktif iş: `emareflow` frontend bileşenlerini genişlet + backend execution engine

---

*Bu dosya Emare Hub tarafından otomatik olarak senkronize edilebilir.*  
*Bireysel proje hafızaları için ilgili proje klasörüne bakınız.*
