# Control Flow pada Kotlin
## Pengenalan
Dalam modul ini akan dibahas apa itu Control Flow dan Macam Macamnya pada Bahasa Kotlin

## Daftar Isi
- [Apa itu Control Flow?](#apa-itu-control-flow)
- [Macam - Macam Control Flow](#macam-control-flow)
    - [When Expression](#when-expression)
    - [For Loop](#for-loop)
    - [While Loop](#while-loop)
## Materi

### Apa Itu Control Flow?
Control Flow adalah mekanisme pengaturan proses berjalannya eksekusi kode program berdasarkan kondisi yang terjadi. Kita seringkali menemui percabangan di dalam program seperti

> *Jika kondisi **ini** bernilai **true** maka jalankan kode **ini**, jika bernilai **false** maka jalankan kode **itu***

Percabangan ini lazim terjadi karena kita membuat program yang dapat berjalan di berbagai kemungkinan kondisi yang bernilai benar (true) atau salah (false) sehingga kita perlu memahami konsep control flow ini.

### Macam - Macam Control Flow<a id="macam-control-flow"></a>

#### When Expression

Seringkali jika kita menemukan permasalahan seleksi kondisi dalam program, kita akan menggunakan if else sebagai solusi. Hal itu tidak salah, namun akan menjadi merepotkan jika kondisi yang akan kita seleksi lebih dari 2. Perhatikan kasus berikut:
        
>    - terdapat sebuah variable "nilai"
>    - jika nilai diantara 0 dan 50 maka cetak "tidak lulus"
>    - jika nilai diantara 50 dan 60 maka cetak "baik"
>    - jika nilai diantara 60 dan 100 maka cetak "sangat baik"
>    - jika diluar nilai diatas maka cetak "error"
    
kita bisa menyelesaikan masalah tersebut dengan if else yaitu seperti berikut
```kotlin
if ( nilai >=0 && nilai <= 50){
    print("tidak lulus")
} else if(nilai > 50 && nilai <= 60){
    print("baik")
} else if(nilai > 60 && nilai <=100){
    print("sangat baik")
} else{
    print("error")
}
```

Cukup panjang bukan? namun jika kita menggunakan when expression maka akan menjadi
```kotlin
when(nilai) {
    0..50 -> print("tidak lulus")
    51..60 -> print("baik")
    61..100 -> print("sangat baik")
    else -> print("error")
}
```
>Sumber: https://kotlinlang.org/docs/control-flow.html#when-expression


#### For Loops<a id="for-loop"></a>

Perulangan for adalah suatu konsep untuk melakukan perulangan eksekusi kode program sehingga kita tidak perlu menulis program berulang kali
```kotlin
for(i in 1..10){
    println(i)
}

//output
1
2
3
4
5
6
7
8
9
10
```
Kode diatas akan menjalankan semua yang ada di dalam *curly braces* sebanyak 10 kali. Angka 10 kali di dapat dari kode ```i in 1..10``` yang berarti *i dalam rentang 1 hingga 10*. Awalnya program akan membuat variable ```i``` dengan nilai awal 1. Pada setiap iterasi terjadi, nilai variable i akan bertambah 1 hingga 10. Ketika ```i``` sudah mencapai nilai 10, maka perulangan selesai

> Sumber: https://kotlinlang.org/docs/control-flow.html#for-loops


### While Loop
Jika kita melihat pada [For Loop](#for-loop), kita akan mengetahui bahwa perulangan tersebut sudah kita tentukan seberapa banyak perulangan akan dilakukan. Lalu bagaimana jika ingin membuat perulangan namun kita tidak tahu berapa banyak perulangan tersebut akan dilakukan? Kita dapat menggunakan while loop untuk mengatasi hal itu. Mari kita lihat kode dibawah
```kotlin
val angka = 1
while(angka < 1000){
    if(angka % 2 == 0){
        println(angka)
    }
    angka++
}

//output
2
4
6
..
..
..
998
````
Kode diatas adalah kode untuk mencetak seluruh angka genap dari 1 hingga 1000. Anggap saja kita tidak tahu berapa banyak angka genap diantara 1 dan 1000, sehingga kita butuh while loop untuk melakukannya. Kode didalam **Curly Braces** akan berjalan selama kondisi ```angka < 1000``` terpenuhi.

Terdapat 1 varian dari while yaitu ```do...while...``` yang artinya *Lakukan ... selama ...*. Hampir serupa dengan ```while```. ```do ... while ...``` akan menjalankan kode di dalam *curly braces* minimal sekali, lalu memeriksa kondisi. Mari kita lihat kode dibawah:
```kotlin
val x = 11

do {
    println("x dicetak")
} while(x <= 10)

//Output
x dicetak
```
pada kode diatas, meskipun kondisi ``` x <= 10``` bernilai false namun kode di dalam *curly braces* tetap tetap di eksekusi karena program berjalan dari atas ke bawah sehingga perintah di dalam ```do{}``` di jalankan
> Sumber: https://kotlinlang.org/docs/control-flow.html#while-loops