# Pico CTF - Respetitions CTF Çözümü

## Soru Özeti
Soruda enc_flag adında bir dosya var. Bu dosyadan bayrağı bulmamızı istiyor.

## Çözüm Yolu

## 1.adım
```bash
cat enc_flag
```
komutu ile bayrağı okuduğumuzda elimizde base64 le şifrelenmiş bir mesaj görüyoruz.

## 2.adım
```bash
echo 'base64 lü metin' | base64 -d
```
komutu ile base64 ten çeviriyoruz. Sonuç olarak yine base64 le şifreli mesaj görüyoruz.
Sorunun adından da anlaşıldığı gibi bayrağımız base64 le birden fazla kere şifrelenmiş .
```bash
echo 'base64 lü metin' | base64 -d
```
bu kod mantığı ile giderek ya da cyberchef sitesinden from base64 ü seçip tekrar tekrar decode ediyoruz.
Bayrağa ulaştık!!

**Öğrendiklerim**
Base64 algoritması verileri 3 baytlık (24 bit) bloklar halinde işler ve bunları 4 karakterlik gruplara dönüştürür. Kodlanacak verinin boyutu 3'ün katı değilse, eksik kalan kısmı tamamlamak için sonuna dolgu karakteri (padding) olarak = eklenir:
1 bayt eksikse: Sona = eklenir.
2 bayt eksikse: Sona == eklenir.
Tam 3'ün katıysa: Dolgu gerekmez, sonda = olmaz.
Karakter kümesi: Yalnızca büyük/küçük İngilizce harfler (A-Z, a-z), rakamlar (0-9), + ve / içerir (URL uyumlu versiyonunda + yerine -, / yerine _ kullanılır).
Uzunluk: Toplam karakter sayısı her zaman 4'ün katıdır.
