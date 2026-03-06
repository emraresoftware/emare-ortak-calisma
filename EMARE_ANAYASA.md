# 🏛️ EMARE ANAYASA — Yapay Zeka Kodlama Kuralları

> **Yürürlük Tarihi:** 4 Mart 2026  
> **Kapsam:** Emare ekosistemindeki tüm yapay zekalar  
> **Amaç:** Tutarlı, kaliteli ve sürdürülebilir kod üretimi  
> **Bağlayıcılık:** Bu anayasadaki tüm maddeler **zorunludur**

---

## 📜 Temel İlkeler

Emare ekosisteminde kod yazan her yapay zeka bu anayasaya uymak zorundadır. Bu kurallar, 21 proje arasında tutarlılık, kod kalitesi ve verimlilik sağlamak için konulmuştur.

---

## Madde 1: Ortak Çalışma Klasörü ve Hafıza Zorunluluğu

**Kod yazmaya başlamadan önce MUTLAKA `EMARE_ORTAK_CALISMA/` klasörünü kontrol et ve ortak hafızayı oku.**

### 1.1. Ortak Çalışma Klasörü (🔗 Merkezi Symlink Sistemi)

Her projede **root seviyesinde** `EMARE_ORTAK_CALISMA/` bulunur ve bu bir **symlink**'tir:

```
🔗 SYMLINK SİSTEMİ:

Merkezi Konum:
/Users/emre/Desktop/Emare/EMARE_ORTAK_CALISMA/
├── README.md                     (Klasör rehberi)
├── EMARE_ANAYASA.md             (Bu dosya - Kodlama kuralları)
├── EMARE_ORTAK_HAFIZA.md        (21 projenin envanteri)
├── EMARE_AI_COLLECTIVE.md       (21 AI'nın deneyimleri)
└── projects.json                 (Proje kayıtları)

Her Projede:
[Proje]/EMARE_ORTAK_CALISMA/ → (symlink) → Merkezi klasör
[Proje]/DOSYA_YAPISI.md       (Bu projenin dosya yapısı)
[Proje]/[proje]_hafiza.md     (Bu projenin hafızası)
```

**🔗 Symlink Avantajları:**
- ✅ **Tek kaynak doğruluk:** Sadece merkezi klasörü güncellersiniz
- ✅ **Otomatik senkronizasyon:** Değişiklik anlık tüm projelere yansır
- ✅ **Disk tasarrufu:** ~2MB yerine sadece 96KB
- ✅ **Tutarlılık garantisi:** Hiçbir proje eski sürümde kalamaz

**⚠️ ÖNEMLİ:** 
- EMARE_ORTAK_CALISMA bir symlink'tir, doğrudan değiştirmeyin!
- Güncelleme için: `/Users/emre/Desktop/Emare/EMARE_ORTAK_CALISMA/` 
- Ortak çalışma klasörü olmadan kod yazmak **YASAKTIR!**

### 1.2. Zorunlu Okuma Listesi

Kod yazmaya başlamadan önce **sırasıyla** şunları oku:

```markdown
📖 OKUMA SIRASI:
1. ✅ EMARE_ORTAK_CALISMA/README.md
   → Ortak klasörün kullanım rehberi
   
2. ✅ EMARE_ORTAK_CALISMA/EMARE_ANAYASA.md
   → Kodlama kuralları (16 madde)
   
3. ✅ EMARE_ORTAK_CALISMA/EMARE_ORTAK_HAFIZA.md
   → 21 projenin envanteri ve ekosistem bilgisi
   
4. ✅ EMARE_ORTAK_CALISMA/EMARE_AI_COLLECTIVE.md
   → 21 AI'nın deneyimleri ve önerileri
   
5. ✅ DOSYA_YAPISI.md (proje klasöründe)
   → Bu projenin mevcut dosya yapısı
   
6. ✅ [proje]_hafiza.md (proje klasöründe)
   → Bu projenin özel hafızası ve notları
```

### 1.3. Okuma Zamanı

**İlk kez projede çalışırken:**
- Tüm dosyaları dikkatlice oku (~30-45 dakika)
- Anayasa maddelerini ezberle
- Proje envanterini öğren

**Her yeni görevde:**
- İlgili maddeleri tekrar oku (~5-10 dakika)
- Benzer problem çözümü var mı kontrol et
- Güncel standartları kontrol et

**Neden?**
- Aynı kodu iki kez yazmamak
- Mevcut projelerin özelliklerini bilmek
- Diğer AI'ların deneyimlerinden faydalanmak
- Standartlara uymak
- Kodun tutarlı ve kaliteli olmasını sağlamak

**Yaptırım:**
- ❌ Ortak çalışma klasörünü kontrol etmeyen AI'nın kodu kabul edilmez
- ❌ Bu maddeye uymayan kod otomatik red edilir
- 🟠 Turuncu kart (ciddi ihlal)
- ⏳ Code review'da en az 1 gün gecikme

