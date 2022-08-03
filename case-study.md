# Case study: Basic use of Git and Github

## Scenario 1

Kita adalah seorang programmer yang akan membuat aplikasi untuk pembelajaran online bernama **ruang-belajar**. Ini adalah aplikasi yang cukup kompleks sehingga setiap perubahan harus:

- Tercatat dengan baik
- Memiliki backup
- Dan diharapkan bisa rollback ke versi-versi yang lama

Oleh karena itu kita telah memutuskan untuk menggunakan Git untuk mengelola dan mengontrol versi code dari aplikasi tersebut.

---

Kita memulai dengan membuat Git repository di komputer lokal, kemudian kita membuat struktur foldernya sebagai berikut:

```path
📁ruang-belajar
   📁.git
   📄index.html
```

Lalu kita mengisi file `index.html` dengan code:

```html
<html>
<head>
    <title>Ruang Belajar</title>
</head>
<body>
    
</body>
</html>
```

Agar isi dari file `index.html` tidak hilang, maka kita melakukan commit dengan pesan "inisialisasi file index.html"

Kemudian kita membuat file berikutnya yaitu `test.hmtl` dengan isi:

```html
<html>
<head>
    <title>Test Page</title>
</head>
<body>
    
</body>
</html>
```

Namun kita tidak ingin file `test.hmtl` di-commit di Git, karena file itu hanya sample page percobaan pribadi. Akhirnya kita harus mendaftarkannya ke file `.gitignore`.

Lalu kita membuat folder di repository kita untuk menampung semua halaman dari aplikasi **ruang-belajar** bernama `pages`.

Lalu kita tambahkan beberapa file disana yaitu `meterial.html`, `question.html` dan kita melakukan commit berikutnya dengan pesan "add pages ruang-belajar"

Akhirnya strukture file dari aplikasi yang kita buat akan menjadi seperti ini:

```path
📁ruang-belajar
   📁.git
   📁pages
      📄meterial.html
      📄question.html
   📄index.html
   📄test.hmtl
   📄.gitignore
```

Kemudian kita mulai bekerja pada file `material.html` dengan menambahkan beberapa list judul materi pada file tersebut, yaitu:

```html
<html>
<head>
    <title>Material Page</title>
</head>
<body>
    <ul>
        <li>Git basic</li>
        <li>Github basic</li>
    <ul>
</body>
</html>
```

Dan beberapa list pertanyaan pada file `question.html` yaitu:

```html
<html>
<head>
    <title>Question Page</title>
</head>
<body>
    <ul>
        <li>What is Git?</li>
        <li>Why use Git?</li>
    <ul>
</body>
</html>
```

Selanjutnya, kita membuat commit untuk file `material.html` saja dengan pesan "add list material". Dan di commit berikutnya untuk file `question.html` dengan pesan "add list question".

Selanjutnya kita akan mengerjakan ke-2 halaman tersebut dengan target yang sudah ditentukan, dan dirasa itu akan cukup.

Namun, tiba-tiba atasan kita meminta untuk menambahkan halaman dashboard untuk menganalisa jawaban dan nilai dari pengguna aplikasi yang kita buat namun dengan tidak menambah batas waktu pengerjaan.

Sepertinya, hal tersebut tidak akan cukup waktunya jika dikerjakan sendirian. Akhirnya, kita meminta bantuan **Bob** salah satu programmer untuk membantu mengerjakan feature dashboard yang diminta secara paralel.

Oleh karena itu kita harus membuat branch, agar **Bob** bisa bekerja dengan branch tersebut tanpa mengganggu branch utama.

Jadi kita membuat branch bernama `dashboard-feature`.

## Scenario 2

Sekarang kita bayangkan menjadi **Bob** yang diminta untuk membuat feature dashboard tersebut, jadi dari branch utama, kita harus beralih ke branch `dashboard-feature` dan menambahkan file `dashboard.html` di folder pages.

Segingga strukture folder di branch `dashboard-feature` akan terlihat seperti ini:

