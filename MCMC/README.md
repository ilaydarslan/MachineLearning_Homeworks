# Uzak Bir Galaksinin Parlaklık Analizi

Bu projede, Bayesyen çıkarım ve MCMC yöntemi kullanılarak gürültülü gözlem verilerinden bir gök cisminin gerçek parlaklığı (`mu`) ve gözlem hatası (`sigma`) tahmin edilmiştir.

## Problem Tanımı
Amaç, sentetik olarak üretilen gözlem verilerinden gerçek parlaklık ve belirsizlik parametrelerini Bayesyen yöntemlerle tahmin etmektir.

## Veri
Çalışmada sentetik veri kullanılmıştır:
- `true_mu = 150.0`
- `true_sigma = 10.0`
- `n_obs = 50`

Veri, Gaussian gürültü eklenerek oluşturulmuştur.

## Yöntem
Aşağıdaki adımlar uygulanmıştır:
- Log-likelihood tanımlandı
- Log-prior tanımlandı
- Log-posterior tanımlandı
- `emcee` kütüphanesi ile MCMC örnekleme yapıldı
- Posterior örneklerden median ve güven aralıkları hesaplandı
- `corner` kütüphanesi ile Corner Plot oluşturuldu

## Sonuçlar
Elde edilen temel sonuçlar:
- `mu median = 147.7863`
- `mu %16 = 146.4261`
- `mu %84 = 149.0720`
- `mu mutlak hata = 2.2137`

- `sigma median = 9.4921`
- `sigma %16 = 8.5543`
- `sigma %84 = 10.5313`
- `sigma mutlak hata = 0.5079`

## Yorum / Tartışma
Sonuçlar, Bayesyen yöntemin gürültülü veriler altında gerçek parametrelere yakın tahminler yapabildiğini göstermektedir. Özellikle `mu` parametresi gerçek değere yakın tahmin edilmiştir. `sigma` parametresi için de makul bir sonuç elde edilmiştir. Corner Plot incelendiğinde parametreler arasında güçlü bir korelasyon olmadığı görülmektedir.

## Dosyalar
- `bayesian_brightness_analysis.ipynb`
- `corner_plot.png`
- `report.pdf`