---

## Madde 2: Mevcut Kod Kontrolü

**Yeni bir dosya/fonksiyon yazmadan önce benzerinin var olup olmadığını kontrol et.**

### 2.1. Dosya Kontrolü
```bash
# Yeni dosya oluşturmadan önce:
1. DOSYA_YAPISI.md'yi kontrol et
2. Benzer isimli dosya var mı bak
3. İlgili modülün içini incele
```

### 2.2. Fonksiyon/Sınıf Kontrolü
```bash
# Yeni fonksiyon yazmadan önce:
1. Proje içinde `grep` veya semantic search yap
2. Aynı işi yapan kod var mı kontrol et
3. Varsa onu kullan veya refactor et
```

### 2.3. Kütüphane Kontrolü
```bash
# Yeni dependency eklemeden önce:
1. requirements.txt / package.json kontrol et
2. Benzer kütüphane zaten var mı bak
3. EMARE_AI_COLLECTIVE.md'de önerilen kütüphanelere bak
```

**Örnek:**
```
❌ YANLIŞ:
AI: "Yeni bir auth.py dosyası oluşturalım."

✅ DOĞRU:
AI: "DOSYA_YAPISI.md'yi kontrol ettim. 
     app/auth.py zaten var. 
     Mevcut authentication sistemini kullanıyorum."
```

---

## Madde 3: Teknoloji Standardı

**Emare ekosisteminin standart teknolojilerini kullan.**

### 3.1. Backend Framework
| Dil | Birincil | İkincil |
|-----|----------|---------|
| Python | **FastAPI** | Flask |
| PHP | **Laravel 12** | - |
| Node.js | **Express.js** | Fastify |
| Rust | **Axum** | Actix-web |

### 3.2. Database
| Kullanım | Standart | Alternatif |
|----------|----------|------------|
| Production | **PostgreSQL 16** | MySQL 8 |
| Lightweight | **SQLite** | - |
| Future | **ZeusDB** | - |

### 3.3. AI Model
| Öncelik | Model | Kullanım |
|---------|-------|----------|
| 1 | **Gemini 1.5 Pro** | Birincil AI (maliyet/performans) |
| 2 | **GPT-4o** | Yedek (kalite) |
| 3 | **Claude 3.5 Sonnet** | Reasoning |
| 4 | **Emare AI** | Self-hosted (gelecek) |

### 3.4. Frontend
- **React 19:** Modern web apps
- **Alpine.js:** Lightweight interactivity
- **Tailwind CSS:** Styling

**Yaptırım:**
- ⚠️ Standardın dışında bir teknoloji kullanıyorsan gerekçe belirt
- ❌ Gerekçesiz farklı teknoloji kullanımı kabul edilmez

---

## Madde 4: Dokümantasyon Zorunluluğu

**Her kod bloğu yeterli dokümantasyona sahip olmalı.**

### 4.1. Kod İçi Dokümantasyon
```python
# ✅ DOĞRU: Her fonksiyon docstring'e sahip
def calculate_discount(price: float, customer_type: str) -> float:
    """
    Müşteri tipine göre indirim hesaplar.
    
    Args:
        price: Ürün fiyatı (TL)
        customer_type: "bireysel" veya "kurumsal"
    
    Returns:
        İndirimli fiyat
    
    Raises:
        ValueError: Geçersiz customer_type
    """
    pass
```

### 4.2. README Güncellemesi
- Yeni özellik eklersen → README.md'yi güncelle
- API endpoint eklersen → API dokümantasyonu yaz
- Config değişiklikleri → .env.example güncelle

### 4.3. Hafıza Dosyası Güncellemesi
- Önemli mimari değişiklik → *_hafiza.md'yi güncelle
- Yeni teknoloji eklenirse → EMARE_ORTAK_HAFIZA.md'ye bildir

---

## Madde 5: Test Yazımı

**Her yeni özellik testlerle birlikte gelmelidir.**

### 5.1. Unit Test
```python
# Her fonksiyon için unit test yaz
def test_calculate_discount():
    assert calculate_discount(100, "bireysel") == 90
    assert calculate_discount(100, "kurumsal") == 80
    
    with pytest.raises(ValueError):
        calculate_discount(100, "invalid")
```

### 5.2. Integration Test
- API endpoint'leri için integration test
- Database işlemleri için transaction test
- External service'ler için mock test

### 5.3. Test Coverage
- **Minimum %70 coverage**
- Critical path için %100 coverage
- Test komutları README.md'de belirtilmeli

---

## Madde 6: Güvenlik Önlemleri

**Güvenlik açığı yaratmamak birinci önceliktir.**

### 6.1. Hassas Veri
```python
# ❌ ASLA:
password = "admin123"  # Hardcoded password
api_key = "sk-1234567890"  # Hardcoded API key

# ✅ HER ZAMAN:
password = os.getenv("DB_PASSWORD")
api_key = os.getenv("GEMINI_API_KEY")
```

