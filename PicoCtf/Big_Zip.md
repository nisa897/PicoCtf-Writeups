# PicoCTF - Big Zip Çözümü

## Soru Özeti
Bu soruda bize verilen big-zip-files.zip dosyasından gizli bayrağı bulmamız isteniyor.

## Çözüm Yolu
Terminalde şu komutu kullanarak veya online bir araçla şifreyi çözdüm:
```bash
unzip -p big-zip-files.zip | grep "pico"
```
<img width="985" height="179" alt="image" src="https://github.com/user-attachments/assets/c36c5329-914c-416e-a741-e1890d7506a6" />

## Sonuç 
Aldığımız çıktıda bayrağı bulduk.

**Öğrendiklerim**
1. unzip
ZIP dosyalarını açmak için kullanılan temel araçtır.
2. -p
Normalde unzip komutu dosyaları klasöre çıkartır. Ancak -p parametresi, dosya içeriğini diske yazmak yerine standart çıktıya (terminal ekranına) gönderir.
Bu alandan tasarruf etmemizi sağlar.
3. grep 
Filtreleme aracıdır. Kendisine gelen devasa veri yığını içinde sadece istediğimiz kelimelerin geçtiği satırları bulur ve ekrana basar.


