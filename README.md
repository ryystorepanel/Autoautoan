# Autoautoan - Kumpulan Skrip Setup VPS

Repositori ini berisi kumpulan skrip untuk otomatisasi setup server VPS. Skrip ini dirancang untuk mempermudah instalasi berbagai layanan VPN dan tools pendukung lainnya, semuanya dikelola dari satu sumber.

---

## ## Prasyarat

Sebelum memulai, pastikan Anda memiliki:
* Server VPS baru (**Fresh Install** sangat direkomendasikan).
* Sistem Operasi: **Debian 10/11** atau **Ubuntu 20.04/22.04**.

---

## ## Instalasi

Ada beberapa cara untuk menginstal skrip dari repositori ini, tergantung pada kebutuhan Anda.

### ### Instalasi Utama (One-Liner)

Ini adalah perintah utama untuk menjalankan setup lengkap. Perintah ini akan memperbarui server, menginstal dependensi yang diperlukan, dan menjalankan skrip `setup.sh` utama.

Salin dan jalankan seluruh baris perintah di bawah ini di terminal VPS Anda:

```bash
apt update && apt upgrade -y && apt install -y build-essential jq shc bzip2 gzip coreutils screen curl && wget [https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/setup.sh](https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/setup.sh) && chmod +x setup.sh && ./setup.sh
```

---

### ### Instalasi Skrip Tambahan (Manual)

Jika Anda hanya ingin menginstal komponen tertentu, Anda bisa menggunakan perintah-perintah di bawah ini secara terpisah.

#### **Menjalankan `install.sh`**
Metode alternatif untuk instalasi cepat.
```bash
wget -qO- [https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install.sh](https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install.sh) | bash
```

#### **Setup Skrip `xray-cleanup`**
Menginstal skrip untuk membersihkan log Xray secara otomatis.
```bash
wget -O /usr/local/bin/xray-cleanup [https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/xray-cleanup-telegram.sh](https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/xray-cleanup-telegram.sh)
chmod +x /usr/local/bin/xray-cleanup
```

#### **Setup `apiserver`**
Menginstal skrip untuk API server.
```bash
wget -q [https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install/apiserver](https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install/apiserver) && chmod +x apiserver && ./apiserver apisellvpn
```

---

## ## Setelah Instalasi

Setelah proses instalasi selesai dan server mungkin melakukan reboot, Anda dapat mengakses panel menu utama dengan mengetik perintah:

```
menu
```

---

## ## Konten Repositori

Pastikan file-file berikut ada di dalam repositori ini agar instalasi berjalan dengan benar:
* `setup.sh`: Skrip instalasi utama.
* `install.sh`: Skrip instalasi alternatif.
* `xray-cleanup-telegram.sh`: Skrip untuk membersihkan log Xray dengan notifikasi Telegram.
* `install/apiserver`: Skrip untuk setup API server.
* *(dan file-file lain yang dipanggil oleh `setup.sh`)*
