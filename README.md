# StrukturData_Q1_2501010011_IGedeArisParatamaPutra

# SOAL :
1. Karakteristik Memori dan Akses Data
Jelaskan mengapa operasi akses elemen pada Array dapat dilakukan dalam waktu konstan
O(1), sedangkan pada Singly Linked List membutuhkan waktu linear O(n). Hubungkan
jawaban Anda dengan konsep alamat memori (kontinu vs non-kontinu).
2. Analisis Efisiensi Operasi Manipulasi
Dalam kondisi apa sebuah Linked List lebih diunggulkan dibandingkan Array untuk operasi penyisipan (insertion) dan penghapusan (deletion) data? Berikan alasan teoritisnya.
3. Konsep Doubly Linked List
Jelaskan struktur anatomi dari sebuah node pada Doubly Linked List. Apa dampak keberadaan pointer tambahan tersebut terhadap penggunaan memori serta fleksibilitas penelusuran dibandingkan dengan Singly Linked List?
4. Mekanisme Circular Linked List
Apa yang membedakan Circular Linked List dari Linked List biasa secara teoritis? Sebutkan satu contoh skenario penggunaan (use case) di mana struktur melingkar ini lebih efektif digunakan.
5. Array Dinamis di Python
Python list secara internal diimplementasikan sebagai Dynamic Array. Jelaskan mekanisme yang terjadi ”di balik layar” ketika sebuah Dynamic Array kehabisan kapasitas saat melakukan operasi append.

# JAWABAN :
1.   Array memiliki karakteristik penyimpanan pada memori yang bersifat kontigu (contiguous memory allocation). Setiap elemen ditempatkan secara berurutan dalam blok memori. Kondisi ini memungkinkan akses elemen berdasarkan indeks dilakukan secara langsung melalui perhitungan alamat:
  alamat (𝑖) = base address + 𝑖 × ukuran elemen
Proses tersebut hanya melibatkan operasi aritmetika konstan, sehingga kompleksitas waktu akses elemen pada array adalah O(1).
Sebaliknya, Singly Linked List menggunakan alokasi memori non-kontigu, di mana setiap node tersebar di lokasi memori yang berbeda dan saling terhubung melalui pointer. Untuk mengakses elemen ke-i, diperlukan proses traversal mulai dari node pertama (head) hingga posisi yang dituju. Oleh karena itu, kompleksitas waktu akses elemen pada Singly Linked List adalah O(n).

2.   Linked List lebih unggul dibandingkan Array dalam operasi penyisipan (insertion) dan penghapusan (deletion) pada kondisi tertentu, yaitu ketika operasi dilakukan pada posisi yang telah diketahui atau pada bagian awal struktur data.
Secara teoritis:
  - Pada Array, operasi insertion dan deletion memerlukan pergeseran elemen (shifting) untuk menjaga sifat kontigu, sehingga kompleksitas waktunya adalah O(n).
  - Pada Linked List, operasi insertion dan deletion hanya memerlukan perubahan pointer, tanpa perlu memindahkan elemen lain, sehingga kompleksitas waktunya adalah O(1) apabila node referensi telah diketahui.

Namun demikian, apabila posisi node harus dicari terlebih dahulu, maka waktu pencarian tetap O(n), sehingga keuntungan Linked List bergantung pada konteks akses.

3. Doubly Linked List merupakan struktur data linear di mana setiap node terdiri atas tiga komponen utama:
    - Data
    - Pointer ke node berikutnya (next)
    - Pointer ke node sebelumnya (prev)

Struktur ini memungkinkan traversing dua arah, yaitu maju dan mundur.
Dampak dari keberadaan pointer tambahan adalah sebagai berikut:

Konsumsi memori lebih besar dibanding Singly Linked List, karena setiap node menyimpan satu pointer tambahan.
Fleksibilitas traversal lebih tinggi, karena memungkinkan akses dua arah tanpa perlu melacak node sebelumnya secara manual.
Mempermudah implementasi operasi tertentu seperti undo/redo, navigasi dua arah, serta penghapusan node yang lebih efisien tanpa perlu mengetahui predecessor secara eksplisit.

4. Circular Linked List merupakan variasi dari Linked List di mana node terakhir tidak menunjuk ke nilai null, melainkan kembali menunjuk ke node pertama (head), sehingga membentuk struktur melingkar. Perbedaan utama dengan Linked List biasa adalah tidak adanya terminasi eksplisit pada akhir list, sehingga traversal bersifat siklik.

Contoh penggunaan yang efektif dari struktur ini adalah Round Robin Scheduling pada sistem operasi, di mana setiap proses dieksekusi secara bergiliran dalam siklus berulang tanpa akhir. Struktur melingkar memungkinkan iterasi proses dilakukan secara kontinu tanpa perlu kembali ke awal secara manual.

5. Python list diimplementasikan menggunakan konsep dynamic array. Ketika operasi append dilakukan dan kapasitas array telah penuh, maka mekanisme berikut terjadi:
   
   => Sistem mengalokasikan blok memori baru dengan kapasitas yang lebih besar (biasanya menggunakan strategi pertumbuhan eksponensial atau amortized growth).
   
   => Seluruh elemen dari array lama disalin ke array baru.

   => Memori array lama dilepaskan dan dikelola oleh garbage collector.

   => Elemen baru kemudian ditambahkan ke struktur array yang baru.

Dari sisi kompleksitas:

    - Operasi append memiliki kompleksitas O(1) amortized.
    - Namun, pada saat resizing terjadi, kompleksitas menjadi O(n) karena proses penyalinan elemen.

Dengan demikian, dynamic array mengoptimalkan kinerja rata-rata operasi append dengan mengorbankan biaya sesekali yang lebih besar saat re-alokasi memori.


