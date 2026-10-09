# Kod Açıklamaları

Bu doküman kodun her satırını ezberletmek için değil, önemli kararların neden alındığını anlatmak için hazırlanmıştır.

## HTML

- `<!doctype html>`: Tarayıcıya modern HTML standardını kullanacağını bildirir.
- `<html lang="tr">`: Sayfanın dilini belirtir; ekran okuyucu ve arama motorları için faydalıdır.
- `meta viewport`: Mobil cihazlarda sayfanın gerçek cihaz genişliğine göre ölçeklenmesini sağlar.
- `meta description`: Sayfanın içeriğini özetler.
- `header`, `nav`, `main`, `section`, `article`, `footer`: İçeriğin amacını ifade eden semantik etiketlerdir.
- `a href`: Başka bir sayfaya veya sayfa içindeki bir bölüme geçiş sağlar.
- `label for` ve `input id`: Etiket ile form alanını ilişkilendirir.
- `required`, `type="email"`, `minlength`: Tarayıcının temel form doğrulamasına yardım eder.
- `aria-label`: Görsel metni yeterli olmayan bir kontrolün amacını erişilebilir isimle belirtir.
- `aria-hidden="true"`: Yardımcı teknolojiye dekoratif içeriği yok saymasını söyler.
- `class`: CSS ile tekrar kullanılabilir stilleri ilişkilendirir.

## CSS mimarisi

- `base/reset.css`: Tarayıcıların varsayılan stillerinden kaynaklanan tutarsızlıkları azaltır.
- `base/variables.css`: Renk, font ve ölçüleri merkezi olarak yönetir.
- `base/typography.css`: Metin görünümü ve ortak yardımcı sınıflar.
- `layout/`: Header, footer ve sayfa genişliği gibi ana düzen.
- `components/`: Buton ve ürün kartı gibi yeniden kullanılan parçalar.
- `pages/`: Belirli sayfa gruplarına ait düzenler.
- `main.css`: Diğer dosyaları sırayla içe aktarır.

## CSS özellikleri

- `box-sizing: border-box`: Genişlik hesabına padding ve border'ı dahil ederek ölçü yönetimini kolaylaştırır.
- `clamp(min, preferred, max)`: Bir değerin ekranla birlikte esnemesini, fakat belirli sınırlar içinde kalmasını sağlar.
- `min()`: Sabit bir üst sınır ile mevcut alanı karşılaştırarak uygun genişliği seçer.
- `repeat(4, minmax(0, 1fr))`: Grid'de eşit dört sütun oluşturur ve sütun içeriğinin gereksiz taşma yapmasını azaltır.
- `@media`: Belirli ekran koşullarında farklı kurallar uygulamak için kullanılır.
- `:hover`: İşaretçi üzerine geldiğinde görünümü değiştirir.
- `:focus-visible`: Klavye gibi odak temelli kullanımda görünür odak göstergesi sağlar.
- `::before`: HTML'e yeni içerik eklemeden dekoratif katman oluşturabilir.

## Öğrencinin görevi

Her başlık için koddan bir örnek göster ve şu soruları cevapla:
1. Bu kod ne yapıyor?
2. Burada kullanılmasaydı ne olurdu?
3. Bu çözümün alternatifi var mı?
4. Hangi durumda bu yaklaşım uygun olmaz?
