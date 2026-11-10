# JEJAKIN - Kalkulator Emisi & Finansial Komuter UPI Bandung

JEJAKIN adalah aplikasi kalkulator berbasis web (*client-side*) yang dirancang untuk membantu mahasiswa dan civitas akademika Universitas Pendidikan Indonesia (UPI) Bandung dalam mengestimasi emisi karbon (CO₂), waktu tempuh perjalanan, dan biaya operasional komuter harian menuju kampus.

Aplikasi ini mengintegrasikan data karakteristik kemacetan koridor Kota Bandung (berdasarkan Google Maps Traffic Index) serta membandingkan biaya perjalanan kendaraan pribadi terhadap moda transportasi publik resmi di Bandung, yaitu **Trans Metro Pasundan (TMP / Teman Bus)** dan **Trans Metro Bandung (TMB)**.

---

## Fitur Utama

1. **Estimasi Jejak Karbon Multi-Moda**:
   - Menghitung emisi per perjalanan dan proyeksi tahunan untuk Sepeda Motor, Mobil Pribadi, Bus Kota, Kendaraan Listrik, dan Jalan Kaki/Sepeda.
   - Menggunakan faktor emisi IPCC dan Kementerian ESDM Republik Indonesia.

2. **Diferensiasi Waktu Tempuh Berbasis Kemacetan Bandung**:
   - Menghitung waktu tempuh spesifik tiap moda di jam sibuk berdasarkan data empiris TomTom & Google Maps lalu lintas Bandung:
     - Sepeda motor: ~23,5 km/jam (fleksibilitas manuver di kemacetan).
     - Mobil pribadi: ~16,3 km/jam (indeks kecepatan jam sibuk Bandung).
     - Bus kota / TMP: ~13,0 km/jam ditambah buffer waktu tunggu/headway.
     - Jalan kaki: ~4,5 km/jam.

3. **Komparasi Biaya Finansial & Penghematan Angkutan Umum**:
   - Menghitung konsumsi BBM dan biaya perjalanan harian, bulanan, serta per semester (16 minggu masa perkuliahan aktif).
   - Menyediakan perbandingan langsung dengan tarif angkutan umum Kota Bandung:
     - **Trans Metro Pasundan (TMP)**: Tarif Pelajar/Mahasiswa Rp2.000 (Umum Rp4.900).
     - **Trans Metro Bandung (TMB)**: Tarif Pelajar/Mahasiswa Rp2.000 (Umum Rp4.000).

4. **Widget Navigator Rute Google Maps Terintegrasi**:
   - Menyajikan kartu opsi rute langsung di dalam antarmuka web sesuai koridor asal komuter utama mahasiswa UPI (Sukajadi, Cibiru, Cimahi, Kopo, Buahbatu, Dago).
   - Menampilkan rute transit beserta nomor trayek bus resmi (misal: *Cicaheum - Ledeng*).
   - Pratinjau peta interaktif OpenStreetMap langsung di peramban.

5. **Privasi Penuh (Privacy by Design)**:
   - Seluruh kalkulasi diproses 100% di peramban pengguna (*client-side JavaScript*).
   - Data alamat dan kebiasaan perjalanan tidak disimpan di server mana pun.

---

## Struktur Berkas

```
transportasi_jejakin/
├── index.html        # Halaman utama aplikasi (production entry point)
├── Jejakin.html      # Berkas sumber aplikasi asli
├── vercel.json       # Konfigurasi routing & clean URLs untuk deployment Vercel
└── README.md         # Dokumentasi proyek
```

---

## Menjalankan Secara Lokal

Cukup jalankan server lokal sederhana menggunakan Python atau ekstensi Live Server:

```bash
# Menggunakan Python 3
python -m http.server 8000
```

Buka `http://localhost:8000` pada peramban web Anda.

---

## Kontribusi terhadap SDGs

Proyek ini mendukung pencapaian Sasaran Pembangunan Berkelanjutan (Sustainable Development Goals / SDGs):
- **SDG 3**: Kehidupan Sehat dan Sejahtera (Target 3.9 - Mengurangi dampak polusi udara terhadap kesehatan pernapasan).
- **SDG 11**: Kota dan Permukiman Berkelanjutan (Target 11.2 - Akses ke sistem transportasi umum yang terjangkau dan berkelanjutan).
- **SDG 13**: Penanganan Perubahan Iklim (Target 13.3 - Peningkatan literasi dan kesadaran mitigasi emisi gas rumah kaca).
- **SDG 7**: Energi Bersih dan Terjangkau (Target 7.3 - Efisiensi energi per kapita).
- **SDG 9**: Industri, Inovasi, dan Infrastruktur (Target 9.5 - Rekayasa prototipe berbasis sains terintegrasi).

