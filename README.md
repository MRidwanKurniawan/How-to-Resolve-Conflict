# Berkontribusi

Asumsi untuk pembahasan ini, account yang akan berkontribusi adalah `MRidwanKurniawan`, silahkan ganti sesuai dengan nama account anda.

# Setting awal

Bagian ini harus anda kerjakan sebelum mengirimkan kontribusi. Setting awal ini hanya dilakukan sekali saja.

* Install Git
* Buat account di Github
* Fork repo ini ke repo pada account anda, caranya: login kemudian `fork`.

* Pada komputer lokal anda, kerjakan langkah berikut:

```
$ git clone https://github.com/MRidwanKurniawan/How-to-Resolve-Conflict
Cloning into 'How-to-Resolve-Conflict'...
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Checking connectivity... done.
$
```
Pada kondisi saat ini, di komputer lokal anda sudah terdapat repo `How-to-Resolve-Conflict` yang berada pada direktori dengan nama yang sama. Untuk keperluan berkontribusi, ada 2 nama repo yang harus anda setting:
  1. origin => menunjuk ke repo milik anda di github, hasil dari fork.
  2. upstream => menunjuk ke repo milik upstream (repo asli) 
Repo `origin` sudah dituliskan konfigurasinya pada saat anda melakukan proses clone dari repo anda. Konfigurasi repo upstream harus dibuat.

```
$ git remote -v
$
```
Tambahkan remote upstream:

```
$ git remote add upstream https://github.com/MRidwanKurniawan/How-to-Resolve-Conflict
```
* Selesai setting awal.

# Sync Repo Sebelum Pull Request (PR)

Bagian ini dikerjakan sebelum mengirimkan PR. Tujuannya untuk memastikan bahwa yang kita buat belum dibuat oleh orang lain.

```
$ git fetch upstream
$ git checkout master
$ git merge upstream/master
$ git status
$ git push origin master
```

Hasil dari sync tersebut adalah kondisi yang sudah _synchronized_ dengan upstream (disebut dengan _even_).

Sebelum mengirim PR, disarankan untuk melihat log terlebih dahulu untuk memeriksa apakah sudah ada yang melakukan commit terhadap perubahan yang akan anda lakukan.


```
$ git log
```

Jika belum ada, maka anda bisa mulai menyiapkan dan mengirimkan perubahan.

# Membuat Perubahan dan Mengirim PR

## Membuat Perubahan

Untuk setiap perubahan, buat dalam branch, jangan buat dalam master karena akan mencampur adukkan dan membuat susah dilacak.

```
$ git checkout -b berkontribusi
$ git branch
```

Setelah itu editlah seperlunya (bisa meliputi hanya satu file atau lebih banyak lagi), setelah selesai, kirim perubahan tersebut ke repo milik anda (bukan upstream tetapi origin).


```
$ git status
$ git add -A
$ git commit -m "Menambahkan petunjuk berkontribusi"
$ git push origin berkontribusi
```
Pada posisi ini, kontributor siap untuk mengirimkan PR.

## Mengirim PR

* Pada halaman web di repo account Github anda, pilih branch `berkontribusi` kemudian klik pada **New Pull Request**.
* Setelah muncul halaman **Open a pull request**, isikan catatan untuk PR anda tersebut, setelah itu klik pada tombol **Submit pull request**.

* Setelah itu, pada repo MRidwanKurniawan akan muncul **1 Pull request** sesuai isian anda.
* Pada posisi ini anda tinggal menunggu apakah akan langsung di-merge ataukan ada diskusi lebih dulu.

# Menanti Hasil Merge

Setelah selesai mengirimkan PR, kontributor menunggu proses penggabungan (merge). Jika disetujui, maka pada saat login, akan muncul notifikasi:

Setelah membaca notifikasi itu (jika perlu), kontributor akan tahu bahwa PR yang dia usulkan sudah di-merge. Setelah itu, pada repo lokal kotributor, sync dengan upstream:

```
$ git checkout master
$ git fetch upstream
$ git merge upstream/master
$ git status
$ git push origin master
```
Setelah itu, repo kontributor berada dalam kondisi sync. 

