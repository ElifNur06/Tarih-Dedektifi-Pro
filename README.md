# 🕵️‍♂️ Tarih Dedektifi

Tarih Dedektifi, oyuncuların kendilerini tarihin en kritik ve gizemli anlarının tam merkezinde buldukları, metin tabanlı ve yapay zeka destekli bir mobil rol yapma (RPG) oyunudur. Geleneksel çizgisel hikaye anlatımının dışına çıkan bu yapıda, her seçim hikayenin akışını ve oyunun sonunu doğrudan etkiler. Proje; üretken yapay zeka teknolojileri, dinamik görsel üretimi ve modern mobil teknolojilerin entegrasyonu ile zenginleştirilmiş sürükleyici bir deneyim sunar.

## 🚀 Kullanılan Teknolojiler ve Mimari

* **Arayüz & Çerçeve:** Flutter & Dart (Aydınlık & Renkli Tema)
* **Yapay Zeka (LLM):** Google Gemini API (`gemini-2.5-flash`)
* **Görsel Üretimi:** Pollinations.ai (Flux Model)
* **Sohbet Arayüzü:** `dash_chat_2`
* **Durum Yönetimi:** Riverpod (Altyapısı hazırlandı)
* **Veri Kalıcılığı:** `shared_preferences` (Oyun içi Save/Load sistemi)
* **Erişilebilirlik & Ses:** `flutter_tts` (Metin Okuma) ve `speech_to_text` (Sesli Komut)
* **Görsel Efektler:** `shimmer` (Yükleme animasyonları) ve `animated_text_kit` (Daktilo efekti)
* **Raporlama:** `pdf` ve `printing` (Çözülen vakaların PDF dökümü)

## 🎮 Temel Özellikler ve Oyun Mekanikleri

### 📜 Yapay Zeka Oyun Motoru ve JSON Haberleşmesi
Oyunun tüm akışı, Gemini API'ye entegre edilmiş katı bir "Sistem Talimatı" (System Instruction) şablonuna dayanır. Yapay zeka serbest metin üretmek yerine, mobil uygulamanın motoru tarafından güvenle ayrıştırılabilen bir JSON yapısı döndürür. Hikaye metni, görsel betimlemesi, oyuncu seçenekleri, eşya kazanımı ve can değişimi anlık olarak bu yapı üzerinden kontrol edilir.

### ❤️ Dinamik Can (Health) ve 💡 Akıllı İpucu (Hint) Sistemi
- Oyuncu maceraya 100 can puanı ile başlar. Yapılan seçimlerin tehlike düzeyine göre can puanı artabilir veya azalabilir.
- Oyuncu kritik anlarda tıkandığında 10 can feda ederek yapay zekadan duruma özel, üstü kapalı ve gizemli bir yönlendirme (ipucu) alabilir.

### 🎒 Dinamik Envanter ve 🧩 Mini Bulmacalar
- Kazanılan eşyalar otomatik olarak oyuncunun çantasına (envanterine) eklenir.
- Envanterde iki veya daha fazla eşya/ipucu biriktiğinde rastgele bir mini bulmaca tetiklenir ve oyuncudan parçaları birleştirip mantıklı bir sonuç çıkarması istenir.

### 🎙️ Gelişmiş Etkileşim ve UI/UX Animasyonları
- **Sesli Etkileşim:** Hikayeler TTS ile Türkçe seslendirilirken, oyuncu STT ile mikrofona konuşarak oyuna serbest metinle yön verebilir.
- **Daktilo Efekti:** Atmosferi güçlendirmek için yapay zekanın yanıtları harf harf ekrana yazdırılır.
- **Shimmer (Banyo) Efekti:** Görseller indirilirken ekranda *"📸 Sahne oluşturuluyor..."* animasyonu oynatılarak bekleme deneyimi optimize edilir.

### 💾 Yerel Veri Kalıcılığı (Save/Load)
- Her hamleden sonra can durumu, aktif envanter ve diyalog geçmişi `shared_preferences` kullanılarak yerel hafızaya kaydedilir. Oyuncu uygulamayı kapatıp açtığında maceraya kayıpsız bir şekilde kaldığı yerden devam edebilir.

### 📄 Vaka Raporu Dışa Aktarma (PDF Export)
- Çözülen vakalar ve diyaloglar tek bir tuşla, Türkçe karakter destekli şık bir PDF "Vaka Raporu"na dönüştürülür. Elde edilen belge, cihazın yerel paylaşım menüsü üzerinden (WhatsApp, E-posta vb.) başkalarıyla kolayca paylaşılabilir.

## 🔮 Gelecek Yol Haritası (Geliştirme Planı)
-Hikayedeki duygu durumuna göre (Gergil, Heyecanlı, Gizemli) değişen dinamik arka plan müzikleri (audioplayers entegrasyonunun genişletilmesi).
-Oyuncuların çözdükleri vakalara ve sergiledikleri performansa göre yarışacağı çevrimiçi Liderlik Tablosu (Leaderboard) entegrasyonu. 

## Görseller
<img width="336" height="600" alt="image" src="https://github.com/user-attachments/assets/df988821-4f91-4db0-a4ff-7033b72e9d63" />
<img width="338" height="598" alt="image" src="https://github.com/user-attachments/assets/985b008d-b673-4960-a2fb-77d908d2d1d4" />
<img width="337" height="596" alt="image" src="https://github.com/user-attachments/assets/b81a3570-f8e8-49ef-9d1f-78fd32c1b678" />
<img width="336" height="596" alt="image" src="https://github.com/user-attachments/assets/15e01866-6ee8-491c-a6cf-7586cc341742" />
<img width="339" height="595" alt="image" src="https://github.com/user-attachments/assets/3916fb88-2360-4081-ae2a-c3d0abb25012" />
<img width="338" height="600" alt="image" src="https://github.com/user-attachments/assets/73f6886a-0d0f-4ade-9e99-f46af4f8ddb1" />
<img width="335" height="597" alt="image" src="https://github.com/user-attachments/assets/677cbdee-1b47-4441-a50d-9ae206c2cd0d" />

## 📂 Proje Klasör Yapısı

Sorumlulukların ayrılması (Separation of Concerns) prensibine uygun olarak tasarlanan dizin yapısı:

```text
lib/
│
├── main.dart             # Uygulama giriş noktası, WelcomeScreen ve tema bağlayıcısı.
├── theme.dart            # Uygulamanın aydınlık, renkli ve dinamik tema konfigürasyonu.
├── game_screen.dart      # DashChat entegrasyonu, oyun mekanikleri, TTS/STT ve AI haberleşmesi.
└── pdf_service.dart      # Raporlama modülü, PDF oluşturma ve paylaşım servisi.


