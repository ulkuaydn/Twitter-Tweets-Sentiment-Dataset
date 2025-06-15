# Twitter Tweets Sentiment Dataset Projesi

Bu projede, **Kaggle** üzerinden temin edilen “Twitter Tweets Sentiment Dataset” kullanılarak **duygu analizi (Sentiment Analysis)** ve **konu modelleme (Topic Modeling)** yapılmıştır. Amaç, sosyal medya verilerinden anlamlı içgörüler elde ederek hem bireysel hem de kurumsal karar süreçlerine katkı sağlamaktır.

---

##  Proje Özeti

Twitter, kullanıcıların düşüncelerini anlık olarak paylaştığı, kısa metin yapısına sahip bir sosyal medya platformudur. Bu proje kapsamında:

- Tweet'ler metin ön işleme teknikleriyle temizlendi.
- TF-IDF ve Bag of Words yöntemleri ile sayısallaştırma yapıldı.
- Lojistik Regresyon ile duygu sınıflandırması gerçekleştirildi.
- LDA (Latent Dirichlet Allocation) ile konu modelleme uygulandı.

---

##  Veri Seti

Veri seti [Kaggle](https://www.kaggle.com/datasets/yasserh/twitter-tweets-sentiment-dataset) platformundan alınmıştır ve şu sütunlardan oluşur:

| Sütun Adı     | Açıklama                                      |
|---------------|-----------------------------------------------|
| `text`        | Tweet’in orijinal tam metni                   |
| `selected_text` | Tweet’te duyguyu en çok yansıtan parça     |
| `sentiment`   | Tweet’in duygu durumu (positive, negative, neutral) |

###  Örnek Kayıtlar

| text                         | selected_text     | sentiment |
|------------------------------|-------------------|-----------|
| I love this phone            | love              | positive  |
| Worst service ever           | Worst service     | negative  |
| Not sure about this product  | Not sure          | neutral   |

---

##  Veri Ön İşleme

Ham veriler analiz öncesi şu işlemlerden geçirilmiştir:

- Küçük harfe dönüştürme  
- URL, mention ve hashtag temizliği  
- Noktalama işaretleri ve sayıları kaldırma  
- Stopword (gereksiz kelimeler) temizliği  
- Boşluk düzenlemeleri  
- `clean_tweet` adında yeni bir sütun oluşturuldu  

### Örnek Temizleme:

| Orijinal Tweet                            | Temizlenmiş Tweet         |
|-------------------------------------------|----------------------------|
| "I can't believe this happened!"          | cant believe happened      |
| "@user I totally agree. #truth"           | totally agree              |

---

##  Yöntem ve Uygulama

### 1.  Duygu Analizi (Sentiment Analysis)

- `sentiment` sütunu 3 sınıfa dönüştürülmüştür:  
  - 0 = Negative  
  - 1 = Neutral  
  - 2 = Positive

- Metinler **TF-IDF** yöntemi ile sayısallaştırılmıştır.
- **Logistic Regression** algoritması ile model eğitilmiştir.

####  Model Performansı

| Metrik      | Değer |
|-------------|-------|
| Accuracy    | 0.85  |
| Precision   | 0.86  |
| Recall      | 0.84  |
| F1-Score    | 0.85  |

---

### 2.  Konu Modelleme (Topic Modeling)

- Temizlenmiş metinler `token` hâline getirilmiştir.
- **gensim** ve **pyLDAvis** kütüphaneleri kullanılmıştır.
- **LDA (Latent Dirichlet Allocation)** yöntemiyle 5 ana konu tespit edilmiştir.

####  Örnek Konular

- **Konu 1:** `battery, charge, power, life`  
- **Konu 2:** `delivery, late, order, wait`  
- **Konu 3:** `screen, display, resolution, brightness`

---

##  Sonuç ve Değerlendirme

Bu çalışmayla birlikte:

- Tweet’ler üzerinden %85 doğrulukla duygu sınıflandırması yapılmıştır.
- Kullanıcıların sıklıkla bahsettiği konular başarılı şekilde belirlenmiştir.

### Uygulama Alanları:

-  **Marka algısı** takibi  
-  **Müşteri şikayeti** tespiti  
-  **Kriz yönetimi** ve hızlı aksiyon alma  
-  **Genelleştirilebilir ML modelleri** ile otomatik etiketleme  

---

##  Kullanılan Araçlar ve Kütüphaneler

- Python (pandas, numpy, sklearn, nltk, gensim, pyLDAvis)
- Jupyter Notebook / Google Colab
- Matplotlib & Seaborn (görselleştirme)

---

##  Not

Bu proje sadece bir başlangıçtır. Model performansı artırmak için:

- Derin öğrenme tabanlı modeller (BERT, RoBERTa)
- Veri artırma (data augmentation)
- Daha büyük veri setleri denenebilir.



 
