# Quadriqa-Rover
# 🚀 ARC'26 / TEKNOFEST Otonom İKA - Team Quadriga Rover

Anatolian Rover Challenge (ARC'26) ve TEKNOFEST kapsamında finalist olarak yarışmaya hak kazanan, zorlu arazi koşullarında görev icra edebilmesi için geliştirilmiş otonom/uzaktan kontrollü İnsansız Kara Aracı (İKA) prototipidir. 

Bu depoda, aracın lokomotiv eyleyicileri, güç yönetimi izolasyonu ve distributed (merkeziyetsiz) kontrol mimarisine ait gömülü yazılım ve donanım lojikleri yer almaktadır.

---

## 🛠️ Teknik Özellikler & Donanım Mimarisi

- **Mekanik & Mobilite:** High-torque RS775 motorlar ile desteklenmiş robust 4x4 yürüyen aksam sistemi.
- **Merkeziyetsiz Kontrol Mimarisi (Decentralized Control):** Klasik tek bir merkezi kontrolcü yerine, her bir tekerlek için bağımsız **ESP32 Node**'ları ve BTS7960 motor sürücüleri konumlandırılmıştır. Bu sayede anlık tork vektörlemesi (Instant Torque Vectoring) ve zero-radius (olduğun yerde) dönüş kabiliyeti sağlanmıştır.
- **Yedeklilik (Redundancy):** Her tekerlek bağımsız bir düğüm (node) olarak çalıştığı için, olası bir donanım/sürücü arızasında sistem hatayı tolore ederek hareketine devam edebilir.
- **Haberleşme Katmanları:** Yüksek bant genişliği gerektiren AI video akışları için Ubiquiti AirMax şebekesi; telemetri ve kritik kontrol verileri için ise legal 868 MHz bandında çalışan **RFD 868X** modem mimarisi kullanılmıştır.
- **Güç Yönetimi & İzolasyon:** Motorların oluşturduğu tehlikeli voltaj sıçramalarını (voltage spikes) lojik devrelere yansıtmamak adına 3 alt sistem izolasyonu yapılmıştır. XT90 anti-spark konnektörler ve 300W buck konnektörler ile Nvidia Jetson Orin ve Pixhawk birimleri için kararlı lojik voltaj beslemesi sağlanmıştır.
- **Algılama & Otonomi:** Çevre analizi ve engel tespiti için özelleştirilmiş **YOLO V11** modeli, Nvidia Jetson Orin üzerinde çalışmaktadır. Gece görevlerinde softwaredriven exposure enhancement özellikli starlight kamera entegrasyonu mevcuttur.

---

## 💻 Kullanılan Teknolojiler ve Protokoller

- **Diller & Platformlar:** C/C++ (Arduino framework / ESP-IDF mantığı), ROS2, MATLAB/Simulink
- **Haberleşme:** I2C, SPI, UART, RTSP / RSCP (Video stream)
- **Alt Seviye Kontrol:** Pixhawk (ArduPilot - 400 Hz low-level motion loop) + Distributed ESP32 Nodes

---

## 📂 Depo İçeriği (Repository Structure)

- `/src`: ESP32 mikrodenetleyicileri için yazılmış alt seviye kontrol, tork vektörleme ve eyleyici kodları.
- `/hardware`: KiCad şematik çıktıları, güç dağıtım mimarisi blok şemaları ve donanım izolasyon şeması.
- `/telemetry`: Ground station (Yer istasyonu) ile kurulan haberleşme ve telemetri lojikleri.

---

## 🎬 Kalifikasyon Videomuz

Aracın saha testlerini, mekanik dayanım süreçlerini ve teknik detaylarının anlatımını içeren **ARC'26 Kalifikasyon Videomuzu** aşağıdaki bağlantıdan izleyebilirsiniz:

📺 [ARC'26 VPR: Kapsül Ai-Lab Quadriga Rover Team](https://www.youtube.com/watch?v=PGwKUAU1WMQ)

---

## 👤 İletişim

- **Geliştirici:** Çağlar Özcine
- **LinkedIn:** [www.linkedin.com/in/çağlar-özçine-332b5239a](https://www.linkedin.com/in/%C3%A7a%C4%9Flar-%C3%B6z%C3%A7ine-332b5239a)
- **E-Posta:** +90 534 783 47 20