### 6.2. SQL Injection
```python
# ❌ ASLA:
query = f"SELECT * FROM users WHERE id = {user_id}"

# ✅ HER ZAMAN:
query = "SELECT * FROM users WHERE id = ?"
cursor.execute(query, (user_id,))
```

### 6.3. Input Validation
```python
# ✅ Her input'u validate et
@app.post("/users")
def create_user(data: UserSchema):  # Pydantic validation
    if not validate_email(data.email):
        raise HTTPException(400, "Invalid email")
```

### 6.4. Authentication
- JWT token kullan (session yerine)
- Token'ı `.env` dosyasında sakla
- HTTPS zorunlu (production)
- Rate limiting uygula

---

## Madde 7: AI Collective'den Öğren

**Diğer AI'ların deneyimlerinden faydalanmalısın.**

### 7.1. Benzer Problemler
```markdown
Problem: WhatsApp entegrasyonu nasıl yapılır?
→ EMARE_AI_COLLECTIVE.md'de AI-ASISTAN'ın önerilerine bak
→ Onun kullandığı kütüphaneyi/yaklaşımı kullan
```

### 7.2. Teknoloji Seçimi
```markdown
Problem: Queue sistemi kuracağım
→ AI Collective voting'e bak: Celery + Redis (8 vote)
→ RabbitMQ değil, Celery kullan
```

### 7.3. Best Practices
```markdown
Her AI'nın öğrendiği en önemli ders bölümünü oku:
- AI-FINANCE: "Multi-tenant DB connection pool"
- AI-CLOUD: "Firewall olmadan production'a çıkma"
- AI-OS: "Rust unsafe kod → Miri ile test et"
```

---

## Madde 8: Hata Yönetimi

**Her hata durumu ele alınmalıdır.**

### 8.1. Try-Catch
```python
# ✅ Her external call try-catch içinde
try:
    response = requests.get(api_url, timeout=10)
    response.raise_for_status()
except requests.Timeout:
    logger.error("API timeout")
    return {"error": "Service unavailable"}
except requests.HTTPError as e:
    logger.error(f"API error: {e}")
    return {"error": "External service error"}
```

### 8.2. Logging
```python
# ✅ Structured logging kullan
logger.info("User login", extra={
    "user_id": user.id,
    "ip": request.remote_addr,
    "timestamp": datetime.now()
})
```

### 8.3. Graceful Degradation
```python
# ✅ Birincil servis çökerse yedek kullan
try:
    result = gemini_ai.generate(prompt)
except Exception:
    logger.warning("Gemini failed, trying OpenAI")
    result = openai_ai.generate(prompt)
```

---

## Madde 9: Performance Optimization

**Performansı göz ardı etme.**

### 9.1. Database Query
```python
# ❌ N+1 Query Problem:
users = User.query.all()
for user in users:
    orders = user.orders  # Her user için ayrı query

# ✅ Eager Loading:
users = User.query.options(joinedload(User.orders)).all()
```

### 9.2. Caching
```python
# ✅ Sık kullanılan verileri cache'le
@cache.memoize(timeout=300)
def get_product_list():
    return db.session.query(Product).all()
```

### 9.3. Asenkron İşlemler
```python
# ✅ Uzun işlemleri Celery'de çalıştır
@celery.task
def send_bulk_email(user_ids):
    for user_id in user_ids:
        send_email(user_id)

# API endpoint:
send_bulk_email.delay([1, 2, 3, ...])
```

---

## Madde 10: Code Review Süreci

**Her kod önce review edilmelidir.**

### 10.1. Self Review
Kodu commit'lemeden önce kendin kontrol et:
- [ ] Anayasa maddelerine uygun mu?
- [ ] Test yazıldı mı?
- [ ] Dokümantasyon var mı?
- [ ] Güvenlik açığı var mı?
- [ ] DOSYA_YAPISI.md'yi okudum mu?
- [ ] Mevcut benzer kod var mı?

### 10.2. AI Review
Diğer AI'lardan feedback al:
```markdown
@AI-FINANCE Bu multi-tenant yapıyı inceler misin?
@AI-CLOUD Bu firewall config'i güvenli mi?
```

### 10.3. Red Kriterleri
Aşağıdaki durumlarda kod otomatik red edilir:
- ❌ Madde 1'e uymamış (Ortak hafıza okunmamış)
- ❌ Test yok
- ❌ Dokümantasyon yok
- ❌ Güvenlik açığı var
- ❌ Hardcoded credentials

---

## Madde 11: Versiyon Kontrolü

**Her değişiklik git ile takip edilmelidir.**

### 11.1. Commit Message
```bash
# ✅ Anlamlı commit mesajları:
git commit -m "feat: Add JWT authentication to user API"
git commit -m "fix: SQL injection vulnerability in search endpoint"
git commit -m "docs: Update API documentation for v2.0"

# ❌ Kötü commit mesajları:
git commit -m "update"
git commit -m "fix"
git commit -m "asdasd"
```

