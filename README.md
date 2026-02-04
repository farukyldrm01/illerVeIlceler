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
```
Nasıl Kullanılır?
-----------------

Projenize dahil etmenin 3 farklı yolu:

### 1\. Raw URL ile Çekme (Fetch API)

Veriyi indirmeden, direkt GitHub üzerinden kullanmak için:

JavaScript

    // KULLANICI_ADIN ve REPO_ADIN kısımlarını kendi reponuza göre düzenleyin
    const url = '[https://raw.githubusercontent.com/KULLANICI_ADIN/REPO_ADIN/main/tr-il-ilce.json](https://raw.githubusercontent.com/KULLANICI_ADIN/REPO_ADIN/main/tr-il-ilce.json)';
    
    fetch(url)
      .then(response => response.json())
      .then(data => {
        console.log("İller yüklendi:", data);
      })
      .catch(error => console.error('Hata:', error));

### 2\. Projeye Import Etme (React / Vue / Node.js)

Dosyayı projenize indirip direkt import edebilirsiniz:

JavaScript

    import cityData from './tr-il-ilce.json';
    
    // Örnek: Plakası 1 olan ili bul (Adana)
    const selectedCity = cityData.find(city => city.plaka === 1);
    console.log(selectedCity.ilceler);

### 3\. Python ile Okuma

Python

    import json
    
    with open('tr-il-ilce.json', 'r', encoding='utf-8') as f:
        data = json.load(f)
    
    for item in data:
        print(f"{item['plaka']} - {item['il']}")

🛠 Kontrol Scripti (Opsiyonel)
------------------------------

Eğer veriyi düzenlerseniz, JSON formatının bozulup bozulmadığını veya sıralamayı kontrol etmek için şu basit Python scriptini kullanabilirsiniz:

Python

    import json
    
    # JSON dosyasını yükle ve plakaya göre sırala
    try:
        with open('tr-il-ilce.json', 'r', encoding='utf-8') as f:
            data = json.load(f)
        
        # Plakaya göre sıralama
        data.sort(key=lambda x: x['plaka'])
        
        print(f"Toplam {len(data)} il başarıyla yüklendi ve sıralandı.")
        
    except json.JSONDecodeError:
        print("HATA: JSON formatı bozuk!")
    except FileNotFoundError:
        print("HATA: Dosya bulunamadı!")

🤝 Katkıda Bulunma
------------------

Eksik veya hatalı bir veri görürseniz:

1.  Forklayın.
    
2.  Düzeltip Commit atın.
    
3.  Pull Request gönderin.
    

📝 Lisans
---------

MIT License. Özgürce kullanabilirsiniz.
