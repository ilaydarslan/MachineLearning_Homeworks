1. Tanımlar ve Makine Öğrenmesi İlişkisi
Makine öğrenmesi büyük ölçüde lineer cebire dayanır. Matrisler veri setlerini, model parametrelerini ve dönüşümleri temsil etmek için kullanılır. Matris işlemleri, verinin ölçeklenmesi, döndürülmesi ve dönüştürülmesini sağlar.

Özdeğerler ve özvektörler, verinin yapısını anlamada önemli rol oynar. Özvektörler yönü, özdeğerler ise bu yönlerdeki büyüklüğü temsil eder.

Bu kavramlar özellikle şu alanlarda kullanılır:

PCA (Temel Bileşen Analizi)
SVD (Tekil Değer Ayrışımı)
Sinir ağları
Kovaryans analizi

2. NumPy linalg.eig Analizi
NumPy kütüphanesinin linalg modülünde bulunan eig fonksiyonu, kare bir matrisin özdeğerlerini ve özvektörlerini hesaplamak için kullanılır. Bu fonksiyon, lineer cebirde önemli bir yere sahip olan özdeğer problemini sayısal yöntemlerle çözer.

Fonksiyonun temel kullanımı şu şekildedir:
import numpy as np

A = np.array([[1,2] [3, 4]])

values, vectors = np.linalg.eig(A)

Bu fonksiyonun çalışma mantığı, aşağıdaki matematiksel ifadeye dayanır:

A·v = λ·v

Burada:

A: Matris
v: Özvektör
λ: Özdeğer

Fonksiyon çalıştırıldığında:
values değişkeni matrisin özdeğerlerini içerir.
vectors değişkeni ise bu özdeğerlere karşılık gelen özvektörleri sütunlar halinde içerir.
NumPy bu hesaplamaları doğrudan kendisi yazmak yerine, arka planda yüksek performanslı lineer cebir kütüphanelerini (özellikle LAPACK) kullanarak gerçekleştirir. Bu sayede hesaplamalar hızlı ve güvenilir şekilde yapılır.

Dikkat edilmesi gereken bazı noktalar:

-Girdi olarak verilen matris mutlaka kare matris olmalıdır.
-Sonuçlar bazen karmaşık (complex) sayılar içerebilir.
-Hesaplamalar sayısal olduğu için çok küçük hatalar olabilir.

Kaynakça:
NumPy Dokümantasyonu
https://numpy.org/doc/2.1/reference/generated/numpy.linalg.eig.html
NumPy GitHub
https://github.com/numpy/numpy/tree/main/numpy/linalg

3. Soru – Özdeğer Hesaplama ve Karşılaştırma

Bu çalışmada, bir matrisin özdeğerleri iki farklı yöntem kullanılarak hesaplanmıştır. İlk olarak, NumPy kütüphanesinin hazır eig fonksiyonu kullanılmadan, karakteristik polinom yardımıyla manuel bir hesaplama yapılmıştır. Daha sonra aynı matris için NumPy linalg.eig fonksiyonu kullanılarak özdeğer ve özvektörler elde edilmiştir.

Manuel yöntemde, matrisin karakteristik polinomu oluşturulmuş ve bu polinomun kökleri bulunarak özdeğerler hesaplanmıştır. NumPy yöntemi ise bu işlemleri arka planda daha optimize ve hızlı bir şekilde gerçekleştirmektedir.

Elde edilen sonuçlar karşılaştırıldığında, manuel hesaplama ile NumPy kullanılarak elde edilen özdeğerlerin birbirine oldukça yakın olduğu görülmüştür. Küçük farklar, sayısal hesaplama yöntemlerinden kaynaklanmaktadır.

Sonuç olarak, manuel yöntem teorik olarak konunun anlaşılması açısından faydalı olsa da, pratik uygulamalarda NumPy gibi hazır kütüphanelerin kullanılması daha hızlı ve güvenilir sonuçlar vermektedir.

Kaynakça
https://github.com/LucasBN/Eigenvalues-and-Eigenvectors
https://numpy.org/doc/2.1/reference/generated/numpy.linalg.eig.html