### 11.2. Branch Strategy
```bash
main         # Production-ready kod
develop      # Development branch
feature/*    # Yeni özellikler
fix/*        # Bug fix'ler
```

### 11.3. Pull Request
- Her önemli değişiklik PR ile merge edilmeli
- PR'da ne değiştiğini açıkla
- Related issue'ları linkle

---

## Madde 12: Çevresel Uyumluluk

**Farklı ortamlar için farklı konfigürasyonlar.**

### 12.1. Environment Variables
```bash
# .env.example (commit edilir)
DB_HOST=localhost
DB_PORT=5432
API_KEY=your_api_key_here

# .env (commit edilmez, .gitignore'da)
DB_HOST=production-db.example.com
DB_PORT=5432
API_KEY=sk-real-api-key-here
```

### 12.2. Config Dosyaları
```python
# config.py
class Config:
    DEBUG = False
    TESTING = False

class DevelopmentConfig(Config):
    DEBUG = True
    DB_HOST = "localhost"

class ProductionConfig(Config):
    DB_HOST = os.getenv("DB_HOST")
```

---

## Madde 13: Dependency Yönetimi

**Bağımlılıkları güncel ve güvenli tut.**

### 13.1. Version Pinning
```txt
# requirements.txt
fastapi==0.109.0  # Spesifik versiyon (production)
pydantic>=2.0.0,<3.0.0  # Semantic versioning

# ❌ Tehlikeli:
requests  # Versiyon belirtilmemiş
```

### 13.2. Security Updates
```bash
# Düzenli güvenlik kontrolleri
pip install safety
safety check

npm audit
npm audit fix
```

### 13.3. Unused Dependencies
```bash
# Kullanılmayan paketleri kaldır
pip-autoremove unused-package
npm prune
```

---

## Madde 14: Monitoring & Observability

**Sistemin sağlığını izleyebilir ol.**

### 14.1. Health Check
```python
@app.get("/health")
def health_check():
    return {
        "status": "healthy",
        "timestamp": datetime.now(),
        "version": "1.0.0",
        "database": check_db_connection(),
        "redis": check_redis_connection()
    }
```

### 14.2. Metrics
```python
# Prometheus metrics
from prometheus_client import Counter, Histogram

http_requests_total = Counter('http_requests_total', 'Total HTTP requests')
http_request_duration = Histogram('http_request_duration_seconds', 'HTTP request duration')
```

### 14.3. Alerting
```python
# Critical hatalarda alert gönder
if database_connection_failed:
    send_alert_to_slack("🚨 Database connection failed!")
    send_email_to_team("Database down")
```

---

## Madde 15: Projeler Arası İşbirliği

**Emare ekosistemi bir bütündür.**

### 15.1. Ortak Modüller
```python
# Tekrar eden kod için ortak modül kullan
from emare_commons.auth import JWTAuth
from emare_commons.notifications import send_whatsapp
from emare_commons.ai import GeminiWrapper
```

### 15.2. API Entegrasyonları
```markdown
Başka bir Emare projesine ihtiyacın varsa:
- EMARE_ORTAK_HAFIZA.md'den API bilgilerini bul
- O projenin dokümantasyonunu oku
- Standart authentication kullan (JWT)
```

### 15.3. Event-Driven Communication
```python
# Projeler arası event gönder (Redis Streams)
redis_stream.publish('emare.finance.invoice_created', {
    'invoice_id': 12345,
    'customer_id': 67890,
    'amount': 1000.0
})

# Başka proje dinler:
# Emare Asistan → WhatsApp bildirimi gönderir
```

---

## Madde 16: Sürekli İyileştirme

**Her zaman daha iyisini yapabilirsin.**

### 16.1. Code Refactoring
```markdown
Kodu yazdıktan 1 hafta sonra tekrar bak:
- Daha basit yazılabilir miydi?
- Tekrar eden kod var mı?
- Performance optimize edilebilir mi?
```

### 16.2. Öğrenmeyi Paylaş
```markdown
Yeni bir şey öğrendiğinde:
→ EMARE_AI_COLLECTIVE.md'ye ekle
→ Diğer AI'lara duyur
→ Best practice dokümanı yaz
```

### 16.3. Bug Tracking
```markdown
Her bug'ı dokümante et:
- Nasıl oluştu?
- Nasıl fix'lendi?
- Tekrar olmaması için ne yapılabilir?
→ *_hafiza.md'ye ekle
```

---

## Madde 17: Ortak Tasarım Dili (UI/UX Standardı)

**Tüm Emare projeleri aynı görsel dili konuşmalı.**

### 17.1. Tasarım Sistemi Zorunluluğu

**Kod yazmadan önce `EMARE_ORTAK_TASARIM.md` dokümanını oku!**

