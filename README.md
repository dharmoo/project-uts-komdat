# PairDrop

<span style="font-size: 16px; font-style: bold;">This is a custom-sized heading.</span>

<span align="center"><img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/android-chrome-512x512.png?raw=true" alt="PairDrop" width="400" height="400"></span>

## Brief Overview

[PairDrop](https://pairdrop.net) merupakan Web App yang berfungsi sebagai media transfer data antarperangkat digital. WebApp ini terinspirasi dari [SnapDrop](https://snapdrop.net) (now defunct) dan juga AirDrop (yang hanya dapat diakses oleh perangkat Apple). PairDrop diciptakan sebagai WebApp alternatif yang bersifat Open Source dan juga menjunjung tinggi konsep Self Hosting oleh penggunanya. Beberapa fitur utama dari PairDrop antara lain:
- Menghubungkan beberapa gawai dalam jaringan lokal yang sama
  - Dua atau lebih perangkat dapat saling dihubungkan dalam proses transfer data secara lokal.
- Menghubungkan dua gawai secara permanen
  - Dua perangkat dapat dihubungkan dengan sebuah kode untuk mempermudah proses transfer data yang berkelanjutan.
- Menciptakan ruang publik yang dapat digunakan sebagai tempat transfer data
  - Pengguna dapat menciptakan ruang publik khusus di mana pengguna perangkat lain yang diundang dapat masuk dan melakukan transfer data.

## Instalasi

### Prasyarat Instalasi

Berikut ini adalah beberapa program yang harus disediakan terlebih dahulu sebelum melakukan proses instalasi PairDrop
  - Virtual Machine   
  - Docker  

### Langkah-langkah Instalasi

1. Lakukan proses Log-in ke dalam SSH:  
    ```
    $ ssh username@hostname_or_IP
    ```  
2. Lakukan proses instalasi Docker dan juga cloning terhadap Repo PairDrop:  
    ```
    $ git clone https://github.com/schlagmichdoch/PairDrop.git
    $ cd PairDrop
    ```  
3. Lakukan perubahan ke dalam file docker-compose.yml:  
   ```
   import http.server
   import socketserver

   PORT = 80

   Handler = http.server.SimpleHTTPRequestHandler

   with socketserver.TCPServer(("0.0.0.0", PORT), Handler) as httpd:
   	print("Server started on port", PORT)
   	httpd.serve_forever()
   ```  
4. Jangan lupa untuk jalankan command ini agar DropPair dapat dideploy:  
   ```
   $ sudo docker compose up -d
   ```  
5. Cek apakah docker berhasil dijalankan:  
   ```
   $ sudo docker ps
   ```  

## Cara Pemakaian

Untuk mulai menggunakan PairDrop, pengguna dapat mengklik link [berikut](https://ipb.link/komunikasi-lucu). Setelah pengguna mengklik link tersebut, akan muncul tampilan layar PairDrop sebagai berikut:

<p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/mainroom.png" alt="homepage" width="750" style="display: block; margin: 0 auto;">
</p>

Setelah masuk, pengguna dapat melakukan transfer data dengan perangkat lain dengan beberapa metode sesuai dengan kebutuhan serta kondisi perangkat dan juga jaringan pengguna:
### Melakukan transfer data antarperangkat dalam sebuah jaringan lokal:  
   Langkah 1: Pastikan bahwa kedua perangkat telah terhubung ke dalam jaringan yang sama.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/samenetwork.png" alt="samnetwork" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 2: Untuk mempermudah proses pencarian perangkat, pengguna dapat mengubah nama display perangkat (opsional).  
    <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/changename.png" alt="changename" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 3: Klik pada perangkat yang ingin dikirimi data.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/clickonuser.png" alt="click" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 4: Upload dan kirim file yang akan dikirim.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/sendpic.png" alt="upload" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 5: Pada perangkat penerima, klik Accept untuk mendownload file. 
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/receive.jpg" alt="receive" width="300" style="display: block; margin: 0 auto;">
    </p>

    
### Menghubungkan dua perangkat secara permanen untuk transfer data:  
   Langkah 1: Pastikan bahwa kedua perangkat masuk ke laman utama PairDrop. 
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/samenetwork.png" alt="samnetwork" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 2: Klik tombol rantai yang ada di bagian kanan atas laman.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/chain.png" alt="chain" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 3: Pengguna dapat memasukkan kode atau meng-scan kode QR yang ada di perangkat yang ingin dihubungkan.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/pair.png" alt="pair" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 4: Klik pada perangkat yang ingin dikirimi data.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/click-pair.png" alt="click" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 5: Upload file yang akan dikirim.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/upload.png" alt="upload" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 6: Pada perangkat penerima, klik Accept untuk mendownload file.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/sent.jpg" alt="accept" width="300" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 7: Untuk memutus hubungan, klik unpair pada perangkat yang ingin diputus hubungannya.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/unpair.png" alt="unpair" width="700" style="display: block; margin: 0 auto;">
    </p>

    
### Menciptakan ruang publik untuk kebutuhan transfer data:  
   Langkah 1: Pastikan bahwa kedua perangkat masuk ke laman utama PairDrop.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/samenetwork.png" alt="samnetwork" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 2: Klik tombol contact yang ada di bagian kanan atas laman.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/share2.png" alt="sharebutton" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 3: Satu atau lebih pengguna dapat memasukkan kode atau meng-scan kode QR yang ada di perangkat utama untuk dapat masuk ke dalam ruang publik temporari.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/qrshare.png" alt="qrshare" width="700" style="display: block; margin: 0 auto;">
    </p>

   Langkah 4: Untuk mempermudah proses pencarian perangkat, pengguna dapat mengubah nama display perangkat (opsional).  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/share.png" alt="changename" width="700" style="display: block; margin: 0 auto;">
    </p>
   
   Langkah 5: Klik pada perangkat yang ingin dikirimi data.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/clickon.png" alt="clickondevice" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 6: Upload file yang akan dikirim.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/apu.png" alt="upload" width="700" style="display: block; margin: 0 auto;">
    </p>
    
   Langkah 7: Pada perangkat penerima, klik Accept untuk mendownload file.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/apureceived.jpg" alt="received" width="300" style="display: block; margin: 0 auto;">
    </p>
   
   Langkah 8: Untuk memutus hubungan, klik unpair pada perangkat yang ingin diputus hubungannya.  
   <p align="center">
  <img src="https://github.com/dharmoo/project-uts-komdat/blob/main/images/leave.png" alt="leave" width="700" style="display: block; margin: 0 auto;">
    </p>

## Pembahasan

Penjelasan terkait kelebihan dan juga kekurangan dari WebApp PairDrop ialah sebagai berikut:  

### Kelebihan PairDrop

Terdapat cukup banyak hal positif yang menjadikan PairDrop pilihan alternatif yang baik untuk dijadikan media transfer data sederhana. Beberapa kelebihan tersebut ialah sebagai berikut:  
  - Sifat PairDrop yang sangat terbuka terhadap prinsip Open Source dan juga Self-Hosting.  
  - User Experience yang jelas dan tidak membingungkan, dengan tampilan yang sederhana.  
  - Terdapat banyak cara untuk menghubungkan dua perangkat (Membuat Public Room, Menghubungkan Perangkat secara Permanen dengan Kode, dan juga Menghubungkan Perangkat dalam Jaringan yang Sama). Hal ini memungkinkan bagi pengguna untuk menyesuaikan metode koneksi yang sesuai dengan kebutuhan dan juga kondisi yang ada.
  - Terdapat banyak fitur yang meningkatkan Quality of Life (QoL) seperti Dark Mode, Multilingual, dan juga Notifikasi perangkat. 

### Kekurangan PairDrop

Meskipun ada banyak hal positif dalam WebApp PairDrop, kami masih menemukan beberapa kekurangan ataupun limitasi yang diharapkan dapat diperbaiki oleh pihak pengembang. Kekurangan-kekurangan tersebut ialah sebagai berikut: 
  - Perangkat Apple masih belum dapat dihubungkan dengan perangkat Non-Apple. Hal ini mengakibatkan proses transfer data antara kedua perangkat tidak mungkin terjadi.
  - Kecepatan proses pendeteksian perangkat dalam sebuah jaringan masih dapat ditingkatkan kembali.


Selanjutnya, jika dibandingkan dengan WebApp lain yang menjadi inspirasi dari dibuatnya PairDrop (AirDrop dan juga SnapDrop), terdapat beberapa perbedaan fundamental antara ketiga WebApp ini.

### Perbandingan dengan AirDrop

Perbedaan utama antara PairDrop dan juga AirDrop yang dimiliki oleh Apple ialah dari tingkat kompatibilitasnya. Berbeda dengan AirDrop yang dikhususkan untuk perangkat Apple saja, PairDrop dapat diakses dan digunakan oleh hampir semua perangkat. Sama seperti dengan sistem AirDrop, PairDrop juga dapat menghubungkan antara handphone dengan laptop ataupun PC. Hal ini menunjukkan bahwa sebenarnya kinerja dari PairDrop sangatlah mirip dengan AirDrop, dengan perbedaan utamanya yang terletak di metode connect PairDrop yang lebih beragam.

### Perbandingan dengan SnapDrop

Mengingat proses development PairDrop yang terinspirasi dari SnapDrop, maka dapat dikatakan bahwa ada banyak aspek (mulai dari skema warna, UX, fitur, hingga sifatnya yang Open Source) yang mirip dengan SnapDrop. Namun, jika diperhatikan secara saksama, masih ada beberapa perbedaan fitur yang membuat PairDrop (menurut kami) lebih nyaman untuk digunakan dibandingkan dengan SnapDrop. Perbedaan-perbedaan tersebut ialah sebagai berikut:  
  - Keterbukaan PairDrop terhadap prinsip Self-Hosting.  
  - Terdapat fitur untuk mengganti bahasa dari tampilan PairDrop.  
  - Terdapat fitur untuk menampilkan notifikasi apabila ada perangkat lain yang ingin terhubung.  
  - Terdapat lebih banyak cara untuk menghubungkan dua perangkat (Membuat Public Room, Menghubungkan Perangkat secara Permanen dengan Kode, dan juga Menghubungkan Perangkat dalam Jaringan yang Sama).  

## Referensi

Cantumkan tiap sumber informasi yang anda pakai.
