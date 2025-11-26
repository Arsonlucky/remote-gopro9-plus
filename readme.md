# Firmware Remote GoPro

Ini adalah firmware untuk ESP32 yang berfungsi sebagai remote control untuk kamera GoPro HERO 9 dan model yang lebih baru. Kompatibilitas dengan GoPro HERO 13 belum diuji.

## Fitur Utama

*   **Kontrol Nirkabel**: Mengontrol start/stop perekaman GoPro melalui Bluetooth Low Energy (BLE).
*   **Antarmuka Web**: Dilengkapi dengan server web untuk konfigurasi, kontrol, dan melihat log secara real-time.
*   **Koneksi Otomatis**: Secara otomatis mencari dan terhubung kembali ke GoPro yang terakhir terhubung.
*   **Mode Pairing**: Memungkinkan pemasangan dengan kamera GoPro baru melalui antarmuka web.
*   **Pemicu Fisik**: Mendukung tombol fisik untuk memicu start/stop perekaman.
*   **Sistem Registrasi**: Perangkat harus diregistrasi menggunakan kunci unik untuk mengaktifkan fungsionalitas penuh, mencegah penggunaan yang tidak sah.
*   **Pembaruan OTA**: Mendukung pembaruan firmware Over-the-Air setelah perangkat terhubung ke jaringan Wi-Fi.

## Cara Penggunaan

### 1. Startup Pertama (Mode Registrasi)

1.  Nyalakan perangkat ESP32.
2.  Perangkat akan membuat Access Point (AP) Wi-Fi dengan nama **"GoPro Remote AP"**.
3.  Hubungkan ponsel atau laptop Anda ke jaringan Wi-Fi tersebut.
4.  Setelah terhubung, portal captive akan secara otomatis membuka halaman web registrasi. Jika tidak, buka browser dan kunjungi alamat `192.168.4.1`.
5.  Halaman akan menampilkan kode generator perangkat. Gunakan alamat ini untuk menghasilkan **Kunci Registrasi** dengan mengirim whatsapp pada web.
6.  Masukkan kunci yang valid dan klik "Register". Perangkat akan menyimpan status registrasi dan reboot.

### 2. Operasi Normal (Setelah Registrasi)

Setelah berhasil diregistrasi, fungsionalitas penuh akan aktif.

*   **Pairing GoPro**:
    *   Buka antarmuka web.
    *   Klik tombol (pair new gopro). Ini akan menghapus informasi GoPro lama dan memulai pemindaian untuk kamera baru.
    *   Atur GoPro Anda ke mode "Pairing" atau "Connect Device".
    *   Perangkat akan menemukan dan terhubung ke GoPro. Alamat GoPro akan disimpan secara otomatis untuk koneksi di masa mendatang.
*   **Kontrol via Web**:
    *   Gunakan tombol "Toggle Shutter" untuk memulai atau menghentikan perekaman.
    *   Gunakan tombol "Change Mode" untuk mengubah mode kamera (misalnya ke mode video).
    *   Status koneksi, status perekaman, dan level baterai GoPro akan ditampilkan di antarmuka.
*   **Kontrol via Tombol Fisik**:
    *   Tekan tombol fisik yang terhubung ke pin yang telah dikonfigurasi untuk memulai atau menghentikan perekaman.

Semua pengaturan pin dapat diatur pada webserver perangkat.

## Tampilan Antarmuka

### Homepage Webserver
![Tampilan Homepage Webserver](./readme/Screenshot%202025-11-26%20at%202.51.47%20PM.png)