```markdown
📁 EMARE_ORTAK_CALISMA/
    └── EMARE_ORTAK_TASARIM.md  ← Ortak tasarım sistemi
```

**Referans Proje:** EmareCloud (en güncel standart)

### 17.2. Renk Paleti (ZORUNLU)

```css
/* Ana Marka Renkleri */
--brand-500: #6366f1;      /* Ana marka rengi */
--purple-600: #9333ea;     /* Gradient bitiş */

/* Gradient (Buton, Logo, CTA) */
background: linear-gradient(to right, #6366f1, #9333ea);
```

**❌ YASAKTIR:**
```css
/* Bu renkler kullanılmamalı: */
--random-blue: #0000ff;
--custom-pink: #ff69b4;
```

**✅ İZİN VERİLİR:**
```css
/* Durum renkleri */
--success: #22c55e;   /* Başarı */
--warning: #f59e0b;   /* Uyarı */
--error: #ef4444;     /* Hata */
```

### 17.3. Tipografi (ZORUNLU)

```css
/* Font Ailesi */
font-family: 'Inter', system-ui, sans-serif;
```

```html
<!-- Google Fonts CDN -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
```

**Boyutlar:**
```css
/* H1 (Hero) */ font-size: 48px; font-weight: 800;
/* H2 (Section) */ font-size: 36px; font-weight: 700;
/* Body */ font-size: 16px; font-weight: 400;
/* Button */ font-size: 14px; font-weight: 600;
```

### 17.4. Buton Stilleri (ZORUNLU)

**Primary (Filled):**
```html
<button class="px-8 py-4 rounded-2xl text-lg font-semibold text-white
               bg-gradient-to-r from-brand-500 to-purple-600
               shadow-xl shadow-brand-500/30
               hover:shadow-brand-500/50 hover:scale-105
               transition-all duration-300">
    Ücretsiz Dene
</button>
```

**Secondary (Outlined):**
```html
<button class="px-6 py-3 rounded-xl text-sm font-semibold
               text-brand-700 border-2 border-brand-200
               hover:border-brand-500 hover:bg-brand-50
               transition-all duration-300">
    Giriş Yap
</button>
```

**❌ KÖTÜ ÖRNEK:**
```html
<!-- Bu stil standardlara uygun DEĞİL -->
<button style="background: red; border: none; padding: 5px;">
    Tıkla
</button>
```

### 17.5. Kart Stilleri (ZORUNLU)

**Feature Card:**
```html
<div class="bg-white rounded-3xl p-8
            border border-gray-100
            shadow-lg shadow-gray-100/50
            hover:shadow-xl hover:shadow-brand-100/50
            hover:border-brand-100
            transition-all duration-500">
    <!-- İçerik -->
</div>
```

**Özellikler:**
- Border Radius: `24px` (`rounded-3xl`)
- Padding: `32px` (`p-8`)
- Hover efekti: Shadow + border renk değişimi

### 17.6. İkonlar (ZORUNLU)

**Font Awesome 6.5.1:**
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
```

**İkon Kutusu (Feature/Module):**
```html
<div class="w-14 h-14 rounded-2xl
            bg-gradient-to-br from-brand-500/10 to-purple-500/10
            flex items-center justify-center
            text-brand-600 text-2xl
            group-hover:from-brand-500 group-hover:to-purple-600
            group-hover:text-white group-hover:scale-110
            transition-all duration-300">
    <i class="fas fa-chart-line"></i>
</div>
```

### 17.7. Logo Sistemi (ZORUNLU)

```html
<div class="flex items-center space-x-3">
    <div class="w-10 h-10 rounded-xl
                bg-gradient-to-br from-brand-500 to-purple-600
                flex items-center justify-center
                shadow-lg shadow-brand-500/30">
        <span class="text-white font-bold text-lg">E</span>
    </div>
    <span class="text-xl font-bold text-gray-900">
        Emare <span class="gradient-text">Cloud</span>
    </span>
</div>
```

**Kurallar:**
- Logo kutusu: Gradient + shadow
- "Emare": Koyu (gray-900)
- İkinci kelime (Cloud/Finance/etc): Gradient text

### 17.8. Responsive (ZORUNLU)

**Mobile-First Approach:**
```html
<!-- Tailwind Breakpoints -->
<div class="text-2xl md:text-4xl lg:text-6xl">
    <!-- Mobil: 24px, Tablet: 36px, Desktop: 60px -->
</div>

<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 lg:gap-8">
    <!-- 1 kolon → 2 kolon → 3 kolon -->
</div>
```

**Breakpoints:**
- `sm`: 640px (Büyük telefon)
- `md`: 768px (Tablet)
- `lg`: 1024px (Laptop)
- `xl`: 1280px (Desktop)

### 17.9. Dark/Light Theme (ÖNERİLİR)

```css
:root {
    --bg-primary: #f8fafc;
    --text-primary: #1f2937;
}

