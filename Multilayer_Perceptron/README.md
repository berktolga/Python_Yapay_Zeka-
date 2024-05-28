Multilayer Perceptron

Sequential model, çok katmanlı algılayıcıdaki katmanları modellemeyi oluşturmaya olanak sağlar.

Flatten,  matris şeklindeki veriyi tek boyuta çevirmek için kullanılır.
Flatten, girdi verilerini basitçe düzleştirir.

Dense layer, gizli katmanlardır.  Fully-connected bir model oluşturmak için kullanılır. 
Bir katmandaki bütün nöronlar bir önceki katmandaki bütün nöronlara bağlanırsa buna Dense ya da tam bağlantılı katman denir.

Çıktı değeri aktivasyon fonksiyonuna göre belirlenir.
ReLu, daha çok gizli katmanlarda kullanılır.
Son dense layer, output(çıktı) katmanıdır.
Output(çıktı) katmanındaki aktivasyon fonksiyonu olarak sigmoid veya softmax kullanıldı.

Input shape, girdi verilerinin şeklini temsil eder.
(128,128,3) girdi olan veri boyutudur. İlk başta bunu belirlemek gerekiyor.

Modelin öğrenme işlemi için bazı ayarlamalar yapılır:
Optimizer: Ağırlık katsayılarının güncellenmesi için kullanılan optimizasyon yöntemidir.
Birçok optimize edici vardır: SGD, Adam, Adagrad,Adamax
Adam(The Adaptive Movement Estimation Algorithm) algoritması kullanıldı.
(https://keras.io/api/optimizers/)

Adam optimizasyonu,  gradient descent’in bir uzantısıdır. Stokastik bir gradyan iniş yöntemidir.
Gerçek gradyanı hesaplamak için tüm veri kümesini kullanmak yerine, stokastik bir yaklaşım oluşturmak için rastgele seçilen bir veri alt kümesini kullanır.
Daha az bellek gerektirir ve büyük veri kümelerinde daha iyi performans gösterir.
Daha optimize bir gradyan inişi sağlamak için RMSP(Root Mean Square Propagation) ve Momentumlu Gradyan İniş(Gradient Descent with Momentum) algoritmalarını birleştirerek çalışır.
(https://www.geeksforgeeks.org/intuition-of-adam-optimizer/)

Loss Function: Gerçek değer ile tahmin edilen değer arasındaki hatayı ifade eder.

Ara katmanlarda ReLU aktivasyon fonksiyonu, output katmanında ise bazı uygulamalarda softmax, bazı uygulamalarda sigmoid kullanıldı.
Öğrenme oranı 0.001 olarak ayarlandı.
Kullanılan gradyan yöntemi Adam’dır.
Gizli katman sayısı ve bu katmanlardaki düğüm sayısı farklı farklı uygulandı.
Her uygulama için sayılar ve sonuçlar ayrı dosyalardadır.
