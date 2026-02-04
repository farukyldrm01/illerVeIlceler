# 🇹🇷 Türkiye İl ve İlçeler JSON Verisi (Turkey Provinces and Districts)

Bu repository, Türkiye'deki 81 il ve bu illere bağlı tüm ilçeleri içeren, geliştiriciler için hazırlanmış güncel bir **JSON** veri setidir.

Projenizde il/ilçe seçim menüleri (dropdown), harita uygulamaları veya adres formları oluştururken kolayca kullanabilirsiniz.

## 📂 Veri Yapısı (Data Structure)

Veri seti aşağıdaki JSON formatında yapılandırılmıştır. Her il objesi; il adını, plaka kodunu ve o ile ait ilçelerin listesini içerir.

```json
[
  {
    "il": "Adana",
    "plaka": 1,
    "ilceler": [
      "Aladağ",
      "Ceyhan",
      "Çukurova",
      "Feke",
      "İmamoğlu",
      "Karaisalı",
      "Karataş",
      "Kozan",
      "Pozantı",
      "Saimbeyli",
      "Sarıçam",
      "Seyhan",
      "Tufanbeyli",
      "Yumurtalık",
      "Yüreğir"
    ]
  },
  {
    "il": "Adıyaman",
    "plaka": 2,
    "ilceler": [
      "Besni",
      "Çelikhan",
      "Gerger",
      "Gölbaşı",
      "Kahta",
      "Merkez",
      "Samsat",
      "Sincik",
      "Tut"
    ]
  }
  // ... diğer iller
]