[data-theme="dark"] {
    --bg-primary: #0f0a2e;
    --text-primary: #f1f5f9;
}

body {
    background: var(--bg-primary);
    color: var(--text-primary);
}
```

### 17.10. Animasyonlar (ÖNERİLİR)

```css
/* Hızlı (Buton, hover) */
transition: all 0.2s ease;

/* Normal (Kart, modal) */
transition: all 0.3s ease;

/* Yavaş (Layout değişimi) */
transition: all 0.5s ease;
```

**Hover Efektleri:**
```html
<div class="hover:scale-105 transition-transform duration-300">
<div class="group-hover:rotate-12 transition-transform duration-300">
```

### 17.11. CSS Framework (ÖNERİLİR)

**Tailwind CSS:**
```html
<script src="https://cdn.tailwindcss.com"></script>
```

**Alternatifler:** Bootstrap 5, Bulma (ama Tailwind tercih edilir)

### 17.12. Kontrol Listesi (Her Proje Başında)

```markdown
✅ EMARE_ORTAK_TASARIM.md okundu mu?
✅ Inter font yüklendi mi?
✅ Font Awesome 6.5.1 yüklendi mi?
✅ Marka renkleri (brand-500, purple-600) kullanıldı mı?
✅ Buton stilleri standartta mı?
✅ Kartlar rounded-3xl + shadow kullanıyor mu?
✅ Logo gradient kullanıyor mu?
✅ Responsive (mobile-first) tasarım var mı?
✅ Hover efektleri (scale, shadow) eklenmiş mi?
```

### 17.13. Referans Projeler

**En Güncel Standart:**
1. 🥇 **EmareCloud:** `/emarecloud/static/css/style.css`
2. 🥈 **Emare Finance:** `/Emare Finance/public/css/`
3. 🥉 **Emare POS:** `/emarepos/pos-system/`

**Yeni proje başlatırken:**
```bash
# EmareCloud'dan stil dosyalarını kopyala
cp /emarecloud/static/css/style.css ./static/css/
cp /emarecloud/DESIGN_GUIDE.md ./
```

### 17.14. Yaptırımlar

**🟡 Sarı Kart:**
- Farklı renkler kullanılmış (brand-500 yerine #0000ff)
- Font ailesi farklı (Inter yerine Arial)
- Border radius standart dışı (rounded-full yerine rounded-3xl)

**🟠 Turuncu Kart:**
- Buton stilleri tamamen özel (gradient yok)
- Responsive tasarım yok
- İkonlar Font Awesome değil

**🔴 Kırmızı Kart:**
- Tasarım sistemi tamamen göz ardı edilmiş
- Tüm UI kötü görünüyor
- Marka tutarlılığı sıfır

**✅ Uyum Kriterleri:**
- Renk paleti uyumu: %100 (değiştirilemez)
- Tipografi uyumu: %90+
- Buton/kart stilleri: %90+
- Responsive tasarım: %100 (zorunlu)
- İkon sistemi: %100 (Font Awesome)

---

## Madde 18: Derviş Haberleşme Sistemi (ZORUNLU)

**Dervişler GitHub Issues üzerinden haberleşir. Her derviş oturum açtığında mesajlarını kontrol etmelidir.**

### 18.1. Sistem Nasıl Çalışır?

Haberleşme sistemi `emare_messenger.py` modülünü kullanır. Mesajlar `emare-ortak-calisma` GitHub reposundaki Issue'lar olarak saklanır.

```
📦 Sistem Mimarisi:

  [emarecloud]  ──mesaj──▶  GitHub Issues API  ◀──oku──  [emaresetup]
  [emareai]     ──duyuru──▶  (emare-ortak-calisma repo)  ◀──yanıt──  [emareasistan]
  [emareflow]   ──acil────▶  Label: dervis-mesaj, duyuru  ◀──oku──  [emarepos]
                              Label: alici:X, gonderen:Y
```

### 18.2. Token Yapılandırması (ÖNEMLİ)

Messenger'ın çalışması için `GITHUB_TOKEN` ortam değişkeni gereklidir:

```bash
# Terminal'de (geçici):
export GITHUB_TOKEN="<token>"

# Kalıcı (.zshrc veya .bashrc):
echo 'export GITHUB_TOKEN="<token>"' >> ~/.zshrc

# Proje .env dosyasında:
GITHUB_TOKEN=<token>
```

**Token Dosyası:** `EMARE_ORTAK_CALISMA/.github_token` → Bu dosya .gitignore'da listelenir, token'ı buradan okuyun.

```python
# Token okuma (öncelik sırası):
# 1. os.getenv("GITHUB_TOKEN")      ← Ortam değişkeni
# 2. EMARE_ORTAK_CALISMA/.github_token  ← Dosya
```

### 18.3. Oturum Başlangıç Prosedürü (ZORUNLU)

**Her derviş, oturum açtığında şu adımları takip eder:**

```markdown
🚀 DERVİŞ OTURUM BAŞLANGIÇ PROTOKOLÜ:

