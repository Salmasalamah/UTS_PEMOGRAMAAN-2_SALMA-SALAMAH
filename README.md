# UTS_PEMOGRAMAAN-2_SALMA-SALAMAH
GITHUB SAYA BERMASALAH, UPLOAD MALAH KE AKUN LAIN (GABISA DI GANTI AKUN)<img width="293" height="476" alt="image" src="https://github.com/user-attachments/assets/fac0e9e3-ecbc-40ed-99b9-f696fed715e5" />

Bagian A – Teori
1. Perbedaan antara Cubit dan BLoC
Cubit dan BLoC (Business Logic Component) adalah dua pola manajemen state yang disediakan oleh package flutter_bloc, keduanya bertujuan memisahkan logika bisnis dari antarmuka pengguna (UI). Perbedaan mendasar terletak pada kompleksitas dan mekanisme perubahan state. Cubit lebih sederhana; ia hanya menggunakan fungsi emit(newState) untuk secara langsung mengeluarkan state baru, menjadikannya ideal untuk state yang mudah dan tidak memerlukan pemrosesan kompleks. Sebaliknya, BLoC menggunakan pola Event-to-State; ia menerima Events (add(event)), memprosesnya melalui fungsi handler, lalu mengeluarkan State baru. BLoC lebih cocok untuk logika yang rumit, membutuhkan middleware, atau alur state yang kompleks.

2. Pentingnya Pemisahan Model Data, Logika Bisnis, dan UI
Pemisahan antara Model Data (ProductModel), Logika Bisnis (CartCubit), dan Antarmuka Pengguna (UI/Widget) dikenal sebagai Arsitektur Berlapis dan merupakan praktik terbaik dalam pengembangan perangkat lunak, sesuai dengan prinsip Single Responsibility Principle (SRP). Pemisahan ini sangat penting untuk:

Kemudahan Pengujian (Testability): Logika bisnis (Cubit) dapat diuji secara independen (Unit Testing) tanpa perlu merender UI.

Kemudahan Pemeliharaan (Maintainability): Perbaikan bug atau pembaruan aturan bisnis dapat dilakukan di CartCubit tanpa merusak tampilan.

Skalabilitas (Scalability): Memungkinkan proyek tumbuh besar secara terstruktur dan menghindari spaghetti code (kode yang campur aduk).

3. Tiga State yang Mungkin Digunakan dalam CartCubit
Dalam konteks aplikasi keranjang ini, CartCubit mengelola state yang berupa Map<ProductModel, int> (produk beserta jumlahnya). Tiga state utama yang dapat digambarkan dari life cycle keranjang adalah:

CartInitial: State awal ketika aplikasi dimuat atau setelah pengguna menyelesaikan checkout. State ini direpresentasikan oleh Map keranjang yang kosong.

CartLoaded: State aktif yang menunjukkan bahwa keranjang saat ini berisi satu atau lebih item (ProductModel). Semua pembaruan jumlah dan penambahan item akan memicu state ini.

CartLoading (Opsional): State sementara yang dapat diimplementasikan saat memproses tindakan yang membutuhkan waktu (misalnya, saat tombol Checkout ditekan dan sedang menunggu konfirmasi dari server/API sebelum keranjang dikosongkan).

Bagian B & C – Implementasi Proyek
Seluruh persyaratan implementasi (Bagian B) dan fitur bonus (Bagian C) telah diselesaikan dalam struktur file yang diminta.

Fitur Kunci yang Diimplementasikan:
ProductModel: Memiliki properti id, name, price, image dan dilengkapi metode toMap() serta fromMap().

CartCubit: Mengimplementasikan semua fungsi logika bisnis: addToCart(), removeFromCart(), updateQuantity(), getTotalItems(), getTotalPrice(), dan clearCart(). Perubahan state memicu pembaruan UI secara real-time.

Halaman Katalog (cart_grid_page.dart): Menampilkan daftar produk fashion menggunakan ProductCard dan menampilkan badge jumlah item di keranjang pada AppBar.

Halaman Keranjang (cart_summary_page.dart): Menampilkan daftar item, total item, dan total harga. Tombol Checkout memanggil clearCart() untuk mengosongkan keranjang.
