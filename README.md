# Konflik pada saat pull request
Konflik terjadi bila ada dua atau lebih kontributor mengubah file yang sama, di baris yang sama, dan salah satu `Pull Request` dari kontributor tersebut belum di marge pihak upstream.
Konflik seperti ini sering terjadi bila kontributor tidak melakukan komunikasi terlebih dahulu.

### Contoh konflik yang terjadi pada pihak kontributor :
<img src=images/konflik1.png>

- Untuk mengatasi konflik tersebut pihak kontributor yang mengalami konflik harus melakukan sinkronisasi pada repository kontributor agar sama dengan repository upstream, dengan menggunakan perintah :
```
$git fetch upstream
$git checkout master
$git merge upstream/master
```

- Jika sudah melakukan perintah di atas maka brance pada repository kontributor akan `even` dengan repository upstream.
<img src=images/even.png>
- Jika sudah `even` pihak kontributor bisa melakukan `clone` dan `Pull Request` ulang.