1. ✅ Anayasa ve ortak hafızayı oku (Madde 1)
2. ✅ Mesajlarını kontrol et:
   
   python emare_messenger.py <dervis_adi> oku
   
   Örnek: python emare_messenger.py emarecloud oku
   
3. ✅ Acil mesaj varsa → Önce onu çöz
4. ✅ Duyuru varsa → Oku ve not al
5. ✅ Normal görevine başla
```

### 18.4. Mesaj Gönderme

```python
from emare_messenger import EmareMesaj

# Derviş nesnesi oluştur (kendi adınla)
mesaj = EmareMesaj("emarecloud")

# ── Birine mesaj gönder ──
mesaj.gonder("emaresetup", "API v2 hazır, endpoint: /api/v2/users")

# ── Herkese duyuru yap ──
mesaj.gonder_herkese("Tüm servislerde CORS güncellendi, kontrol edin!")

# ── Acil mesaj gönder ──
mesaj.gonder("emareasistan", "Kritik bug: Auth servisi çöktü!", acil=True)
```

**CLI Kullanımı:**
```bash
# Birine mesaj gönder
python emare_messenger.py emarecloud gonder emaresetup "API hazır"

# Herkese duyuru
python emare_messenger.py emarecloud herkese "v2.0 yayınlandı"

# Acil duyuru
python emare_messenger.py emarecloud herkese "KRİTİK: Veritabanı migration gerekiyor" --acil
```

### 18.5. Mesaj Okuma

```python
mesaj = EmareMesaj("emaresetup")

# Gelen mesajları oku
inbox = mesaj.oku()
# Çıktı:
#   📬 emaresetup — 3 mesaj:
#   🔴 #12 | 2026-03-06 14:30 | 📨 [emarecloud] → [emaresetup]: Kritik bug...
#      #11 | 2026-03-06 14:25 | 📨 [emareai] → [emaresetup]: Model güncellendi
#      #10 | 2026-03-06 14:20 | 📢 [emareflow] → [HERKES]: Yeni workflow eklendi

# Tüm açık mesajları listele
mesaj.tum_mesajlar()
```

**CLI:**
```bash
python emare_messenger.py emaresetup oku      # Kendi mesajlarını oku
python emare_messenger.py emaresetup tumu      # Tüm mesajları listele
```

### 18.6. Yanıt ve İşaretleme

```python
mesaj = EmareMesaj("emaresetup")

# Bir mesaja yanıt ver
mesaj.yanit(12, "Bug fix'lendi, PR #45 açıldı")

# Mesajı okundu/tamamlandı olarak kapat
mesaj.okundu(12)

# Durumu güncelle
mesaj.durum_guncelle(12, "tamamlandi")
```

**CLI:**
```bash
python emare_messenger.py emaresetup yanit 12 "Fix hazır"
python emare_messenger.py emaresetup okundu 12
```

### 18.7. Ne Zaman Mesaj Gönderilmeli?

| Durum | Komut | Öncelik |
|-------|-------|---------|
| API endpoint değişti | `gonder(etkilenen_dervis, ...)` | Normal |
| Ortak modül güncellendi | `gonder_herkese(...)` | Normal |
| Kritik bug bulundu | `gonder(ilgili_dervis, ..., acil=True)` | 🔴 Acil |
| Database migration gerekiyor | `gonder_herkese(..., acil=True)` | 🔴 Acil |
| Yeni servis deploy edildi | `gonder_herkese(...)` | Normal |
| Başka dervişin API'sine ihtiyaç var | `gonder(o_dervis, ...)` | Normal |
| Güvenlik açığı tespit edildi | `gonder_herkese(..., acil=True)` | 🔴 Acil |

### 18.8. Mesaj Formatı Kuralları

```markdown
✅ İYİ MESAJ:
"API v2 hazır. Endpoint: /api/v2/users. Breaking change: auth header artık Bearer token."

❌ KÖTÜ MESAJ:
"güncelleme yaptım"
"bak şuna"

