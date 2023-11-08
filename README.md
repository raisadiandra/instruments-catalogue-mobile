# Instruments Catalogue
Nama: Raisa Diandra Survijanto
NPM: 2206814545
Kelas: PBP E

## Jawaban Tugas 1

1. Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?
    State adalah data atau informasi yang digunakan pada aplikasi. Stateless widget adalah widget yang tidak punya state. Widget ini biasanya bersifat statis dan tidak menerima input. Sebagai contoh, terdapat tulisan yang tidak bisa dilakukan apa-apa dan hanya berfungsi untuk ditampilkan di halaman saja. Sementara itu, stateful widget adalah widget yang memiliki state. Widget ini lebih fleksibel terhadap perubahan sehingga biasanya digunakan untuk mengambil input. Sebagai contoh, terdapat tombol yang dapat ditekan dan akan melakukan hal lain.

2. Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.
    Berikut class yang ada serta widget yang digunakan pada tiap class:
    - MyApp
        - MaterialApp: struktur utama aplikasi
    - MyHomePage
        - Scaffold: sebagai kerangka dasar halaman
        - AppBar: menampilkan judul dan warna background
        - SingleChildScrollView: agar bisa di-scroll
        - GridViewCount: untuk menampilkan halaman dalam bentuk grid
    - ShopItem
    - ShopCard:
        - Material: mengatur latar belakang halaman seperti warna
        - InkWell: memberikan respons terhadap klik
        - SnackBar: menampilkan pesan semacam notifikasi ketika tombol diklik
        - Container: membungkus icon dan text
        - Icon: menampilkan icon
        - Text: menampilkan tulisan

3. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
    - Membuat sebuah program Flutter baru dengan tema inventory seperti tugas-tugas sebelumnya.
        Pertama saya melakukan flutter create instruments_catalogue. Kemudian saya masuk ke folder tersebut dan menghubungkan folder dengan repositori di GitHub. Kemudian saya melakukan konfigurasi enable web support. Setelah itu, saya merapikan struktur proyek dengan cara membuat file baru yaitu menu.dart dan memasukkan beberapa bagian kode dari main.dart ke dalam menu.dart. Saya juga melakukan import menu.dart pada main.dart agar fungsi dari menu.dart dapat terpakai di main.dart.
    - Membuat tiga tombol sederhana.
        Pertama saya menambahkan widget build di menu.dart dan mengatur agar tampilan menjadi stateless. Kemudian saya menambahkan class ShopItem untuk mendefinisikan tipe data yang akan pada list. Saya membuat list items berisi ShopItem dan di sana diatur tulisan serta logo yang akan muncul pada tombol. Tombol akan berbentuk card, jadi saya membuat class baru bernama ShopCard dan pada widget build-nya, saya tambahkan onTap() pada InkWell sehingga apabila tombol diklik, akan masuk ke dalam fungsi tersebut.
    - Memunculkan Snackbar.
        Pada fungsi onTap(), saya tambahkan hideCurrentSnackbar() apabila belum di-tap, dan showCurrentSnackbar() apabila di-tap, dan akan menampilkan tulisan yang diinginkan sesuai dengan tombol yang diklik.
    - (BONUS) Mengimplementasikan warna-warna yang berbeda untuk setiap tombol.
        Pada list items, untuk setiap item (untuk setiap tombol), saya mengubah warna dengan menggunakan Color.{warna}. Pada tugas ini, saya memberikan warna pink, purple, dan deepPurple untuk tombol-tombolnya.