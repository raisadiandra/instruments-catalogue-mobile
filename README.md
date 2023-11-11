# Instruments Catalogue (Mobile)
Nama: Raisa Diandra Survijanto
NPM: 2206814545
Kelas: PBP E

## Jawaban Tugas 7

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

## Jawaban Tugas 8

1.  Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement(), disertai dengan contoh mengenai penggunaan kedua metode tersebut yang tepat!
    Navigator.push() digunakan untuk menambahkan routing baru ke stack yang dikelola oleh Navigator. Sementara itu, Navigator.pushReplacement() digunakan untuk menggantikan halamans saat ini dengan routing ke halaman baru. Contoh penggunaan push() adalah apabila halaman masih baru di awal, sementara pushReplacement() apabila hendak melakukan redirect.

2. Jelaskan masing-masing layout widget pada Flutter dan konteks penggunaannya masing-masing!
    - Align: mengatur posisi pada halaman.
    - AspectRatio: mengatur ukuran pada halaman.
    - Container: mengatur widget lain serta margin, padding, dan dekorasi.
    - ListView: menampilkan daftar elemen.
    - Stack: meletakkan elemen di atas elemen lain.
    - Column: menyusun widget secara vertikal.
    - Row: menyusun widget secara horizontal.
    - Scaffold: kerangka dasar aplikasi.

3. Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan jelaskan mengapa kamu menggunakan elemen input tersebut!
    - TextFormField: agar dapat meminta input yang dapat diketik (berupa tulisan).
    - ElevatedButton: agar dapat membuat button yang dapat diklik dan terjadi action berikutnya dengan dikliknya button.

4. Bagaimana penerapan clean architecture pada aplikasi Flutter?
    Clean architecture diterapkan agar aplikasi terorganisasi dan terstruktur sehingga mudah untuk diubah dan dipahami. Dalam tugas ini, digunakan dua folder yaitu screens dan widgets yang merupakan presentation layer dalam Flutter. Layer ini mengandung logika yang berkaitan dengan UI dan UX. Selain layer ini, ada juga layer domain, data, dan lain-lain.

5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial)
    - Membuat minimal satu halaman baru pada aplikasi, yaitu halaman formulir tambah item baru.
        Saya membuat file shoplist_form.dart untuk formulir. Kemudian saya menambahkan widget Scaffold yang digunakan sebagai formulir. Saya menambahkan variabel _formKey untuk key di class _ShopFormPageState dan memasukkan key ke dalam body dalam formulir.
        -  Memakai minimal tiga elemen input, yaitu name, amount, description. Tambahkan elemen input sesuai dengan model pada aplikasi tugas Django yang telah kamu buat.
            Dalam class _ShopFormPageState, saya menambahkan seluruh variabel yang akan saya gunakan sesuai dengan proyek di Django (name, amount, description, dan price). Kemudian, saya menambahkan Padding dalam widget Child dalam SingleChildScrollView, yang berfungsi untuk meminta input dengan text field.
        - Memiliki sebuah tombol Save.
            Saya menambahkan widget Align setelah seluruh Padding. Di sana, dibuat berjenis button dan memiliki tulisan "Save". Button bisa ditekan untuk memunculkan data sesuai input.
        - Setiap elemen input di formulir juga harus divalidasi.
            Validasi dilakukan dalam Padding. Input berupa String dan akan di-parse dulu menjadi tipe data yang sesuai, apabila sukses dapat tersimpan, apabila tidak berhasil atau text field kosong, akan menampilkan message error.
    - Mengarahkan pengguna ke halaman form tambah item baru ketika menekan tombol Tambah Item pada halaman utama.
        Pertama, class ShopItem dan ShopCard dipindahkan ke file shop_card.dart agar kode menjadi rapi. Kemudian, pada ShopCard, khususnya onTap(), apabila dibuat navigasi baru, apabila mengeklik "Tambah Produk", menggunakan pushReplacement(), akan melakukan redirect ke page ShopFormPage() untuk masuk ke halaman form.
    - Memunculkan data sesuai isi dari formulir yang diisi dalam sebuah pop-up setelah menekan tombol Save pada halaman formulir tambah item baru.
        Pada widget Align di shoplist_form.dart, pada SingleChildScrollView, dibuat child lagi, dan ditampilkan tulisan sesuai data input. Kemudian, apabila ditekan, menggunakan onPressed(), navigator akan melakukan pop() terhadap tulisan tersebut.
    - Membuat sebuah drawer pada aplikasi.
        Saya membuat file baru bernama left_drawer.dart untuk drawer. Dalam file tersebut, dibuat widget Drawer untuk menampilkan drawer. Dibuat juga ListTile untuk menampilkan halaman utama dan tambah produk. Dalam kedua ListTile tersebut, apabila ditekan, masuk ke fungsi onTap(), yang akan menggunakan pushReplacement() untuk melakukan routing ke MyHomePage() ke halaman utama dan ShopFormPage() ke halaman form. 