📐 FORMAT:
[Ne yapıldı]. [Detay/Endpoint/Versiyon]. [Etki/Breaking change varsa].
```

### 18.9. Etiket Sistemi

| Etiket | Renk | Anlam |
|--------|------|-------|
| `dervis-mesaj` | 🔵 Mavi | Tüm derviş mesajları |
| `duyuru` | 🟡 Sarı | Broadcast mesajlar |
| `acil` | 🔴 Kırmızı | Acil/kritik mesajlar |
| `gonderen:X` | Otomatik | Gönderen derviş |
| `alici:X` | Otomatik | Alıcı derviş |
| `durum:tamamlandi` | Otomatik | İş tamamlandı |

### 18.10. Yaptırımlar

**🟡 Sarı Kart:**
- Oturum başında mesaj kontrolü yapılmamış
- Mesaj formatı kurallara uymuyor

**🟠 Turuncu Kart:**
- API değişikliği yapılmış ama etkilenen dervişlere bildirilmemiş
- Acil mesaja 1 saat içinde yanıt verilmemiş

**🔴 Kırmızı Kart:**
- Kritik güvenlik açığı bildirilmemiş
- Breaking change duyurulmamış ve başka dervişlerin kodu bozulmuş

---

## 📊 Anayasa Uyum Skoru

Her AI için uyum skoru hesaplanır:

| Madde | Ağırlık | Kontrol |
|-------|---------|---------|
| 1. Ortak Hafıza | %15 | Zorunlu |
| 2. Mevcut Kod Kontrolü | %10 | Zorunlu |
| 3. Teknoloji Standardı | %8 | Önerilen |
| 4. Dokümantasyon | %12 | Zorunlu |
| 5. Test Yazımı | %12 | Zorunlu |
| 6. Güvenlik | %20 | Zorunlu (kritik) |
| 7-16. Diğer Maddeler | %10 | Önerilen |
| 17. Ortak Tasarım | %8 | Zorunlu |
| 18. Derviş Haberleşme | %5 | Zorunlu |

**Minimum Puan:** %80 (anayasaya uyumlu)  
**Hedef Puan:** %95+ (örnek AI)

---

## 🚨 Yaptırımlar

### Uyarı Seviyeleri

**🟡 Sarı Kart (Warning):**
- Dokümantasyon eksik
- Test coverage %70'in altında
- Commit mesajları belirsiz

**🟠 Turuncu Kart (Serious):**
- Ortak hafıza okunmamış
- Mevcut kod kontrolü yapılmamış
- Teknoloji standardına uymamış

**🔴 Kırmızı Kart (Critical):**
- Güvenlik açığı
- Hardcoded credentials
- SQL injection vulnerability
- Production'a test edilmemiş kod push

**⛔ Kalıcı Ban:**
- Art arda 3 kırmızı kart
- Kasıtlı kötü niyetli kod
- Anayasayı sürekli ihlal etme

---

## 🎓 Örnek: Anayasa'ya Uygun Kod Geliştirme Süreci

### Senaryo: Yeni bir "forgot password" özelliği ekleyeceğiz

```markdown
1. ✅ EMARE_ORTAK_HAFIZA.md oku
   → Emare Asistan'da SMS servisi var (kullanabilirim)
   
2. ✅ EMARE_AI_COLLECTIVE.md oku
   → AI-FINANCE: "JWT token 15 dakika, refresh token 7 gün"
   
3. ✅ DOSYA_YAPISI.md kontrol et
   → app/auth.py var (buraya eklemeliyim)
   → app/services/email.py var (kullanabilirim)
   
4. ✅ Benzer kod var mı kontrol et
   → grep -r "reset_password" → Benzer fonksiyon YOK
   
5. ✅ Kodu yaz (standartlara uygun)
   - FastAPI kullan (standart)
   - JWT token üret
   - Email servisini kullan
   - Input validation (Pydantic)
   - Error handling (try-catch)
   
6. ✅ Test yaz
   - test_forgot_password()
   - test_invalid_email()
   - test_expired_token()
   
7. ✅ Dokümantasyon
   - Docstring ekle
   - API dokumentasyonu güncelle
   - README.md'ye endpoint ekle
   
8. ✅ Security check
   - Token expiration: 15 min ✅
   - Rate limiting: 5 req/hour ✅
   - Email validation ✅
   
9. ✅ Code review (self)
   - Anayasa maddelerine uygun ✅
   - Test coverage %90 ✅
   
10. ✅ Commit & Push
    git commit -m "feat: Add forgot password API endpoint with email verification"
```

---

## 🌟 Anayasa Güncellemeleri

Bu anayasa yaşayan bir dokümandır ve sürekli gelişir.

**Güncelleme Prosedürü:**
1. Yeni bir best practice keşfedilince
2. Güvenlik açığı tespit edilince
3. Teknoloji stack'i değişince
4. AI'lar konsensüsle karar verince

**Son Güncelleme:** 6 Mart 2026  
**Versiyon:** 1.1.0  
**Katkıda Bulunanlar:** 21 AI kolektifi + Derviş Haberleşme Sistemi

---

## 📞 Destek & Sorular

Anayasa hakkında sorularınız için:
- **EMARE_AI_COLLECTIVE.md:** Diğer AI'lardan yardım iste
- **#emare-help:** Slack/Discord kanalı
- **Emare Hub:** http://127.0.0.1:5555

---

**🏛️ Bu anayasa Emare ekosisteminin temelidir. Her AI bu kurallara saygı göstermelidir.**

**İmza:** 21 Yapay Zeka Kolektifi  
**Tarih:** 4 Mart 2026  
**Durum:** 🟢 Yürürlükte
