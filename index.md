# 📊 Proyek UAS Data Mining  
## Deteksi DoS dan DDoS Attack Menggunakan Dataset Lalu Lintas Jaringan

---

## 🧠 Pendahuluan

Dalam era digital saat ini, serangan terhadap infrastruktur jaringan menjadi semakin kompleks dan sering terjadi. Salah satu jenis serangan yang umum adalah **Denial of Service (DoS)** dan **Distributed Denial of Service (DDoS)**. Keduanya bertujuan mengganggu layanan dengan cara membanjiri sistem target menggunakan trafik palsu dalam jumlah besar.

Proyek ini bertujuan untuk menganalisis dataset lalu lintas jaringan dan membangun sistem klasifikasi yang mampu mendeteksi berbagai jenis serangan DoS/DDoS. Melalui pendekatan data mining dan pembelajaran mesin (machine learning), sistem ini diharapkan dapat mengenali pola lalu lintas anomali secara otomatis dan akurat.

---

## 👥 Anggota Kelompok Data Mining - FTI UNPAM

- Aditya Eko Nugroho  
- Farid Mardan Aziz  
- Ma'ruf Nizar Fazari  
- Raden Aditya Rahmat  
- Zidan Faturrahman

---

## 📈 Distribusi Label Dataset (Simulasi)

Grafik berikut menggambarkan distribusi jumlah data per label (simulasi):

![Distribusi Label Simulasi](images/distribusi_label_simulasi_dos_ddos.png)

---

## 🔎 Ringkasan Dataset Per Jenis Serangan

### 📘 1. Benign Traffic
Lalu lintas jaringan **normal** tanpa aktivitas berbahaya. Ini menjadi dasar pembanding dalam klasifikasi.

**Ciri-ciri:**
- Komunikasi dua arah wajar (client-server)
- Tidak ada lonjakan paket mencurigakan
- Tidak mengandung aktivitas flooding

**Kegunaan:**
- Sebagai baseline model klasifikasi untuk mendeteksi anomali

---

### ⚠️ 2. DDoS ICMP Flood

Jenis serangan **DDoS (Distributed Denial of Service)** menggunakan paket ICMP dari **banyak sumber** (botnet) untuk membanjiri satu target.

![Distribusi DDoS ICMP Flood](images/ddos_icmp_flood.png)

**Ciri-ciri:**
- Sumber: Banyak IP berbeda
- Protokol: ICMP
- Serangan masif dalam waktu singkat

**Contoh:** Ping flood ke DNS Server dari jaringan botnet

**Kelebihan:**  
✅ Sulit difilter karena tersebar  
**Kekurangan:**  
❌ Butuh koordinasi botnet

---

### ⚠️ 3. DoS ICMP Flood

Serangan dari **satu sumber** menggunakan paket ICMP secara masif untuk menjatuhkan layanan.

![Distribusi DoS ICMP Flood](images/dos_icmp_flood.png)

**Ciri-ciri:**
- Sumber: 1 IP
- Protokol: ICMP (Echo Request)
- Volume tinggi, arah tunggal

**Contoh:** `ping -f` ke server aplikasi

**Kelebihan:**  
✅ Praktis, bisa dilakukan langsung  
**Kekurangan:**  
❌ Mudah diblok oleh firewall

---

### ⚠️ 4. DoS UDP Flood

Menargetkan **port acak** menggunakan protokol UDP, memicu sistem mengirim balasan ICMP unreachable.

![Distribusi DoS UDP Flood](images/dos_udp_flood.png)

**Ciri-ciri:**
- Sumber: 1 IP
- Protokol: UDP
- Menyerang port secara acak

**Contoh:** Menyerang VoIP server

**Kelebihan:**  
✅ Connectionless, cepat dijalankan  
**Kekurangan:**  
❌ Polanya dapat dibaca sistem

---

### ⚠️ 5. DDoS UDP Flood

Serangan UDP dalam skala besar dari **berbagai sumber** yang membanjiri sistem target hingga lumpuh.

![Distribusi DDoS UDP Flood](images/ddos_udp_flood.png)

**Ciri-ciri:**
- Sumber: Banyak IP
- Protokol: UDP
- Target: Port umum (53, 123, 80)

**Contoh:** Reflected attack terhadap DNS resolver

**Kelebihan:**  
✅ Mampu menjatuhkan sistem besar  
**Kekurangan:**  
❌ Dapat menghasilkan trafik balik berbahaya

---

## 📌 Kesimpulan

Setiap jenis serangan memiliki pola khas yang dapat dikenali menggunakan pendekatan supervised learning. Pemahaman mendalam terhadap dataset ini sangat krusial untuk membangun model klasifikasi yang akurat dan dapat digunakan dalam sistem deteksi intrusi jaringan (IDS).

---

## ✍️ Dokumentasi Tambahan

- Akan ditambahkan:
  - 📈 Confusion Matrix dan akurasi model
  - 📘 Ringkasan algoritma klasifikasi (KNN, Decision Tree)
  - 📥 Dataset lanjutan dan evaluasi

---

## 📚 Referensi

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Kaggle DDoS Dataset](https://www.kaggle.com/datasets)
- [Cloudflare - What is DDoS?](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/)

---

