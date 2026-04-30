# 📊 Kelime Bulutu Atölyesi

> ÖVA506 Nitel Veri Analizi Teknikleri dersi kapsamında geliştirilmiş, Türkçe metinler için ücretsiz kelime bulutu görselleştirme aracı.

**Geliştiren:** Mikael KARA  
**Ders:** ÖVA506 Nitel Veri Analizi Teknikleri  
**Danışman:** Doç. Dr. Hakan Kılınç  
**Kurum:** Anadolu Üniversitesi — Ölçme ve Veri Analitiği Yüksek Lisans Programı

---

## 🔗 Canlı Demo

👉 **[Uygulamayı Aç](https://mikaelkara.github.io/Nitel-Veri-Analizi-Teknikleri/)**

> *(GitHub Pages deploy ettikten sonra bu bağlantıyı kullanıcı adınızla güncelleyin)*

---

## ✨ Özellikler

### Veri Girişi
- **Tek metin** — paragraf yapıştır, anında görselleştir
- **Etiketli bloklar** — Atlas.ti benzeri çok kodlu sistem; her metin bloğuna etiket ver, etiketler arasında geçiş yap
- **.txt dosya yükleme** — metin dosyasını seç veya sürükle-bırak

### Türkçe Dil Desteği
- 380+ kelimelik kapsamlı **Türkçe stop word listesi** (bağlaç, edat, zamir, yardımcı fiil, çekim ekleri)
- Stop word filtresini açma/kapama toggle'ı
- Kullanıcı tanımlı ek hariç tutma listesi (virgül veya satır sonuyla ayırın)

### Görsel Temalar

| Tema | Açıklama |
|------|----------|
| **Gradient** | Atlas.ti tarzı, tek renk koyu → açık |
| **Çok Renkli** | Frekansa göre 10 farklı renk |
| **Tek Renk** | Kullanıcının seçtiği renk |
| **Isı Haritası** | Kırmızı (sık) → Mavi (seyrek) |

### Filtreler
- Minimum frekans eşiği (1–10)
- Maksimum kelime sayısı (10–200)
- Minimum kelime uzunluğu (1–6 harf)

### Dışa Aktarma

| Format | Açıklama |
|--------|----------|
| **PNG** | Yüksek çözünürlük (2×), baskı kalitesi |
| **SVG** | Vektörel, sonsuz büyütülebilir |
| **Panoya kopyala** | kelime ↹ frekans formatında |
| **.tsv** | Excel/Sheets'te açılabilir frekans tablosu |

---

## 🚀 Kullanım

### Yöntem 1: Direkt kullanım (önerilen)

`kelime-bulutu.html` dosyasını bilgisayarınıza indirip çift tıklayın.

> Herhangi bir sunucu, Node.js veya kurulum **gerekmez**. Tamamen offline çalışır.

### Yöntem 2: GitHub Pages ile yayınlama

1. Bu repoyu fork edin veya dosyayı kendi reponuza yükleyin
2. **Settings → Pages → Deploy from branch → main → / (root)** seçin
3. Birkaç dakika sonra `https://kullaniciadi.github.io/kelime-bulutu/` adresinden erişin

---

## 🛠️ Geliştirici Kurulumu

Kaynak kodları üzerinde değişiklik yapmak isteyenler için:

```bash
# Repoyu klonla
git clone https://github.com/kullaniciadi/kelime-bulutu.git
cd kelime-bulutu

# Bağımlılıkları kur
npm install -g pnpm
pnpm install

# Geliştirme sunucusu başlat
pnpm dev

# Üretim build (tek HTML dosyası)
bash scripts/bundle-artifact.sh
# → bundle.html oluşur
```

### Teknoloji Yığını

- **React 18** + TypeScript
- **Tailwind CSS** + shadcn/ui bileşen kütüphanesi
- **Vite** (geliştirme ortamı) + **Parcel** (tek dosya bundle)
- Bundle sonrası sıfır harici bağımlılık — tam offline çalışır

---

## 📁 Proje Yapısı

```
kelime-bulutu/
├── kelime-bulutu.html          ← Dağıtıma hazır tek dosya (bunu paylaşın)
├── src/
│   ├── App.tsx                 # Ana uygulama bileşeni
│   ├── components/
│   │   └── WordCloud.tsx       # SVG renderer + PNG/SVG export
│   └── lib/
│       ├── stopwords.ts        # Türkçe stop word listesi (380+)
│       └── wordcloud.ts        # Frekans analizi + Arşimet spirali algoritması
├── scripts/
│   ├── init-artifact.sh        # Proje başlatma scripti
│   └── bundle-artifact.sh      # Tek HTML bundle scripti
└── README.md
```

---

## 🧠 Algoritma Hakkında

Kelime yerleştirme **Arşimet spirali** algoritması kullanır:

```
r = a × θ
```

Her kelime, merkezden dışa doğru genişleyen spiral boyunca taranarak çakışmasız ilk boş alana yerleştirilir. Font boyutu frekansa **logaritmik** orantılıdır — sık kelimeler baskın görünürken nadir kelimeler okunabilir kalır.

---

## 📚 Kullanım Senaryoları

- **Nitel araştırma** — Görüşme ve mülakat metinlerinin hızlı frekans analizi
- **Eğitim** — Atlas.ti, NVivo gibi ücretli yazılımlara ücretsiz alternatif
- **İçerik analizi** — Anket yanıtları, sosyal medya, açık uçlu sorular
- **Akademik sunum** — Kelime bulutu görseli PNG/SVG olarak dışa aktar

---

## 📄 Lisans

MIT Lisansı — Özgürce kullanabilir, değiştirebilir ve paylaşabilirsiniz.

---

<p align="center">
  <sub>
    ÖVA506 Nitel Veri Analizi Teknikleri · Doç. Dr. Hakan Kılınç<br>
    Anadolu Üniversitesi · Ölçme ve Veri Analitiği Yüksek Lisans Programı · 2025–2026
  </sub>
</p>
