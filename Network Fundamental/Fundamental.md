## 🌐 Network Fundamentals: The Core of Connectivity
Welcome to the Network Fundamentals repository. This documentation is designed to be a comprehensive guide and learning journal on the fundamentals of computer networking—from how data moves between devices to the protocols that maintain the security and integrity of that information.

"Networking isn't just about connecting computers; it's about connecting people and ideas through a reliable and secure infrastructure."

🌐 Network Fundamentals: Deep Dive into OSI & TCP/IP

Dokumentasi ini berisi catatan komprehensif mengenai dasar-dasar jaringan komputer, yang berfokus pada pemetaan antara **OSI Model, PDU, dan TCP/IP Model.

---

## 🗺️ Perbandingan Arsitektur Jaringan

<img width="1093" height="609" alt="Network Fundamental" src="https://github.com/user-attachments/assets/ee3a39fb-53da-4a5b-8f6b-35a06bece2b7" />
Gambar Dibuat menggunakan: Excalidraw.com


## 🔍 Penjelasan Detail Per Bagian

### 1. The OSI Model (The "Map")
Model OSI membagi proses komunikasi menjadi 7 lapisan diskrit untuk memudahkan standarisasi.

* **Upper Layers (5, 6, 7):** Berfokus pada interaksi pengguna, format data (seperti enkripsi SSL/TLS), dan pengelolaan sesi aplikasi.
* **Transport Layer (4):** Penanggung jawab koneksi *end-to-end*. Di sini ditentukan apakah pengiriman bersifat reliabel (**TCP**) atau cepat (**UDP**).
* **Lower Layers (1, 2, 3):** Berfokus pada pengiriman data lintas jaringan. Melibatkan alamat logika (IP), alamat fisik (MAC), dan media transmisi kabel/nirkabel.

### 2. PDU - Protocol Data Unit (The "Package")
PDU menjelaskan bagaimana bentuk data berubah melalui proses **Enkapsulasi**.

* **Data:** Informasi murni dari aplikasi (misal: isi pesan chat).
* **Segment / Datagram:** Data yang sudah diberi nomor urut dan port. 
    * *Segment* digunakan untuk **TCP**.
    * *Datagram* digunakan untuk **UDP**.
* **Packet:** Data yang sudah diberi label alamat IP (Sumber & Tujuan).
* **Frame:** Data yang dibungkus dengan MAC Address untuk dikirim oleh Switch.
* **Bit:** Bentuk akhir berupa sinyal elektrik (0 dan 1) yang mengalir di kabel.

### 3. TCP/IP Model (The "Real World")
Ini adalah protokol yang digunakan internet secara nyata. Lebih sederhana dari OSI:

* **Application Layer:** Menggabungkan fungsi *Application, Presentation,* dan *Session* menjadi satu. Langsung menangani protokol seperti HTTPS, FTP, dan DNS.
* **Transport Layer:** Mengatur komunikasi antar aplikasi menggunakan port (misal: Port 80 untuk HTTP).
* **Internet Layer:** Bertanggung jawab atas *routing* paket menggunakan protokol IP.
* **Link Layer:** Menangani semua aspek fisik dan koneksi hardware dalam satu lapisan.

---

## 🛠️ Network Components & Protocols

| Layer | Protocols | Hardware / Examples |
| :--- | :--- | :--- |
| **Application** | HTTP, HTTPS, SFTP, DNS | Browser, Email Client |
| **Transport** | TCP, UDP | Ports (80, 443, 22) |
| **Network** | IPv4, IPv6, ICMP | Router, L3 Switch |
| **Data Link** | Ethernet, ARP | Switch, Bridge, NIC |
| **Physical** | DSL, IEEE 802.11 | Fiber Optic, UTP Cable |

---

## ⚙️ Daftar Port Jaringan Paling Penting

| Nomor Port | Protokol | Layanan | Deskripsi |
| :--- | :--- | :--- | :--- |
| 20, 21 | TCP | FTP | Transfer file (Data dan Kontrol) |
| 22 | TCP | SSH / SFTP | Akses remote aman dan transfer file terenkripsi |
| 23 | TCP | Telnet | Akses remote tanpa enkripsi (tidak aman) |
| 25 | TCP | SMTP | Pengiriman email antar server |
| 53 | UDP/TCP | DNS | Penerjemahan nama domain ke alamat IP |
| 67, 68 | UDP | DHCP | Pemberian alamat IP secara otomatis |
| 80 | TCP | HTTP | Akses web tanpa enkripsi |
| 110 | TCP | POP3 | Pengambilan email dari server ke perangkat |
| 143 | TCP | IMAP | Sinkronisasi email di beberapa perangkat |
| 443 | TCP | HTTPS | Akses web dengan enkripsi aman (SSL/TLS) |
| 3389 | TCP | RDP | Protokol Remote Desktop Windows |

---

