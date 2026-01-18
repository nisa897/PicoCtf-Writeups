## PicoCTF - Flag in Flame

## Soru Özeti
Elimizde logs.txt adında şifrelenmiş büyük bir dosya var. Bu dosyadan bayrağı bulmamız isteniyor.

## Çözüm Yolu
Önce hangi şifreleme kullanıldığını bulmamız gerek.

## 1.adım
```bash
head -c 32 logs.txt | xxd
```
Komutuyla hangi yöntemle şifrelendiğine bakalım.
<img width="467" height="37" alt="image" src="https://github.com/user-attachments/assets/62cf268f-1b33-4c71-8bb8-8b0ac66f9002" />

## 2.adım 
Aldığımız çıktıda büyük harfler, küçük harfler ve rakamlar olduğu için base64 le şifrelendiğini anlarız.

base64 -d logs.txt > sonuc.png
