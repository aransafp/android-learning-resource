# Control Flow pada Kotlin
## Pengenalan
Dalam modul ini akan dibahas apa itu Control Flow dan Macam Macamnya pada Bahasa Kotlin

## Daftar Isi
- [Apa itu Control Flow?](#apa-itu-control-flow)
- [Macam - Macam Control Flow](#macam-control-flow)
    - [When Expression](#when-expression)
## Materi

### Apa Itu Control Flow?
Control Flow adalah mekanisme pengaturan proses berjalannya eksekusi kode program berdasarkan kondisi yang terjadi. Kita seringkali menemui percabangan di dalam program seperti

*Jika kondisi **ini** bernilai **true** maka jalankan kode **ini**, jika bernilai **false** maka jalankan kode **itu***

Percabangan ini lazim terjadi karena kita membuat program yang dapat berjalan di berbagai kemungkinan kondisi yang bernilai benar (true) atau salah (false) sehingga kita perlu memahami konsep control flow ini.

### Macam - Macam Control Flow<a id="macam-control-flow"></a>

#### When Expression

Seringkali jika kita menemukan permasalahan seleksi kondisi dalam program, kita akan menggunakan if else sebagai solusi. Hal itu tidak salah, namun akan menjadi merepotkan jika kondisi yang akan kita seleksi lebih dari 2. Perhatikan kasus berikut:
        
- terdapat sebuah variable "nilai"
- jika nilai diantara 0 dan 50 maka cetak "tidak lulus"
- jika nilai diantara 50 dan 60 maka cetak "baik"
- jika nilai diantara 60 dan 100 maka cetak "sangat baik"
- jika diluar nilai diatas maka cetak "error"
    
kita bisa menyelesaikan masalah tersebut dengan if else yaitu seperti berikut
```kotlin
if(nilai >=0 && nilai <= 50){
    print("tidak lulus")
}else if(nilai > 50 && nilai <= 60){
    print("baik")
}else if(nilai > 60 && nilai <=100){
    print("sangat baik")
}else{
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