<img src="assets/banner.svg" width="100%" alt="Wavegen">

Wavegen, Deokwave oynatıcısının görüntü tarafındaki altyapı. [Nami 4K](https://github.com/Deokwave/nami-4k), [Frame Generation](https://github.com/Deokwave/frame-generation) ve [FRC](https://github.com/Deokwave/frc) izlerken bunun üzerinden çalışıyor. Hangi ayarı açtıysan, her kare ekrana gelmeden önce ona göre işleniyor.

## Başlangıç

4K, ara kare ve renk işleminin aynı anda, tarayıcının içinde ve takılmadan çalışması gerekiyordu. Üçünü ayrı ayrı çalıştırmak hem ekran kartını gereksiz yoruyor hem de birbirlerini bekletiyordu.

## Geliştirme

Üçünü tek bir motorda topladık. Wavegen tarayıcının WebGPU arayüzüyle doğrudan ekran kartında çalışıyor. Video kareleri önce 10 bitlik bir halkaya alınıyor, üç işlem de bu halkanın üzerinden geçiyor ve en son tek bir görüntü olarak ekrana çiziliyor. Hiçbir ayar açık değilken motor devreye girmiyor, tarayıcının kendi oynatıcısı görünüyor.

Ağır işleri, yani hareket analizini ve 4K ağını, birkaç ekran yenilemesine bölüyoruz ki hiçbir kare başka bir işi beklemesin. Her sürüm siteye girmeden önce 300'ü aşkın otomatik testten, oynatıcının bir kopyasında Chrome ve Edge'de 53 senaryodan, 60, 120, 144 ve 200 Hz ekranlarda ölçümden ve 20 dakikalık kesintisiz bir oynatmadan geçiyor. Görüntüyü değiştirmemesi gereken bir iyileştirmede, önceki ve sonraki çıktıyı yüzlerce kare çiftinde bayt bayt karşılaştırıyoruz.

## Sonuç

4K ağını yenilemelere bölmek, en ağır ayarda (1080p, Ultra 4K, 200 fps hedef) sayfanın kaçırdığı ekran yenilemesini 55 saniyede 1.320'den 1'e indirdi. Analizi çizimden ayırdığımız sürümde gecikme 720p'de 58-63 ms'den 48-54 ms'ye, 1080p'de 63-65 ms'den 48-55 ms'ye, 4K açıkken de 68-70 ms'den 59-60 ms'ye düştü.

İşlem senin cihazında yapıldığı için ayarların ne kadar rahat çalışacağı biraz da bilgisayarına bağlı. Zorlanırsan önce FPS Artırma'nın kalite modunu Dengeli'ye al.

Kod bu depoda yok, Deokwave kapalı kaynak.

[deokwave.com](https://deokwave.com) · [Discord](https://discord.gg/deokwave) · [Deokwave GitHub](https://github.com/Deokwave)
