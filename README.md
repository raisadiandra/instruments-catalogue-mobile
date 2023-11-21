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

## Jawaban Tugas 9

1. Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?
    Kita bisa melakukan pengambilan data JSON tanpa membuat model terlebih dahulu. Namun, untuk yang mana yang lebih baik, tergantung dengan kebutuhan kita. Apabila kita butuh dengan cepat dan sederhana serta hanya untuk sementara, kita bisa tidak menggunakan model. Namun, apabila kita mau agar proyek terstruktur dengan jelas dan bisa dikembangkan lebih lanjut, lebih baik menggunakan model.

2. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.
    CookieRequest berfungsi untuk melakukan manajemen cookie mengenai data sementara yang akan disimpan. CookieRequest harus dibagikan ke seluruh komponen di aplikasi karena cookie harus disimpan untuk seluruh halaman dan mengurangi meminta ulang autentikasi.

3. Jelaskan mekanisme pengambilan data dari JSON hingga dapat ditampilkan pada Flutter.
    Pertama dilakukan ambil data dari JSON. Setelah itu, dilakukan konversi data dari bentuk JSON menjadi struktur Dart. Kemudian, data dapat ditampilkan di Flutter dengan cara menambahkan widget baru untuk menampilkan data.

4. Jelaskan mekanisme autentikasi dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.
    Pertama, pengguna dapat melakukan input data akun pada Flutter, kemudian aplikasi Flutter akan membuat permintaan HTTP ke endpoint Django yang mengurus pendaftaran akun baru. Kemudian, Django akan menyimpan data akun baru pada database. Setelah itu, pengguna dapat melakukan login pada Flutter dan Flutter akan membuat permintaan kembali kepada Django. Setelah mendapat autentikasi dari Django, aplikasi Flutter dapat menampilkan menu.

5. Sebutkan seluruh widget yang kamu pakai pada tugas ini dan jelaskan fungsinya masing-masing.
    - Provider: menyediakan instance CookieRequest.
    - FutureBuilder: menangani pemanggilan asinkronus ke JSON.
    - CookieRequest: mengelola cookie yang digunakan.    

6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).
    - Memastikan deployment proyek tugas Django kamu telah berjalan dengan baik.
        Setelah menyelesaikan tugas ini, saya melakukan push kembali ke directory GitHub instruments-catalogue dan otomatis ter-deploy.
    - Membuat halaman login pada proyek tugas Flutter.
        Pertama saya membuat aplikasi baru pada Django dengan nama authentication. Dalam views di authentication, saya membuat fungsi login yang meminta username dan password serta melakukan return berbentuk JsonResponse. Fungsi tersebut juga ditambahkan path-nya di urls.py. Kemudian, di Flutter, saya membuat page untuk login dan memasukkan kode untuk login. Dilakukan pula integrasi agar Flutter dan Django tersambung.
    - Mengintegrasikan sistem autentikasi Django dengan proyek tugas Flutter.
        Saya melakukan instalasi provider dan package pbp_django_auth. Di main, saya menambahkan kode untuk CookieRequest agar bisa digunakan.
    - Membuat model kustom sesuai dengan proyek aplikasi Django.
        Dilakukan konversi kode menggunakan Quicktype dan kode hasil konversi tersebut dimasukkan ke dalam product.dart agar menjadi model dalam aplikasi Flutter.
    - Membuat halaman yang berisi daftar semua item yang terdapat pada endpoint JSON di Django yang telah kamu deploy.
        Pertama dilakukan fetch data dari halaman Django. Fetch dilakukan dengan cara menggunakan async dan await hingga data didapatkan. Model yang telah dibuat dapat digunakan sehingga dilakukan impor dari product.dart pada file-file yang sudah digunakan. Kemudian, dibuat file baru bernama list_product.dart untuk menampilkan data dan dimasukkan kode. Kode di left_drawer dan shop_card juga ditambahkan agar halaman list_product dapat diakses.