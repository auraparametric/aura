# λ AURA - Parametrik Hoparlör Projesi
**Geliştirici:** Mert Emir Gültekin
**Versiyon:** Prototype MK-1
AURA, standart hoparlörlerin aksine sesi her yöne dağıtmak yerine, lazer ışını gibi dar ve yönlü bir sütun halinde ileten **ultrasonik parametrik ses** projesidir. Sadece cihazın tam karşısında duran kişi sesi duyabilir, etraftakiler sessizlikle baş başa kalır.
## 🚀 Vizyon ve Kullanım Alanları
*   **Akıllı Tahtalar ve Okullar:** Sınıflardaki akıllı tahtalara entegre edildiğinde, tahtadan çıkan eğitim materyalinin sesi sadece o sınıfta kalır. Sınıf kapısı açık olsa dahi ses koridora veya yan sınıflara taşmaz, mükemmel bir akustik izolasyon sağlanır.
*   **Bankamatikler (ATM):** Tuş ve yönlendirme sesleri yalnızca işlem yapan müşteriye ulaşır, arkada bekleyenler duymaz. Maksimum gizlilik ve güvenlik sunar.
*   **Self Servis Kasalar:** Marketlerdeki birden fazla self servis kasanın yarattığı gürültü kirliliğini engeller. "Bip" sesleri ve anonslar sadece o kasayı kullanan kişiye iletilir.
*   **Müzeler ve Sanat Galerileri:** Ziyaretçiler eserlerin karşısına geçtiklerinde rehberlik sesini duyarlar. Yan yana duran eserlerin sesleri birbirine karışmaz, kulaklık takma zorunluluğu ortadan kalkar.
## 🧠 Nasıl Çalışır?
AURA, insan kulağının duyamayacağı 40kHz'lik (ultrasonik) bir taşıyıcı dalga kullanır.
1.  **DDS (Direct Digital Synthesis):** ESP32 tabanlı Deneyap Kart'ın donanımsal timer'ları (LEDC) ile 40kHz'lik kusursuz bir PWM taşıyıcı dalga üretilir.
2.  **AM Modülasyonu:** 16kHz formatındaki dijital ses verisi (PCM), bu 40kHz'lik sessiz taşıyıcı dalganın üzerine Duty Cycle genlik modülasyonu (AM) ile bindirilir.
3.  **Güçlendirme ve Yayılım:** Modüle edilmiş sinyal **TC4427** Dual MOSFET sürücü entegresi ve LC rezonans bobinleri ile güçlendirilerek **14 adet** (1x7 sol, 1x7 sağ) ultrasonik transdüsere aktarılır.
4.  **Doğrusal Olmayan Akustik (Nonlinear Acoustics):** Ultrasonik dalgalar havada ilerlerken havanın kendi fiziksel direnci nedeniyle parçalanır. Bu fiziksel deformasyon, taşıyıcı dalganın içindeki "asıl duyulabilir sesi" havada, tam dinleyicinin önünde ortaya çıkarır.
