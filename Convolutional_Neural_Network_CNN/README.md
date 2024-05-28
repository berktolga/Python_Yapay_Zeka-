Convolutional Neural Network (CNN) Katmanları

1)	Convolutional Layer
Bu katman CNN’nin ana yapı taşıdır. Resim özelliklerini algılamaktan sorumludur. Bu işlem birçok defa uygulanarak resimdeki öznitelikler çıkarılır. Evrişim işlemi uygulandıkça resmin daha özel noktalarına ulaşılır.

Filtre(kernel), resim üzerinde kaydırma değeri(stride) kadar kaydırılarak resmin farklı açılardan taranmasını sağlar.
	Yani her filtre küçük bir örüntü tespit eder.
	
	Resim ve filtre arasındaki indisler birbirisi ile çarpılır ve tüm sonuçlar toplanır.
	Daha sonra sonuç, çıktı matrisinde toplanır. Bu elde edilen son matris “Feature Map” adlandırılır.

	Kısaca; filtre, görüntü üzerinde hareket ettirilerek bir feature map elde edilir. Yani 
	özellikler tespit edilir.

2)	Non-Linearity Layer
Convolutional katmandan sonra genellikle aktivasyon fonksiyonlarından biri kullanılır. Sinir ağı eğitiminin hızı konusunda en iyi sonucu ReLu fonksiyonu verdiği için diğer aktivasyon fonksiyonlarına yerine artık bu fonksiyon kullanılmaya başlanmış.

ReLu fonksiyonu uygulandıktan sonra Feature Map’teki siyah değerler(negatif değerler) kaldırılır ve onların yerine 0 yazılır.

3)	Pooling Layer
Bu katmanın görevi, gösterimin kayma boyutunu, ağ içindeki parametreleri ve hesaplama sayısını azaltmaktır. Birçok pooling işlemi vardır ama en popüleri “max pooling”tir.

Max Pooling: 
Boyut küçültmek için kullanılır.
Örneğin pooling değeri 2 seçilirse matrisler 2x2’lik küçük matrislere bölünmüş olacak.
Daha sonra her bölünen alt matristeki büyük değerler seçilerek yeni bir matris oluşturulur.
Max pooling her zaman kullanımı her zaman zorunlu değil.
Resmin içerisinde farklı farklı desenler varsa kullanmak daha iyi olabilir.

4)	Flattening Layer
Sinir ağları, giriş verilerini tek boyutlu bir diziden alır.
Bu katman Convolutional ve Pooling katmanından gelen matrisleri tek boyutlu diziye çevirir. 

5)	Fully-Connected Layer
Flattening katmanında elde edilen tek boyutlu dizi Multilayer Perceptron’da kullanılır.

6)	Dropout
Yapay sinir ağında herhangi iki katman arasında bazı düğümlerin etkisiz hale getirilerek denenmesi işlemine denir.
Bu işlem sayesinde modelin aynı verinin farklı şekillerini öğrenmesi sağlanır. 
Ayrıca Overfitting’i önlemede etkili bir işlemdir.
