1-TEORİK TEMELLER
| From | To | Probability |
| ---- | -- | ----------- |
| e    | e  | 0.6         |
| e    | v  | 0.4         |
| v    | v  | 0.8         |
| v    | e  | 0.2         |

| State | High | Low |
| ----- | ---- | --- |
| e     | 0.7  | 0.3 |
| v     | 0.1  | 0.9 |

Viterbi Adım Adım Hesaplama
t1 (High)

Başlangıçta yalnızca e durumu mümkündür.

δ1(e) = P(e) × P(High | e)

δ1(e) = 1.0 × 0.7

δ1(e) = 0.7

δ1(v) = 0

t2 (Low)

e → e

0.7 × 0.6 × 0.3 = 0.126

e → v

0.7 × 0.4 × 0.9 = 0.252
| Fonem Dizisi | Olasılık  |
| ------------ | --------- |
| e → e        | 0.126     |
| e → v        | **0.252** |
En yüksek olasılığa sahip fonem dizisi:

e → v

Dolayısıyla gözlem dizisi [High, Low] için en olası fonem dizisi e → v olarak bulunur.

2-UYGULAMA(PYTHON İLE)
Bu bölümde Python kullanılarak basit bir kelime tanıyıcı sistem simüle edilmiştir.

Modelde iki farklı kelime için ayrı HMM modelleri oluşturulmuştur:

EV

OKUL

Python programı hmmlearn kütüphanesini kullanarak iki ayrı HMM modeli oluşturur.
Her model için başlangıç olasılıkları, geçiş matrisi ve emisyon olasılıkları tanımlanır.

Sisteme yeni bir gözlem dizisi verildiğinde her model için log-likelihood değeri hesaplanır. 
Daha yüksek olasılığa sahip olan model, gözlem dizisinin hangi kelimeye ait olduğunu belirler.

Bu yaklaşım, konuşma tanıma sistemlerinde kullanılan temel sınıflandırma yöntemlerinden biridir.

3-ANALİZ VE YORUMLAMA
3.1 Ses Gürültüsünün Emisyon Olasılıklarına Etkisi

Ses verisinde bulunan gürültü (noise), HMM modelindeki emisyon olasılıklarını doğrudan etkileyebilir. 
Emisyon olasılıkları belirli bir fonemin hangi gözlemleri üretme ihtimalini temsil eder. 
Gürültü bulunduğunda ses sinyalinin spektral özellikleri değişebilir ve model yanlış gözlemler algılayabilir.

Bu durum emisyon dağılımlarının daha belirsiz hale gelmesine neden olur ve modelin doğru fonemi tahmin etmesini zorlaştırır. 
Sonuç olarak gürültü, konuşma tanıma sistemlerinin doğruluğunu azaltabilir.

3.2 Büyük Kelime Dağarcığında Deep Learning Kullanılmasının Nedeni

Gerçek konuşma tanıma sistemlerinde binlerce kelime ve çok karmaşık akustik özellikler bulunur.
HMM ve Viterbi algoritması bu tür büyük ve karmaşık veri yapılarında sınırlı performans gösterebilir.

Derin öğrenme yöntemleri (Deep Learning) ise çok daha büyük veri kümeleri üzerinde karmaşık örüntüleri öğrenebilir. 
Özellikle sinir ağları, konuşma sinyalinden otomatik olarak özellik çıkarabilir ve yüksek doğruluk oranları sağlayabilir.

Bu nedenle modern konuşma tanıma sistemlerinde HMM tabanlı yöntemler yerine çoğunlukla derin öğrenme tabanlı modeller tercih edilmektedir.

SONUÇ
Bu çalışmada HMM kullanılarak basit bir izole kelime tanıma sistemi tasarlanmıştır. 
Viterbi algoritması kullanılarak en olası fonem dizisi hesaplanmış ve Python ile iki farklı kelime modeli arasında sınıflandırma yapılmıştır.
Ayrıca ses gürültüsünün model üzerindeki etkisi ve modern konuşma tanıma sistemlerinde derin öğrenmenin tercih edilme nedenleri tartışılmıştır.
