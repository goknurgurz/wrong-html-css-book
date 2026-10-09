# Hata Ayıklama Cevap Anahtarı

Önce öğrencinin kendi açıklamasını al. Bu dosya öğretmen veya öz değerlendirme içindir.

## Bug 01 — HTML yapısı
**Sorun:** İlk paragraf kapatılmamış; iç içe içerik tarayıcı tarafından otomatik düzeltilebilir ve kaynak yapısı kafa karıştırır.  
**Çözüm:** `p` etiketi `section` başlamadan önce `</p>` ile kapatılmalı. Bölüm içindeki ikinci `p` de `</p>` ile kapatılmalı.  
**Öğrenme hedefi:** Etiketlerin açılıp kapanması, DOM yapısı ve tarayıcı otomatik düzeltmelerine güvenmeme.

Düzeltilmiş örnek:
```html
<h1>Kitap kataloğu</h1>
<p>Bu sayfada HTML yapısını kontrol et.</p>
<section>
  <h2>Yeni çıkanlar</h2>
  <p>Bu bölümdeki etiketleri ve semantik yapıyı incele.</p>
</section>
<a href="catalog.html">Kataloğa git</a>
```

## Bug 02 — CSS specificity
**Sorun:** `#important-notice` ID selector'ı, element ve class selector'larından daha yüksek specificity değerine sahiptir. Sonradan yazılan `.notice` kuralı ID kuralını geçersiz kılamaz.  
**Çözüm:** İstenen renk koyu mürekkep rengi ise ID selector'ını kaldırıp tek bir sınıf üzerinden yönetmek daha sürdürülebilirdir; geçici olarak `#important-notice { color: #242720; }` kullanılabilir.  
**Öğrenme hedefi:** Cascade sırası ile specificity arasındaki fark.

## Bug 03 — Box model
**Sorun:** `width: 100%` üzerine padding ve border eklenince `content-box` modelinde toplam genişlik yüzde 100'ü aşar.  
**Çözüm:** `* { box-sizing: border-box; }` kullan veya panel genişliğini uygun şekilde hesapla.  
**Öğrenme hedefi:** CSS box model.

## Bug 04 — Responsive grid
**Sorun:** Dört adet 280px sütun ve aralarındaki boşluk küçük ekranlara sığmaz.  
**Çözüm:** `.grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 220px), 1fr)); gap: 24px; }` gibi esnek bir grid kullan. İstenirse media query ile sütun sayısı ayrıca yönetilebilir.  
**Öğrenme hedefi:** Grid, `minmax`, `auto-fit` ve responsive tasarım.

## Bug 05 — Form
**Sorunlar:** `label for="email-address"` hiçbir input'un `id` değeriyle eşleşmiyor; input `type="text"` olduğu için e-posta doğrulaması yok; `name` niteliği yok; butonun `type` değeri açık değil.  
**Çözüm:**
```html
<label for="email">E-posta adresin</label>
<input id="email" name="email" type="email" autocomplete="email" required>
<button type="submit">Gönder</button>
```
**Öğrenme hedefi:** Label/input ilişkisi ve yerleşik form doğrulaması.

## Bug 06 — Bağlantı yolları
**Sorun:** Dosyanın `pages/` içinde olduğunu varsayarsak `index.html` ve `css/main.css` yolları bir üst dizine çıkmadığı için yanlış konumu gösterir.  
**Çözüm:** Ana sayfa için `../index.html`; CSS için `../css/main.css` kullanılmalı.  
**Öğrenme hedefi:** Göreli yolların dosyanın bulunduğu klasöre göre hesaplanması.

## Ek sözlü sorular
1. Hangi hata tarayıcıda hemen görünür, hangisi davranış/erişilebilirlik sorunu yaratır?
2. Bir sorunu çözmeden önce nasıl yeniden üretirsin?
3. CSS'i `!important` ile düzeltmek neden her zaman iyi bir çözüm değildir?
4. Hatanın düzeldiğini hangi testle kanıtlarsın?
