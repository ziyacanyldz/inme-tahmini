# İnme Hastalığı Tahmini
# Veri Kümesi
Strok tahmini için veri seti Kaggle'den alınmıştır (https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset). Bu veri kümesinde 5110 satır ve 12 sütun bulunur. Sütunlarda 'id', 'gender', 'age', 'hypertension', heart_disease','ever_married', 'work_type', 'Residence_type','avg_glucose_level', 'bmi', 'chemistry_status' ve 'inme' değerleri bulunur. Çıktı sütunu 'stroke', '1' veya '0' değerine sahiptir. '0' değeri inme riskinin tespit edilmediğini gösterirken, '1' değeri olası bir inme riskini gösterir. Çıktı sütunundaki ('stroke') '0' olasılığı, aynı sütundaki '1' olasılığından daha ağır bastığından, bu veri kümesi oldukça dengesizdir. Daha iyi doğruluk ve verileri dengelemek için veri ön işlemesi yapılır.
![image](https://user-images.githubusercontent.com/96024765/166560726-3ce3528b-25c7-4940-a8e1-eecbf8c643da.png)

# Veri Ön İşleme
Veri setinden istenmeyen gürültüyü ve aykırı değerleri kaldırmak için model oluşturmadan önce Veri Ön İşleme gereklidir. Alınan veri kümesi, 12 özniteliğe sahiptir. İlk olarak, 'id' sütunu, varlığı model oluşturmada fazla bir fark yaratmadığı için atılır. Daha sonra veri kümesi boş değerler açısından kontrol edilir ve boş değer varsa boş değerin olduğu satır silinir. Veri setini model oluşturmaya uygun hale getirmek için etiket kodlaması yapılır. Makine genellikle sayılarla eğitildiğinden, dizelerin tamsayılara dönüştürülmesi gerekir.

# Dengesiz Verileri İşleme
İnme tahmini görevi için seçilen veri seti oldukça dengesizdir. Tüm veri kümesi 5110 satıra sahiptir, bunlardan 249 satırı inme hastasıyken 4861 satır inme hastası değildir. Bu çalışmada veri seti dengesiz ve dengeli modellerin sonuçlarını karşılaştırabilmek için D1 ve D2 olarak iki farklı şekilde incelenmiştir.
![image](https://user-images.githubusercontent.com/96024765/166561359-325a265f-64f3-4188-b6e7-20c00390a458.png)
D1 de veri seti dengesiz. D2 de ise smote yöntemi ile veri seti dengeli  hale getirilmiş.

# Grid Search Kullanarak Algoritmalara Uygun Hiperparametreleri Bulma
Grid search ile hiper parametre seçim işleminde; belirlenen aralıkta bulunan tüm değerlerin kombinasyonları için ağ eğitilip sonuçlar gözlenir duruma göre en iyi kombinasyon hiper parametre grubu olarak seçilir. 
