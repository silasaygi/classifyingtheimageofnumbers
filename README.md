## Rakamların Görüntüsünü Sınıflandırma

Bu çalışma, scikit-learn kütüphanesinin digits veri setini kullanarak rakamların görüntüsünü sınıflandırmayı hedeflemektedir. 
Çalışma, veri yükleme ve ön işlemeden boyut indirgeme, modelleme ve model değerlendirme adımlarına kadar bir makine öğrenimi projesinin tüm aşamalarını içermektedir.

# Bu proje, Turkcell Geleceği Yazanlar platformunda bulunan "Uygulamalı Tabanlı Makine Öğrenimi" eğitiminden, 
# Kaan Can Yılmaz hocamızın hazırlamış olduğu bir projedir. 

# 1. Veri Yükleme ve Ön İşleme

Digits veri seti, el yazısıyla yazılmış rakam görüntülerinden oluşan bir veri setidir. Bu veri seti, digits.data ve digits.target olmak üzere iki ana bölümden oluşur:

digits.data: Görüntülerden özelliklerin elde edildiği sayısal bir matris.
digits.target: Her görüntüyü temsil eden sınıf etiketleri (0-9 arası rakamlar).

Train-Test Split:
Veri seti, %80 eğitim ve %20 test olacak şekilde bölünerek test verisi modelin doğruluğunu değerlendirmek için ayrılmıştır.

Standardizasyon:
Veriler, modelleme aşamasında daha iyi performans elde etmek için standart hale getirilmiştir:

# 2. PCA ile Boyut İndirgeme

Boyut indirgeme, verilerin çok boyutlu uzaydan daha düşük boyutlu bir uzaya aktarılarak hesaplama maliyetlerini azaltır ve görsel analiz yapılmasını kolaylaştırır.
Tüm varyansın %95’ini koruyacak şekilde bir PCA modeli oluşturulmuştur.

# 3. Model Training ve Grid Search

Bu aşamada, çeşitli makine öğrenimi modelleri GridSearchCV kullanılarak optimize edilmiş ve en iyi parametreler belirlenmiştir. 
Kullanılan modeller şunlardır:
Destek Vektör Makineleri (SVM), 
Random Forest,
K-Nearest Neighbors (KNN).

# 4. Voting Classifier ile Birleştirme

En iyi performansa sahip SVM, Random Forest ve KNN modelleri birleştirilerek bir "Voting Classifier" oluşturulmuş ve doğruluğu test edilmiştir.

# Sonuç ✨

Boyut indirgeme, parametrik optimizasyon ve model birleştirme gibi 
tekniklerle %97’nin üzerinde bir başarı oranı elde edilmiştir. 
