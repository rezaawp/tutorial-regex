PEMBAHASAN BAGIAN 1

- Pemilihan dengan tanda | vertical bar yang berarti atau

- Pengelompokan dengan tanda (dan)

- Set Karakter dengan tanda bracket [ dan]

- Quantifier dengan tanda kurung kurawal { dan }

Pemilihan

Karakter meta pemilihan sering kali disebut juga dengan karakter meta alternasi. Karakter meta pemilihan diwakili oleh karakter | (garis lurus vertikal) dan dibaca sebagai "atau".

Gunanya untuk memilih satu dari dua atau lebih alternatif yang disediakan.

Pengelompokan

Pengelompokan diwakili oleh karakter (dan), yang digunakan untuk mengelompokkan set aturan. Pada umumnya karakter meta pengelompokan digunakan bersamaan dengan karakter meta lain.

Set Karakter

Set karakter diwakili oleh karakter [ dan 1. pada dasarnya juga digunakan untuk pemilihan layaknya karakter metal. Namun, set karakter ini mempunyai fasilitas syntax rentang dan negasi. Contoh dari syntax rentang adalah [m-n], yang akan cocok dengan karakter mulai dari m hingga n. Contoh dari syntax negasi adalah [m], yang akan cocok dengan semua karakter kecuali karakter huruf m. Perhatikan contoh dari aturan set karakter berikut ini:

迴

[0-9] akan cocok dengan angka 0 sampai 9.

[A-EG-Z] akan cocok dengan semua huruf besar kecuali F.

[0-9][0-9] akan cocok dengan 00 sampai 99 (100 kombinasi).

[012][0-9] akan cocok dengan 00 sampai 29 (30 kombinasi).

[012][0-9]130 akan cocok dengan '00 sampai 29' atau 'angka 30′ (31 kombinasi).

Quantifier

Karakter meta quantifier menyatakan berapa rentang atau jumlah karakter yang diperbolehkan dari sebuah pola (satu atau kelompok karakter yang berada di sebelah kiri quantifier). Berikut ini adalah beberapa format dari quantifier.

X(m) artinya set aturan X harus ada sebanyak m kali.

X(m.) artinya set aturan X harus ada minimal sebanyak m kali.

X(n) artinya set aturan X boleh ada hingga terulang maksimal n buah.

⚫X[m.n] artinya set aturan X boleh ada dari minimal m buah hingga terulang sebanyak maksimal n buah.

PEMBAHASAN BAGIAN 2

- Optional dengan tanda ? "boleh ada / boleh juga tidak",

- Tanda. ( titik / dot) mewakili semua karakter kecuali new line

- Pengulangan dengan tanda + dan *

- Jangkar dengan caret ^ ( diawali ) dan dolar $ (diakhiri)

Optional

Karakter meta optional diwakili oleh simbol ? (tanda tanya). Karakter meta optional dalam regex artinya huruf atau kelompok aturan yang berada pada sebelah kiri tanda tanya (?) bersifat optional. Dapat juga dibaca "boleh ada atau boleh juga tidak".

Titik

Titik atau dot adalah simbol dallas repes yang cocok dengan semata karakterjangga

Pengulangan

Karakter meta perulangan diwakili oleh simbol atau +. Jika pada karakter meta pemilihan (?) dapat diartikan "boleh ada boleh tidak" atau "nol atau satu", maka karakter meta * dapat diartikan "nol atau lebih" dan karakter meta + dapat diartikan "satu atau lebih" dari karakter atau set aturan yang tepat berada pada sebelah kiri karakter meta pengulangan tersebut.

Jangkar

Karakter meta jangkar diwakili oleh simbol dan S. Masing-masing simbol tersebut dapat diartikan "harus diawal" dan "harus diakhir". Karakter meta ini tidak melambangkan arti apapun, melainkan mensyaratkan posisi atau penambatan pola ke string yang ingin dicocokkan. Itulah sebabnya pasangan karakter meta ini disebut anchor atau jangkar.

PEMBAHASAN BAGIAN 3 (MODIFIER)

a. Modifier i (IGNORE_CASE)

b. Modifiers (SINGLE_LINE)

c. Modifier m (MULTIPLE_LINE)

d. Modifier g (GLOBAL_MATCH)


a. Modifier i (IGNORE_CASE)

Jika kita menggunakan modifier ini, maka mesin regex tidak akan membedakan antara huruf besar dan kecil. Artinya pola [a-z] dengan modifier i akan dianggap sama dengan pola [a-zA-Z]. Modifier ini bermanfaat untuk mempersingkat pola, jika kita menginginkan pencocokan yang tidak membedakan huruf besar dan kecil.

b. Modifiers (SINGLE_LINE)

Masih ingat dengan karakter meta. (titik)? Pada dasarnya, karakter meta titik akan cocok dengan string atau karakter apapun. Kecuali karakter new line (n) atau enter. Contoh:

Selamat.+ akan cocok dengan Selamat Datang namun tidak dengan Selamat Datang (deretan karakter Selamat diikuti deretan karakter Datang pada baris selanjutnya). Ini dikarenakan mesin regex menganggap akhir baris sebagai akhir dari sebuah string yang hendak dicocokkan. Sehingga sub pola + tidak akan cocok dengan string Selamat Datang dimana setelah string Selamat tidak ada lagi karakter pada baris pertama string

Dengan menggunakan modifiers, karakter meta. (titik) akan cocok dengan new line, sehingga mesin regex akan menelan semua sisa string hingga Andatang. Dengan kata lain, dengan modifiers, setiap string akan dianggap terdiri dari satu baris saja.

c. Modifier m (MULTIPLE_LINE)

Meskipun dinamakan multiple line, modifier ini bukanlah kebalikan dari modifiers. Bahkan kedua modifier ini dapat dipakai secara bersamaan tanpa saling bentrok satu sama lain. Contoh:

Tanpa ada modifier m. "Ditang tidak akan cocok dengan string Selamat Datang Karena karakter meta jangkar mensyaratkan deretan karakter Datang ada pada awal string, dalam hal ini awal dari string adalah Selamat

Dengan modifier m, pola tersebut akan cocok karena tiap awal dan akhir haris dianggap sebagai ujung yang bisa cocok dengan karakter meta jangkar. Contoh Jain, Selamat's akan cocok di mode m tapi tidak tanpa m. Dengan kata lain, dalam mode m setiap baris dalam string akan dianggap memiliki awal dan ujung string masing-masing.

d. Modifier g (GLOBAL_MATCH)

Dengan modifier ini, pencocokan berikutnya akan dilanjutkan dari posisi terakhir yang ditemukan, tidak diulang dari posisi awal string. Terutama berguna jika ingin melakukan iterasi /perulangan string dari awal hingga akhir.
