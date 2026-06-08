# 🎯 FocusBox

FocusBox, öğrencilerin ve çalışanların dikkat dağıtıcı unsurlardan uzaklaşarak daha verimli çalışma alışkanlıkları geliştirmelerine yardımcı olmak amacıyla geliştirilmiş Arduino tabanlı akıllı odaklanma kutusudur.

Kullanıcı belirlediği süre boyunca telefonunu veya dikkatini dağıtan diğer nesneleri kutu içerisine yerleştirir. Sistem, RFID kart doğrulaması sonrasında kutuyu kilitler ve belirlenen süre sona erene kadar açılmasını engeller. Süre tamamlandığında kullanıcı görsel ve işitsel olarak bilgilendirilir ve kutu yeniden açılır.

---

## 🚀 Özellikler

* RFID tabanlı kullanıcı doğrulama
* Döner enkodör ile süre ayarlama
* LCD ekran üzerinden kullanıcı arayüzü
* Servo motor kontrollü kilitleme mekanizması
* Gerçek zamanlı geri sayım sistemi
* Süre sonunda sesli uyarı (Buzzer)
* Otomatik sistem sıfırlama
* Yetkisiz kartlara karşı erişim koruması

---

## 🛠️ Kullanılan Donanımlar

| Bileşen               | Açıklama               |
| --------------------- | ---------------------- |
| Arduino Uno R3        | Ana kontrol birimi     |
| RFID RC522            | Kart doğrulama sistemi |
| 16x2 I2C LCD          | Kullanıcı arayüzü      |
| SG90 Servo Motor      | Kilitleme mekanizması  |
| KY-040 Rotary Encoder | Süre ayarlama          |
| Aktif Buzzer          | Sesli uyarı sistemi    |
| Breadboard            | Prototipleme           |
| Jumper Kablolar       | Bağlantılar            |

---

## ⚙️ Çalışma Prensibi

1. Sistem açılır ve karşılama ekranı görüntülenir.
2. Kullanıcı rotary encoder ile odaklanma süresini belirler.
3. Süre onaylandıktan sonra sistem RFID kart bekleme moduna geçer.
4. Yetkili RFID kart okutulur.
5. Servo motor kutuyu kilitler.
6. Geri sayım başlar ve LCD ekranda görüntülenir.
7. Süre tamamlandığında buzzer çalışır.
8. Servo motor kilidi açar.
9. Sistem başlangıç ekranına dönerek yeni kullanım için hazır hale gelir.

---

## 🔌 Bağlantılar

### RFID RC522

| RC522 | Arduino Uno |
| ----- | ----------- |
| SDA   | D10         |
| SCK   | D13         |
| MOSI  | D11         |
| MISO  | D12         |
| RST   | D9          |
| 3.3V  | 3.3V        |
| GND   | GND         |

### LCD I2C

| LCD | Arduino Uno |
| --- | ----------- |
| SDA | A4          |
| SCL | A5          |
| VCC | 5V          |
| GND | GND         |

### Rotary Encoder

| Encoder | Arduino Uno |
| ------- | ----------- |
| CLK     | D2          |
| DT      | D3          |
| SW      | D4          |
| VCC     | 5V          |
| GND     | GND         |

### Servo Motor

| Servo  | Arduino Uno              |
| ------ | ------------------------ |
| Signal | D5                       |
| VCC    | 5V (Harici güç önerilir) |
| GND    | GND                      |

### Buzzer

| Buzzer | Arduino Uno |
| ------ | ----------- |
| +      | D6          |
| -      | GND         |

---

## 📚 Kullanılan Kütüphaneler

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <SPI.h>
#include <MFRC522.h>
#include <Servo.h>
```

---

## 🧪 Test Sonuçları

* RFID doğrulama sistemi başarılı şekilde çalışmaktadır.
* Yetkisiz kartlar sistem tarafından reddedilmektedir.
* Rotary encoder üzerinde değer atlama problemi gözlemlenmemiştir.
* Geri sayım sistemi `millis()` fonksiyonu kullanılarak kararlı şekilde çalışmaktadır.
* Süre sonunda buzzer ve servo motor senkronize olarak çalışmaktadır.
* Sistem tamamlanan her oturum sonunda otomatik olarak sıfırlanmaktadır.

---

## 💰 Proje Maliyeti

Toplam prototip maliyeti yaklaşık **600 TL**'dir.

---

## 🔮 Gelecek Geliştirmeler

* Mobil uygulama entegrasyonu
* Bluetooth bağlantısı
* Çalışma istatistiklerinin kaydedilmesi
* Bulut tabanlı veri takibi
* Çoklu kullanıcı desteği

---

## 👩‍💻 Geliştirici

**Merve Sarıkaya**

FocusBox, odaklanmayı artırmak ve dijital dikkat dağınıklığını azaltmak amacıyla geliştirilmiş bir mühendislik projesidir.

