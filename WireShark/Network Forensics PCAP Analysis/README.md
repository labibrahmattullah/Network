# Case Study 01: WordPress Authentication & Traffic Analysis

## 📌 Overview
This case study focuses on inspecting unencrypted HTTP traffic to identify credential exposure and analyze a potential authentication brute-force attempt targeting a WordPress CMS platform.

---

## 🛠️ Analysis Methodology & Steps

### 1. Packet Metadata & Capture Timeline
* **File Investigated:** `HTTP Traffic.pcapng`
* **Timestamp of First Frame:** May 31, 2016, 22:40:02.333 UTC
* **Network Topology Inferred:** * **Source Host (Client):** `10.0.0.10`
  * **Destination Host (Target Web Server):** `10.0.0.12`

### 2. Identifying Unencrypted Authentication (HTTP POST)
By filtering the HTTP traffic, a series of `POST` requests directed to the WordPress login endpoint were isolated:
* **Target URI:** `/WordPress/wp-login.php`
* **Protocol:** HTTP/1.1

Upon expanding the **HTML Form URL Encoded** layer of the packet packet, cleartext credentials were successfully extracted from the payload structure:
* **Form Item (`log`):** `admin`
* **Form Item (`pwd`):** `qwerty@13`
* **Form Item (`wp-submit`):** `Log In`
<img width="1918" height="490" alt="Screenshot 2026-04-30 195255" src="https://github.com/user-attachments/assets/a4aca42a-5bd0-483c-bddc-f43a054f50ac" />

> ⚠️ **Security Finding:** The transmission of credentials over plain HTTP (Port 80) exposes the session to credential harvesting and Man-in-the-Middle (MitM) sniffing attacks.

### 3. Stream Reconstruction & Server Response
Following the TCP/HTTP stream (`Stream Index: 1100`) reveals how the server processed this specific authentication attempt:

* **HTTP Response Code:** `HTTP/1.1 200 OK`
* **Server Banner:** `Apache/2.4.9 (Win32) PHP/5.5.12`
* **Set-Cookie Header observed:** `wordpress_test_cookie=WP+Cookie+check`

```http
GET /WordPress/wp-admin/images/wordpress-logo.svg?ver=20131107 HTTP/1.1
Referer: [http://10.0.0.12/WordPress/wp-login.php](http://10.0.0.12/WordPress/wp-login.php)
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) Chrome/42.0.2311.135 Safari/537.36 Edge/12.10240
Host: 10.0.0.12
