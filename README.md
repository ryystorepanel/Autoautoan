# Autoautoan - Skrip Instalasi VPS

Repositori ini berisi kumpulan skrip untuk otomatisasi setup server VPS. Skrip ini dirancang untuk mempermudah instalasi berbagai layanan VPN dan tools pendukung lainnya.

---

## ## Prasyarat

Sebelum memulai, pastikan Anda memiliki:
* Server VPS baru (**Fresh Install** sangat direkomendasikan).
* Sistem Operasi: **Debian 10/11** atau **Ubuntu 20.04/22.04**.

---

## ## Instalasi

Salin perintah dari blok kode di bawah ini dan jalankan langsung di terminal VPS Anda.

### ### Instalasi Utama (One-Liner)

Perintah ini akan menjalankan setup lengkap, mulai dari update sistem hingga eksekusi skrip utama.

```bash
apt update && apt upgrade -y && apt install -y build-essential jq shc bzip2 gzip coreutils screen curl && wget https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/setup.sh https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/setup.sh && chmod +x setup.sh && ./setup.sh
```

---

### ### Instalasi Skrip Tambahan (Manual)

Gunakan perintah di bawah ini jika Anda hanya ingin menginstal komponen tertentu secara terpisah.

#### **Menjalankan `install.sh`**
```bash
wget -qO- https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install.sh https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install.sh | bash
```

#### **Setup Skrip `xray-cleanup`**
```bash
wget -O /usr/local/bin/xray-cleanup https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/xray-cleanup-telegram.sh https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/xray-cleanup-telegram.sh && chmod +x /usr/local/bin/xray-cleanup
```

#### **Setup `apiserver`**
```bash
wget -q https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install/apiserver https://raw.githubusercontent.com/ryystorepanel/Autoautoan/main/install/apiserver && chmod +x apiserver && ./apiserver apisellvpn
```

---

## ## Setelah Instalasi

Setelah proses instalasi selesai dan server mungkin melakukan reboot, Anda dapat mengakses panel menu utama dengan mengetik perintah:

```bash
menu
```
