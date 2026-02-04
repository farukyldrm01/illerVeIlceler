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
🚀 Kullanım Örnekleri
Veriyi projenize dahil etmenin birkaç yolu:

1. Raw URL ile Çekme (Fetch API)
Veriyi direkt olarak GitHub üzerinden çekebilirsiniz:

JavaScript
fetch('[https://raw.githubusercontent.com/KULLANICI_ADINIZ/REPO_ADINIZ/main/tr-il-ilce.json](https://raw.githubusercontent.com/KULLANICI_ADINIZ/REPO_ADINIZ/main/tr-il-ilce.json)')
  .then(response => response.json())
  .then(data => console.log(data));
2. Projeye Dahil Etme (Import - Node.js / React / Vue)
Dosyayı indirip projenizin içine atarak import edebilirsiniz:

JavaScript
import cityData from './data/tr-il-ilce.json';

// Örnek: Adana'nın ilçelerini listele
const adana = cityData.find(c => c.plaka === 1);
console.log(adana.ilceler);
3. Python ile Kullanım
Python
import json

with open('tr-il-ilce.json', 'r', encoding='utf-8') as f:
    data = json.load(f)

# Örnek: Tüm illeri yazdır
for item in data:
    print(f"{item['plaka']} - {item['il']}")
🤝 Katkıda Bulunma (Contributing)
Eğer bir yazım hatası fark ederseniz veya yeni bir ilçe eklendiyse, lütfen katkıda bulunmaktan çekinmeyin!

Bu repoyu fork'layın.

Yeni bir branch oluşturun (git checkout -b feature/duzeltme).

Değişikliklerinizi yapın ve commit'leyin (git commit -m 'Eksik ilçe eklendi').

Branch'inizi push'layın (git push origin feature/duzeltme).

Bir Pull Request (PR) oluşturun.

📝 Lisans
Bu proje MIT Lisansı ile lisanslanmıştır. Dilediğiniz gibi kullanabilir, değiştirebilir ve dağıtabilirsiniz.

⭐ Eğer bu proje işinize yaradıysa, sağ üst köşeden Star vermeyi unutmayın
