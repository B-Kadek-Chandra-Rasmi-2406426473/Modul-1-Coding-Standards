Nama : Kadek Chandra Rasmi 
NPM : 2406426473


<details>
  <summary>Reflection 1</summary>
### Implementasi Clean Code Principles

- Meaningful Names: menggunakan nama variabel dan fungsi yang deskriptif sesuai tujuannya, seperti class name `ProductController`, `ProductRepository`, lalu penamaan vaiable seperti `productId`, `productName`, dan lainnya. Hal ini membuat kode mudah dibaca tanpa perlu banyak komentar tambahan.
- Single Responsibility Principle (SRP): memisahkan tanggung jawab dengan jelas, seperti `ProductController` hanya menangani request HTTP, `ProductService` menangani logika bisnis, dan `ProductRepository` menangani manipulasi data.
- Lombok: Penggunaan Lombok pada model Product membantu mengurangi boilerplate code (seperti getter/setter yang panjang), sehingga kelas model terlihat lebih bersih dan fokus pada data.
- Pada fitur Edit dan Delete, saya mengubah logika dari mengembalikan null menjadi melempar `NoSuchElementException`. Ini memastikan error terdeteksi lebih cepat dan tidak menyebabkan bug tersembunyi.

###Secure Coding
Penggunaan UUID.randomUUID() untuk menghasilkan ID produk. Ini lebih aman dibandingkan integer increment (1, 2, 3...) karena ID menjadi unik secara global dan sulit ditebak oleh pihak luar (mencegah Insecure Direct Object References / ID Enumeration)

### Improvement yang bisa dilakukan
Input Validation yang lebih ketat untuk menangani berbagai jenis kemungkinan input yang tidak valid. Error handling yang lebih menyeluruh juga diperlukan untuk program ini. 

</details>

<details>
  <summary>Reflection 2</summary>
1. Saya merasa sedikit lebih yakin dengan kode saya setelah melakukan unit test karena fungsionalitasnya berjalan lancar. Menyusun unit test menurut saya cukup menantang karena harus memikirkan segala kemungkinan kondisi (terutama edge cases) yang berpotensi memunculkan bug. 

Menurut saya tidak ada ukuran pasti berapa banyak unit test yang dibutuhkan untuk suatu class. Jumlahnya menyesuaikan dengan kebutuhan untuk memverifikasi semua kemungkinan alur logika. Unit test dapat diukur dengan tingkat coveragenya. Code coverage membantu kita melihat baris kode mana yang sudah dieksekusi oleh tes dan mana yang belum (misalnya, cabang if/else yang terlewat). Namun, 100% Code Coverage tidak menjamin kode bebas bug. Coverage hanya menghitung apakah baris kode dijalankan, bukan apakah logika baris tersebut benar.

2. Jika saya membuat functional test baru dengan menyalin prosedur setup dan variabel instance yang sama persis dari `CreateProductFunctionalTest.java`, hal itu akan menurunkan kualitas kode. Masalah utamanya adalah Code Duplication (Duplikasi Kode) yang akan menyusahkan untuk dimaintain nantinya. Untuk membuat kode lebih clean, sebaiknya membuat satu base test classyang berisi semua konfigurasi umum dan nantinya class test lain cukup mengextend class tersebut sehingga mengurangi duplikasi dan lebih mudah dimaintain jika terjadi perubahan di kemudian hari. 
</details>
