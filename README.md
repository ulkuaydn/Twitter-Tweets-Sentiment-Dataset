#  Twitter Duygu ve Konu Modelleme Analizi 

 **Python ile Veri Bilimi** dersi kapsamında gerçekleştirilmiş bu projede, Twitter kullanıcılarının paylaştığı tweetler üzerinde duygu analizi ve konu modelleme yöntemleri uygulanmıştır.

Bu proje, sosyal medya metinleri üzerinden anlam çıkarımı yaparak; duygu sınıflandırması, konu tespiti ve metin madenciliği tekniklerini bir araya getirmektedir.

---

##  Proje Bileşenleri

###  Veri Seti: 
- Kaynak: [Kaggle - Twitter Tweets Sentiment Dataset](https://www.kaggle.com/datasets/yasserh/twitter-tweets-sentiment-dataset)
- İçerik: 27.000+ tweet, kullanıcı duygusu, orijinal ve özet metin
- Sütunlar: `text`, `selected_text`, `sentiment`

---

##  Kullanılan Araçlar ve Teknolojiler

| Alan                | Kullanılan Teknoloji   |
|---------------------|------------------------|
| Programlama Dili    | Python                 |
| Görselleştirme      | Matplotlib, Seaborn, WordCloud |
| Veri İşleme         | Pandas, NLTK, Gensim   |
| Makine Öğrenmesi    | Scikit-learn, Logistic Regression |
| Konu Modelleme      | Gensim LDA, pyLDAvis   |
| NLP                 | TF-IDF, BoW, Lemmatization |

---

##  Proje İçeriği

### 1️ Veri Ön İşleme

- URL, mention, özel karakter ve stopword temizliği
- Lemmatization ve küçük harfe çevirme
- `clean_tweet` sütunu oluşturuldu

 Eklenen Görseller:
- ![uzunluk dağılımı](https://github.com/user-attachments/assets/6cb1e383-b18b-4640-962c-fd48226b2978)
- ![en sık geçen kelimeler](https://github.com/user-attachments/assets/7ae3fe93-ac40-47d0-96cb-33eccc08292b)
- ![duygu dağılımı](https://github.com/user-attachments/assets/1471b42d-7514-45fa-879a-33336881afca)

---

### 2️ Vektörleştirme ve Görselleştirme

- TF-IDF ve BoW kullanıldı
- Kelime frekansları çıkarıldı
- WordCloud ile görselleştirildi

---

### 3️ Duygu Analizi (Sentiment Analysis)

- Etiket: `sentiment` → 0 = Negatif, 1 = Nötr, 2 = Pozitif
- Model: `LogisticRegression`
- Eğitim/test oranı: %80 / %20
- Değerlendirme: `Confusion Matrix`, `Accuracy`, `Precision`, `Recall`, `F1-score`

 Eklenen Görsel:
- ![confusion matrix](https://github.com/user-attachments/assets/b4da9da5-d0ea-4766-8209-28335b3a2ff1)


---

### 4️ Konu Modelleme (Topic Modeling)

- Algoritma: LDA (Latent Dirichlet Allocation)
- Tokenizasyon: `nltk.word_tokenize`
- 5000 tweet üzerinde eğitim
- pyLDAvis ile konu görselleştirmesi

 Eklenen Görsel:
- ![konulara arası mesafe haritası](https://github.com/user-attachments/assets/7103c597-7a3f-4452-ae8e-6c849c57c42e)


---

### 5️ Kural Tabanlı Etiketleme & Sınıflandırma

- Belirli anahtar kelimelere göre konular manuel belirlendi
- Bu etiketler ile ikinci bir sınıflandırma modeli kuruldu
- Artık kurala gerek kalmadan model tahmin yapabiliyor

---

##  Model Performansı

| Metrik         | Değer       |
|----------------|-------------|
| Doğruluk       | %85+        |
| Precision      | Yüksek      |
| Recall         | Dengeli     |
| F1-Score       | Tatmin edici |

> Detaylar için: `classification_report` ve `confusion_matrix` kullanıldı.

---

##  Sonuç ve Yorumlar

- Twitter verisi üzerinde uygulanan duygu ve konu modelleme başarılı sonuçlar verdi.
- LDA ile öne çıkan temalar analiz edildi.
- Duygu sınıflandırması, işletmelere sosyal medya analizinde yardımcı olabilir.
- Bu tür analizler, kriz yönetimi, pazarlama stratejileri ve müşteri desteği açısından önemlidir.

---

##  Kaynakça

- [Kaggle Dataset](https://www.kaggle.com/datasets/yasserh/twitter-tweets-sentiment-dataset)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/)
- [NLTK Documentation](https://www.nltk.org/)
- [Gensim LDA](https://radimrehurek.com/gensim/)
- [pyLDAvis Docs](https://pyldavis.readthedocs.io/)

---

## 👨‍💻 Geliştirici

**Ülkü AYDIN**  
YBS Öğrencisi  
Proje: Python ile Veri Bilimi  

---

