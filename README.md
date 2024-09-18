# Makine Öğrenmesi ile YouTube İstatistikleri

# Projenin amacı:

Bu proje, elimizde bulunan *YouTube* istatistiklerini inceleyerek yorum sayısı, beğeni sayısı, beğenmeme sayısı ve videonun kategorisi ile izlenme sayısı arasındaki bağlantıyı inceliyor. Bunu yaparken hem *Supervised* temelleri hem de *Unsupervised* temelleri ayrı ayrı kullanıyor

# Veri Seti:

Kullanılan veri seti 40949 veriden ve 16 sütundan oluşmaktadır.
* **video_id:** YouTube içeriğinin ID numarasını temsil eder.
* **trending_date:** Trend olduğu tarihi belirtir.
* **title:** YouTube içeriğinin başlığını belirtir.
* **channel_title:** YouTube içeriğini paylaşan kanalın ismini temsil eder.
* **category_id:** YouTube içeriğinin kategorisini temsil eder.
* **publish_time:** YouTube içeriğinin yayınlandığı tarihi temsil eder.
* **tags:** YouTube içeriğinde kullanılan *tag*'leri (etiketleri) temsil eder.
* **views:** YouTube içeriğinin izlenme sayısını temsil eder.
* **likes:** YouTube içeriğinin aldığı beğeni sayısını temsil eder.
* **dislikes:** YouTube içeriğinin aldığı beğenmeme sayısını temsil eder.
* **comment_count:** YouTube içeriğinin aldığı yorum sayısını temsil eder.
* **thumbnail_link:** YouTube içeriğinde kullanılan thumbnail görselini (Küçük Resim) temsil eder.
* **comments_disabled:** YouTube içeriğinde yorumların sınırlandırılıp sınırlandırılmadığını temsil eder.
* **ratings_disabled:** YouTube içeriğinin ratinglerinin sınırlandırılıp sınırlandırılmadığını temsil eder.
* **video_error_or_removed:** YouTube içeriğinin oynatılıp oynatılamadığını temsil eder.
* **description:** YouTube içeriğinin açıklamasını temsil eder.

# Değişkenler

Bağımlı değişken(y) **"views** sütunu, bağımsız değişkenler(X) ise **"category_id"** , **"likes"**, **"dislikes"**, **"comment_count"** sütunları olarak belirlenmiştir. Çeşitli regresyon algoritmaları denenerek bağımlı değişkeni bulmaya çalışılır. Bu projede kullanılan regresyon algoritmaları:
```python
from sklearn.linear_model import LinearRegression, Ridge, Lasso, ElasticNet, BayesianRidge
from sklearn.neighbors import KNeighborsRegressor
from sklearn.tree import DecisionTreeRegressor
from sklearn.ensemble import RandomForestRegressor, GradientBoostingRegressor
from sklearn.svm import SVR
from xgboost import XGBRegressor
```

# Model Seçimi

En iyi performansı veren algoritma seçilir, hiperparametre optimize edilir ve seçilen algoritmanın değerlendirilmesi yapılır. Bu projede en iyi performansı veren regresyon modelinin **Random Forest Regression** olduğuna karar verilmiştir. Değerlendirme sürecinde bu projede **Ortalama Karesel Hata(Mean Squared Error), Ortalama Mutlak Hata(Mean Absolute Error)** kullanılmıştır.

# Unsupervised Model

*Unsupervised* modeli geliştirme aşamasında ise kümelemenin daha doğru olabilmesi için **"views"** sütununu da işlemlere dahil ettim. Bu yolda kullandığım *unsupervised* model ise *K-Means* modeli oldu. Bunun sonucunda ise 4 adet farklı küme elde ettim.


# Kaggle Notebook Linkleri

**Supervised:** https://www.kaggle.com/code/yusufozdil/aygazml-supervised
**Unsupervised:** https://www.kaggle.com/code/yusufozdil/aygazml-unsupervised
