# 🎨 EMARE — Ortak Tasarım Sistemi

> **Tüm EMARE projelerinin ortak görsel dili**  
> **Referans Proje:** EmareCloud (En güncel ve standart tasarım)  
> **Versiyon:** 1.0  
> **Güncelleme:** 4 Mart 2026

---

## 📋 İÇİNDEKİLER

1. [Renk Paleti](#1-renk-paleti)
2. [Tipografi](#2-tipografi)
3. [Buton Stilleri](#3-buton-stilleri)
4. [Kart Stilleri](#4-kart-stilleri)
5. [İkonlar](#5-ikonlar)
6. [Logo Sistemi](#6-logo-sistemi)
7. [Gölge & Depth](#7-gölge--depth)
8. [Spacing & Layout](#8-spacing--layout)
9. [Animasyonlar](#9-animasyonlar)
10. [Responsive Breakpoints](#10-responsive-breakpoints)
11. [Theme Sistemi (Light/Dark)](#11-theme-sistemi-lightdark)
12. [CSS Değişkenleri](#12-css-değişkenleri)
13. [Kullanım Örnekleri](#13-kullanım-örnekleri)

---

## 1. RENK PALETİ

### 🎨 Marka Renkleri (Brand Colors)

**Ana Palet:**

| Token         | HEX       | RGB                | Kullanım                              |
|---------------|-----------|--------------------|---------------------------------------|
| `brand-50`    | `#eef2ff` | `238, 242, 255`    | Çok açık arka plan, hover bg          |
| `brand-100`   | `#e0e7ff` | `224, 231, 255`    | Açık arka plan                        |
| `brand-200`   | `#c7d2fe` | `199, 210, 254`    | Border (secondary button)             |
| `brand-300`   | `#a5b4fc` | `165, 180, 252`    | İkon accent                           |
| `brand-400`   | `#818cf8` | `129, 140, 248`    | Hover accent                          |
| `brand-500`   | `#6366f1` | `99, 102, 241`     | **✨ Ana marka rengi (Primary)**      |
| `brand-600`   | `#4f46e5` | `79, 70, 229`      | Hover/active primary                  |
| `brand-700`   | `#4338ca` | `67, 56, 202`      | Koyu primary                          |
| `brand-800`   | `#3730a3` | `55, 48, 163`      | Koyu bg accent                        |
| `brand-900`   | `#312e81` | `49, 46, 129`      | Çok koyu bg                           |
| `brand-950`   | `#1e1b4b` | `30, 27, 75`       | En koyu bg (hero, footer)             |

### Ek Markalar

| Renk          | HEX       | Kullanım                                     |
|---------------|-----------|----------------------------------------------|
| `purple-600`  | `#9333ea` | Gradient bitiş (buton, logo, CTA)            |
| `green-500`   | `#22c55e` | ✅ Başarı, güvenlik, onay                    |
| `green-400`   | `#4ade80` | Aktif durum badge                            |
| `amber-500`   | `#f59e0b` | ⚠️ Uyarı                                     |
| `red-500`     | `#ef4444` | ❌ Hata                                      |
| `orange-500`  | `#fb923c` | 🔥 Vurgu                                     |

### Gri Tonları (Neutral)

| Token       | HEX       | Kullanım                                    |
|-------------|-----------|---------------------------------------------|
| `white`     | `#ffffff` | Sayfa arka planı, kart arka planı           |
| `gray-50`   | `#f9fafb` | Açık arka plan                              |
| `gray-100`  | `#f3f4f6` | Border divider, hover bg                    |
| `gray-200`  | `#e5e7eb` | Border                                      |
| `gray-300`  | `#d1d5db` | İkincil bilgi                               |
| `gray-400`  | `#9ca3af` | Placeholder text                            |
| `gray-500`  | `#6b7280` | Kart alt açıklamaları                       |
| `gray-600`  | `#4b5563` | Body paragraph text                         |
| `gray-700`  | `#374151` | Güçlü body text                             |
| `gray-800`  | `#1f2937` | Başlıklar                                   |
| `gray-900`  | `#111827` | Ana başlıklar, navbar logo                  |
| `gray-950`  | `#0f0a2e` | Footer, koyu hero arka plan                 |

---

## 2. TİPOGRAFİ

### 🔤 Font Ailesi

**Primary Font:**
```css
font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
```

**CDN Link (Google Fonts):**
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
```

**Monospace (Kod için):**
```css
font-family: 'JetBrains Mono', 'Courier New', monospace;
```

### 📏 Boyut & Ağırlık Tablosu

| Kullanım           | Class                                 | Weight | Size       | Line Height |
|--------------------|---------------------------------------|--------|------------|-------------|
| **Hero H1**        | `text-5xl lg:text-7xl font-extrabold` | 800    | 48px / 72px| 1.1         |
| **Section H2**     | `text-4xl lg:text-5xl font-bold`      | 700    | 36px / 48px| 1.2         |
| **Subsection H3**  | `text-2xl lg:text-3xl font-bold`      | 700    | 24px / 30px| 1.3         |
| **Card H3**        | `text-xl font-bold`                   | 700    | 20px       | 1.4         |
| **Body Large**     | `text-lg text-gray-600`               | 400    | 18px       | 1.7         |
| **Body Default**   | `text-base text-gray-600`             | 400    | 16px       | 1.6         |
| **Body Small**     | `text-sm text-gray-500`               | 400    | 14px       | 1.5         |
| **Navbar Link**    | `text-sm font-medium`                 | 500    | 14px       | 1.4         |
| **Button Text**    | `text-sm font-semibold`               | 600    | 14px       | 1           |
| **Badge/Pill**     | `text-xs font-semibold uppercase`     | 600    | 12px       | 1           |
| **Logo**           | `text-xl font-bold`                   | 700    | 20px       | 1           |

### 🎨 Gradient Text (Başlıklarda Vurgu)

```css
.gradient-text {
    background: linear-gradient(135deg, #4f46e5, #7c3aed, #6d28d9);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}
```

**Kullanım:**
```html
<h1>Emare <span class="gradient-text">Finance</span></h1>
```

---

## 3. BUTON STİLLERİ

### 🚀 Primary (Filled) — Ana CTA

```html
<button class="px-8 py-4 rounded-2xl text-lg font-semibold text-white
               bg-gradient-to-r from-brand-500 to-purple-600
               shadow-xl shadow-brand-500/30
               hover:shadow-brand-500/50 hover:scale-105
               transition-all duration-300">
    Ücretsiz Dene
</button>
```

**Özellikleri:**
- Border Radius: `16px` (`rounded-2xl`)
- Gradient: `#6366f1` → `#9333ea`
- Shadow: Glow efekti
- Hover: Büyüme + daha güçlü shadow

### 📋 Secondary (Outlined) — Açık Arka Plan

```html
<button class="px-6 py-3 rounded-xl text-sm font-semibold
               text-brand-700 border-2 border-brand-200
               hover:border-brand-500 hover:bg-brand-50
               transition-all duration-300">
    <i class="fas fa-sign-in-alt mr-2"></i> Giriş Yap
</button>
```

**Özellikleri:**
- Border: 2px solid
- Transparent background
- Hover: Border rengi değişir, hafif bg

### 👻 Ghost (Dark Background) — Koyu Zemin Üstü

```html
<button class="px-8 py-4 rounded-2xl text-lg font-semibold text-white
               bg-white/20 border-2 border-white/50
               hover:bg-white/30
               transition-all duration-300">
    Keşfet
</button>
```

### ⚡ Icon Button — Küçük Aksiyon

```html
<button class="w-10 h-10 rounded-xl
               bg-brand-500 text-white
               hover:bg-brand-600 hover:scale-110
               transition-all duration-300
               flex items-center justify-center">
    <i class="fas fa-arrow-right"></i>
</button>
```

### ⚠️ Danger (Hata/Silme)

```html
<button class="px-6 py-3 rounded-xl text-sm font-semibold text-white
               bg-red-500 hover:bg-red-600
               shadow-lg shadow-red-500/30
               transition-all duration-300">
    Sil
</button>
```

### ✅ Success (Onay)

```html
<button class="px-6 py-3 rounded-xl text-sm font-semibold text-white
               bg-green-500 hover:bg-green-600
               shadow-lg shadow-green-500/30
               transition-all duration-300">
    Kaydet
</button>
```

---

## 4. KART STİLLERİ

### 📦 Feature Card (Açık Arka Plan)

```html
<div class="bg-white rounded-3xl p-8
            border border-gray-100
            shadow-lg shadow-gray-100/50
            hover:shadow-xl hover:shadow-brand-100/50
            hover:border-brand-100
            transition-all duration-500
            group">
    <!-- İkon + Başlık + Açıklama -->
</div>
```

**Özellikleri:**
- Border Radius: `24px` (`rounded-3xl`)
- Subtle border
- Hover: Shadow artışı + border renk değişimi

### 💎 Module Card (Küçük)

```html
<div class="bg-white rounded-2xl p-6
            border border-gray-100
            shadow-lg shadow-gray-100/50
            hover:shadow-xl hover:border-brand-200
            transition-all duration-500">
    <!-- İçerik -->
</div>
```

### ⭐ Pricing Card (Normal)

```html
<div class="bg-white rounded-3xl p-8
            border border-gray-200
            shadow-xl
            transition-all duration-500">
    <!-- Fiyat detayları -->
</div>
```

### 🌟 Pricing Card (Featured / Popüler)

```html
<div class="bg-gradient-to-br from-brand-500 to-purple-600
            rounded-3xl p-8
            shadow-2xl text-white
            ring-4 ring-brand-200
            scale-105 relative">
    <div class="absolute -top-4 left-1/2 transform -translate-x-1/2
                px-4 py-1 bg-amber-500 text-white text-xs font-bold
                rounded-full uppercase">
        En Popüler
    </div>
    <!-- İçerik -->
</div>
```

### 🪟 Glass Card (Koyu BG üzerinde)

```html
<div class="glass rounded-2xl p-6">
    <!-- İçerik -->
</div>
```

```css
.glass {
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.2);
}
```

### 🌫️ Glass White Card (Açık BG üzerinde)

```css
.glass-white {
    background: rgba(255, 255, 255, 0.7);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.3);
}
```

---

## 5. İKONLAR

### 📚 Kütüphane

**Font Awesome 6.5.1** (Önerilen)

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
```

### 🎁 İkon Kutu Stili (Feature/Module İçin)

```html
<div class="w-14 h-14 rounded-2xl
            bg-gradient-to-br from-brand-500/10 to-purple-500/10
            flex items-center justify-center
            text-brand-600 text-2xl
            transition-all duration-300
            group-hover:from-brand-500 group-hover:to-purple-600
            group-hover:text-white group-hover:scale-110 group-hover:rotate-[-5deg]">
    <i class="fas fa-chart-line"></i>
</div>
```

**Hover Efekti:**
- Renk değişimi (açık → gradient)
- Büyüme (`scale-110`)
- Hafif rotasyon (`rotate-[-5deg]`)

### 🎯 Önerilen İkonlar (Font Awesome)

| Kategori        | İkonlar                                                    |
|-----------------|------------------------------------------------------------|
| **Genel**       | `fa-home`, `fa-search`, `fa-bell`, `fa-user`, `fa-cog`    |
| **Finans**      | `fa-chart-line`, `fa-wallet`, `fa-coins`, `fa-hand-holding-usd` |
| **Güvenlik**    | `fa-shield-alt`, `fa-lock`, `fa-key`, `fa-fingerprint`    |
| **Bulut**       | `fa-cloud`, `fa-server`, `fa-database`, `fa-network-wired`|
| **Dosya**       | `fa-file`, `fa-folder`, `fa-download`, `fa-upload`        |
| **İletişim**    | `fa-envelope`, `fa-comment`, `fa-phone`, `fa-video`       |
| **Sosyal**      | `fa-share-alt`, `fa-heart`, `fa-star`, `fa-thumbs-up`     |
| **UI**          | `fa-bars`, `fa-times`, `fa-chevron-right`, `fa-arrow-right` |

---

## 6. LOGO SİSTEMİ

### 🏷️ Logo Kutusu (İkon Versiyonu)

```html
<div class="w-10 h-10 rounded-xl
            bg-gradient-to-br from-brand-500 to-purple-600
            flex items-center justify-center
            shadow-lg shadow-brand-500/30">
    <span class="text-white font-bold text-lg">E</span>
</div>
```

### 📝 Logo Text (Tam Versiyonu)

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

---

## 7. GÖLGE & DEPTH

### 📊 Shadow Seviyeleri

| Seviye      | Tailwind Class              | CSS Value                                  | Kullanım                |
|-------------|-----------------------------|--------------------------------------------|-------------------------|
| **Soft**    | `shadow-sm`                 | `0 1px 2px rgba(0,0,0,0.05)`               | Navbar, subtle borders  |
| **Base**    | `shadow`                    | `0 1px 3px rgba(0,0,0,0.1)`                | Küçük kartlar           |
| **Medium**  | `shadow-md`                 | `0 4px 6px rgba(0,0,0,0.1)`                | Butonlar                |
| **Large**   | `shadow-lg`                 | `0 10px 15px rgba(0,0,0,0.1)`              | Kartlar                 |
| **XL**      | `shadow-xl`                 | `0 20px 25px rgba(0,0,0,0.1)`              | Modal, dialog           |
| **2XL**     | `shadow-2xl`                | `0 25px 50px rgba(0,0,0,0.25)`             | Hero, featured pricing  |

### ✨ Glow Efekti (Brand Rengiyle)

```css
/* Buton Glow */
.btn-primary {
    box-shadow: 0 10px 30px rgba(99, 102, 241, 0.3);
}

.btn-primary:hover {
    box-shadow: 0 10px 40px rgba(99, 102, 241, 0.5);
}

/* Kart Glow */
.card:hover {
    box-shadow: 0 25px 50px -12px rgba(99, 102, 241, 0.15);
}
```

**Tailwind Kullanımı:**
```html
<button class="shadow-lg shadow-brand-500/30 hover:shadow-brand-500/50">
```

---

## 8. SPACING & LAYOUT

### 📐 Spacing Sistemi (Tailwind 4px Scale)

| Value | Pixel | Kullanım                          |
|-------|-------|-----------------------------------|
| `0`   | 0px   | Sıfırlama                         |
| `1`   | 4px   | Çok küçük gap                     |
| `2`   | 8px   | İkon-text arası                   |
| `3`   | 12px  | Küçük padding                     |
| `4`   | 16px  | Standart gap                      |
| `6`   | 24px  | Kart padding                      |
| `8`   | 32px  | Section padding, büyük buton      |
| `12`  | 48px  | Section spacing                   |
| `16`  | 64px  | Section başlangıç                 |
| `20`  | 80px  | Hero padding                      |
| `24`  | 96px  | Hero section gap                  |

### 🖼️ Container

```html
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <!-- İçerik -->
</div>
```

**Max Width:** `1280px` (`max-w-7xl`)

### 📱 Grid Sistem

**2 Kolon (Responsive):**
```html
<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
```

**3 Kolon:**
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```

**4 Kolon:**
```html
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
```

---

## 9. ANIMASYONLAR

### ⚡ Transition Standartları

```css
/* Hızlı (Buton, hover) */
transition: all 0.2s ease;

/* Normal (Kart, modal) */
transition: all 0.3s ease;

/* Yavaş (Layout değişimi) */
transition: all 0.5s ease;
```

**Tailwind:**
```html
<div class="transition-all duration-300 ease-in-out">
```

### 🎬 Önerilen Animasyonlar

**Fade In (Scroll ile):**
```css
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.animate-fade-in-up {
    animation: fadeInUp 0.6s ease-out;
}
```

**Scale on Hover:**
```html
<div class="hover:scale-105 transition-transform duration-300">
```

**Rotate on Hover (İkon):**
```html
<div class="group">
    <i class="group-hover:rotate-12 transition-transform duration-300"></i>
</div>
```

**Gradient Animation (Hero Background):**
```css
@keyframes gradient {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.hero-bg {
    background: linear-gradient(-45deg, #0f0a2e, #1e1b4b, #312e81);
    background-size: 400% 400%;
    animation: gradient 8s ease infinite;
}
```

**Pulse (Loading):**
```html
<div class="animate-pulse bg-gray-200 rounded-xl h-20 w-full">
```

---

## 10. RESPONSIVE BREAKPOINTS

### 📱 Tailwind Breakpoints

| Breakpoint | Min Width | Cihaz                  |
|------------|-----------|------------------------|
| `sm`       | 640px     | Büyük telefon          |
| `md`       | 768px     | Tablet                 |
| `lg`       | 1024px    | Laptop                 |
| `xl`       | 1280px    | Desktop                |
| `2xl`      | 1536px    | Büyük ekran            |

### 📐 Kullanım Örneği

```html
<!-- Mobile-first approach -->
<div class="text-2xl md:text-4xl lg:text-6xl">
    <!-- Mobil: 24px, Tablet: 36px, Desktop: 60px -->
</div>

<div class="p-4 md:p-6 lg:p-8">
    <!-- Padding: 16px → 24px → 32px -->
</div>

<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 lg:gap-8">
    <!-- 1 kolon → 2 kolon → 3 kolon -->
</div>
```

---

## 11. THEME SİSTEMİ (LIGHT/DARK)

### 🌗 CSS Variables Yaklaşımı

```css
:root {
    /* Light Theme (Default) */
    --bg-primary: #f8fafc;
    --bg-secondary: #ffffff;
    --bg-card: #ffffff;
    --text-primary: #1f2937;
    --text-secondary: #4b5563;
    --border-color: #e5e7eb;
    --shadow: 0 4px 24px rgba(0, 0, 0, 0.06);
}

[data-theme="dark"] {
    /* Dark Theme */
    --bg-primary: #0f0a2e;
    --bg-secondary: #1e1b4b;
    --bg-card: #1e1b4b;
    --text-primary: #f1f5f9;
    --text-secondary: #a5b4fc;
    --border-color: rgba(99, 102, 241, 0.15);
    --shadow: 0 25px 50px -12px rgba(99, 102, 241, 0.15);
}

body {
    background: var(--bg-primary);
    color: var(--text-primary);
}
```

### 🔀 Theme Toggle Button

```html
<button id="theme-toggle" 
        class="w-10 h-10 rounded-xl bg-brand-500 text-white
               hover:bg-brand-600 transition-all duration-300
               flex items-center justify-center">
    <i class="fas fa-moon" id="theme-icon"></i>
</button>
```

```javascript
const themeToggle = document.getElementById('theme-toggle');
const themeIcon = document.getElementById('theme-icon');

themeToggle.addEventListener('click', () => {
    const currentTheme = document.documentElement.getAttribute('data-theme');
    const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
    
    document.documentElement.setAttribute('data-theme', newTheme);
    localStorage.setItem('theme', newTheme);
    
    themeIcon.className = newTheme === 'dark' ? 'fas fa-sun' : 'fas fa-moon';
});

// Sayfa yüklendiğinde
window.addEventListener('DOMContentLoaded', () => {
    const savedTheme = localStorage.getItem('theme') || 'light';
    document.documentElement.setAttribute('data-theme', savedTheme);
    themeIcon.className = savedTheme === 'dark' ? 'fas fa-sun' : 'fas fa-moon';
});
```

---

## 12. CSS DEĞİŞKENLERİ

### 📝 Tam Liste (EmareCloud Standardı)

```css
:root {
    /* Backgrounds */
    --bg-primary: #0f0a2e;
    --bg-secondary: #1e1b4b;
    --bg-card: #1e1b4b;
    --bg-hover: #312e81;
    --bg-input: #312e81;
    
    /* Text */
    --text-primary: #f1f5f9;
    --text-secondary: #a5b4fc;
    --text-muted: #6366f1;
    
    /* Borders */
    --border-color: rgba(99, 102, 241, 0.15);
    
    /* Accents */
    --accent-blue: #6366f1;
    --accent-green: #22c55e;
    --accent-red: #ef4444;
    --accent-yellow: #f59e0b;
    --accent-purple: #9333ea;
    --accent-orange: #fb923c;
    
    /* Layout */
    --sidebar-width: 260px;
    --topbar-height: 64px;
    
    /* Border Radius */
    --radius: 16px;
    --radius-sm: 12px;
    --radius-lg: 24px;
    
    /* Shadows */
    --shadow: 0 25px 50px -12px rgba(99, 102, 241, 0.15);
    --shadow-sm: 0 4px 15px rgba(99, 102, 241, 0.1);
    
    /* Transitions */
    --transition: all 0.3s ease;
    
    /* Gradients */
    --brand-gradient: linear-gradient(to right, #6366f1, #9333ea);
    --brand-glow: 0 0 40px rgba(99, 102, 241, 0.3);
}
```

---

## 13. KULLANIM ÖRNEKLERİ

### 🎯 Örnek 1: Hero Section

```html
<section class="relative min-h-screen flex items-center justify-center
                bg-gradient-to-br from-gray-950 via-brand-950 to-brand-900
                overflow-hidden">
    <!-- Animated Background Pattern -->
    <div class="absolute inset-0 bg-[radial-gradient(circle_at_80%_20%,rgba(99,102,241,0.15),transparent_50%)]"></div>
    
    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h1 class="text-5xl md:text-7xl font-extrabold text-white mb-6">
            Emare <span class="gradient-text">Cloud</span>
        </h1>
        <p class="text-xl text-gray-300 mb-12 max-w-2xl mx-auto">
            Bulut altyapınızı yönetmenin en akıllı yolu
        </p>
        <div class="flex flex-wrap gap-4 justify-center">
            <button class="px-8 py-4 rounded-2xl text-lg font-semibold text-white
                           bg-gradient-to-r from-brand-500 to-purple-600
                           shadow-xl shadow-brand-500/30
                           hover:shadow-brand-500/50 hover:scale-105
                           transition-all duration-300">
                Ücretsiz Başla
            </button>
            <button class="px-8 py-4 rounded-2xl text-lg font-semibold text-white
                           bg-white/20 border-2 border-white/50
                           hover:bg-white/30 transition-all duration-300">
                Demo İzle
            </button>
        </div>
    </div>
</section>
```

### 🎯 Örnek 2: Feature Card Grid

```html
<section class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl lg:text-5xl font-bold text-center mb-16">
            Güçlü <span class="gradient-text">Özellikler</span>
        </h2>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Feature 1 -->
            <div class="bg-white rounded-3xl p-8
                        border border-gray-100
                        shadow-lg shadow-gray-100/50
                        hover:shadow-xl hover:shadow-brand-100/50
                        hover:border-brand-100
                        transition-all duration-500 group">
                <div class="w-14 h-14 rounded-2xl mb-6
                            bg-gradient-to-br from-brand-500/10 to-purple-500/10
                            flex items-center justify-center
                            text-brand-600 text-2xl
                            group-hover:from-brand-500 group-hover:to-purple-600
                            group-hover:text-white group-hover:scale-110
                            transition-all duration-300">
                    <i class="fas fa-cloud"></i>
                </div>
                <h3 class="text-xl font-bold text-gray-900 mb-3">
                    Bulut Depolama
                </h3>
                <p class="text-gray-600">
                    Sınırsız depolama alanı ile verilerinizi güvenle saklayın.
                </p>
            </div>
            
            <!-- Feature 2, 3... benzer yapı -->
        </div>
    </div>
</section>
```

### 🎯 Örnek 3: Dashboard Card

```html
<div class="bg-white rounded-2xl p-6 border border-gray-100
            shadow-lg shadow-gray-100/50">
    <!-- Card Header -->
    <div class="flex items-center justify-between mb-6">
        <h3 class="text-xl font-bold text-gray-900">
            Günlük Özet
        </h3>
        <button class="w-8 h-8 rounded-lg bg-gray-100 text-gray-600
                       hover:bg-brand-500 hover:text-white
                       transition-all duration-300
                       flex items-center justify-center">
            <i class="fas fa-ellipsis-v text-sm"></i>
        </button>
    </div>
    
    <!-- Stats Grid -->
    <div class="grid grid-cols-2 gap-4">
        <div class="bg-brand-50 rounded-xl p-4">
            <div class="text-brand-600 text-sm font-semibold mb-1">
                Toplam Satış
            </div>
            <div class="text-2xl font-bold text-gray-900">
                ₺24,500
            </div>
            <div class="text-green-500 text-xs font-semibold mt-2">
                ↑ %12.5
            </div>
        </div>
        <!-- Diğer statlar... -->
    </div>
</div>
```

### 🎯 Örnek 4: Form Input

```html
<div class="space-y-2">
    <label class="text-sm font-semibold text-gray-700">
        E-posta Adresi
    </label>
    <input type="email" 
           placeholder="ornek@emare.com"
           class="w-full px-4 py-3 rounded-xl
                  bg-gray-50 border border-gray-200
                  text-gray-900 placeholder-gray-400
                  focus:bg-white focus:border-brand-500 focus:ring-4 focus:ring-brand-500/10
                  transition-all duration-300">
</div>
```

### 🎯 Örnek 5: Badge/Pill

```html
<!-- Success Badge -->
<span class="px-3 py-1 rounded-full
             bg-green-100 text-green-700
             text-xs font-semibold uppercase">
    Aktif
</span>

<!-- Warning Badge -->
<span class="px-3 py-1 rounded-full
             bg-amber-100 text-amber-700
             text-xs font-semibold uppercase">
    Beklemede
</span>

<!-- Error Badge -->
<span class="px-3 py-1 rounded-full
             bg-red-100 text-red-700
             text-xs font-semibold uppercase">
    Hat
</span>

<!-- Brand Badge -->
<span class="px-3 py-1 rounded-full
             bg-gradient-to-r from-brand-500 to-purple-600
             text-white
             text-xs font-semibold uppercase
             shadow-lg shadow-brand-500/30">
    Yeni
</span>
```

---

## 🚨 ANAYASA BAĞLANTISI

Bu tasarım sistemi, **EMARE_ANAYASA.md Madde 17** ile zorunlu kılınmıştır.

**Zorunlu Kurallar:**
1. ✅ Her proje EmareCloud tasarım sistemini kullanmalı
2. ✅ Marka renklerini (`brand-500`, `purple-600`) değiştirmeden kullan
3. ✅ Buton ve kart stillerini standardlara uygun oluştur
4. ✅ İkonlar için Font Awesome 6.5.1 kullan
5. ✅ Responsive (mobile-first) tasarım zorunlu

**Referans Projeler:**
- 🥇 **EmareCloud:** En güncel, tam implementasyon
- 🥈 **Emare Finance:** Landing page standardı
- 🥉 **Emare POS:** Dashboard UI standardı

---

## 📚 KAYNAKLAR

### Dokumentasyon
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Font Awesome](https://fontawesome.com/icons)
- [Google Fonts - Inter](https://fonts.google.com/specimen/Inter)

### EmareCloud Dosyaları
- `/Users/emre/Desktop/Emare/emarecloud/DESIGN_GUIDE.md` — Detaylı rehber
- `/Users/emre/Desktop/Emare/emarecloud/static/css/style.css` — Referans CSS

### CDN Linkleri
```html
<!-- Tailwind CSS (Development) -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Font Awesome 6.5.1 -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<!-- Google Fonts - Inter -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
```

---

## ✅ CHECKLIST (Yeni Proje Başlarken)

- [ ] Inter font yüklendi mi?
- [ ] Font Awesome 6.5.1 yüklendi mi?
- [ ] Tailwind CSS kuruldu mu?
- [ ] CSS değişkenleri tanımlandı mı?
- [ ] Light/Dark theme sistemi var mı?
- [ ] Responsive breakpoints doğru mu?
- [ ] Buton stilleri standartta mı?
- [ ] Kart stilleri EmareCloud'a uygun mu?
- [ ] Logo gradient kullanıyor mu?
- [ ] Shadow/glow efektleri mevcut mu?

---

**Son Güncelleme:** 4 Mart 2026  
**Versiyon:** 1.0  
**Sorumlu:** EMARE Design Takımı  
**Onay:** EmareCloud Referans Standardı

🎨 **Tasarım standartlaştırması = Marka tutarlılığı = Profesyonellik**