```path
📁ruang-belajar
   📁.git
   📁pages
      📄meterial.html
      📄question.html
      📄dashboard.html
   📄index.html
   📄test.hmtl
   📄.gitignore
```

Lalu bob menambahkan commit penambahan file tersebut dengan pesan "init dashboard.html". Kemudian, Bob menambahkan file tersebut dengan code:

```html
<html>
<head>
    <title>Dashboard Page</title>
</head>
<body>
    <div>Chart1<div>
    <div>Chart2<div>
</body>
</html>
```

Lalu, melakukan commit kembali dengan pesan "add initial chart 1 and chart 2"

## Back to Scenario 1

Sekarang kita kembali ke sudut pandang kita yang sedang mengerjakan feature utama. Jadi kita harus kembali ke branch utama kita yaitu `master`.

Lalu kita lanjutkan untuk mengerjakan file `meterial.html` dan menambahkan beberapa paraghraph dari file tersebut:

```html
<html>
<head>
    <title>Material Page</title>
</head>
<body>
    <ul>
        <li>Git basic</li>
        <li>Github basic</li>
    <ul>
    <h1>Git basic</h1>
    <p>Git adalah centralize version control system yang sering digunakan oleh programmer profesional saat ini</p>
</body>
</html>
```

Lalu kita lakukan commit kembali denga pesan "add some paraghraph git basic material"

lalu kita menambahkan paragraph untuk materi di list selanjutnya pada file yang sama:

```html
<html>
<head>
    <title>Material Page</title>
</head>
<body>
    <ul>
        <li>Git basic</li>
        <li>Github basic</li>
    <ul>
    <h1>Git basic</h1>
    <p>Git adalah centralize version control system yang sering digunakan oleh programmer profesional saat ini</p>
    <h1>Github basic</h1>
    <p>Github adalah platform untuk menyimpan repo secara online</p>
</body>
</html>
```

## Scenario 3

Setelah bekerja di Branch yang berbeda, ternyata **Bob** telah selesai mengerjakan feature dashboard di branch `dashboard-feature` lebih awal dari perkiraan. Berarti sekarang, saatnya melakukan penggabungan antara perubahan branch `master` dengan branch `dashboard-feature`.

Setelah branch digabungkan, kita siap untuk mengerjakan file selanjutnya yaitu file `question.html`. di sini kita tambahkan pertanyaannya:

```html
<html>
<head>
    <title>Question Page</title>
</head>
<body>
    <ul>
        <li>What is Git?</li>
        <li>Why use Git?</li>
    <ul>
    <h1>What is Git</h1>
    <p>Apa itu git ini?</p>
    <p>Kapan kita mengguanakn git ini?</p>
</body>
</html>
```

Setelah menambahkan pertanyaan tersebut, kita lakukan commit dengan pesan "add two question git init"

Setelah beberapa aktivitas commit berlalu, ternyata kita sadar bahwa ada kesalahan penulisan pada materi git basic. Untungnya kita menggunakan git untuk setiap perubahan. Jadi kita bisa mengembalikan perubahan dari commit yang mengubah materi tersebut dan membetulkan kesalahan yang terjadi ke commit selanjutnya denga lakukan **revert commit**.

Karena ragu, jika terjadi kesalahan dikemudian. Akhirnya kita membuat branch untuk mengerjakan materi yang berbeda yaitu: branch `git-material` dan branch `github-material`.

Oke kita sudah membuat branch untuk memisahkan pekerjaan. dan kita masuk ke branch `git-material` untuk mengerjakan materi git.

Petama kita.

<!-- To Be Continued -->
  
## Submission

- Kamu harus membagikan Github repository yang berisi commit history sesuai skenario di atas.

<!-- 
## Sistem Penilaian (untuk mentor):
- Apakah Github history dan branchingnya sesuai dengan jawaban
- Memiliki todo.txt di .gitignore
- Tidak ada Git commit yang tidak sesuai text
 -->
