# PicoCTF - Binary Search Çözümü

## Soru Özeti
Meydan okumada bize şifreli bir mesaj veriyor. Ve bu mesajın bir kaç farklı yöntemle ard arda şifrelenmiş olabileceğini söylüyor.
Ard arda sırasıyla hangi şifrelenme yöntemleriyle şifrelendiğini bulup bayrağa ulaşacağız.

## Çözüm Yolu
##1.adım
Şifreli mesajı incelediğimizde '=' işaretini görüyoruz. Böylelikle base64 ile şifrelendiğini anlıyoruz.
Terminalde 
```bash
echo 'şifreli mesaj' | base64 -d
```
kodunu çalıştırıyoruz.

##2.adım
Yeni şifreli mesajımızın karakterleri 0-9,a-f arasında olduğu için her ile şifrelendiğini anlıyoruz.
terminalde 
```bash
 echo 'yeni şifreli mesaj' | xxd -r -p ; echo ""
```
kodunu çalıştırıyoruz.


##3.adım
Çıkan sonucun en başında 'cvpPGS' olduğunu görüyoruz.
Bayrak formatının PicoCTF olduğunu aklımıza getirip harflerin 13 kaydırıldığını anlıyoruz.
Yani mesajımız son olarak rot13 ile şifrelenmiş.
Terminalde 
 ```bash
 echo 'yeni şifreli mesaj' | tr 'A-Za-Z' 'N-Z'
  ```
  ```bash
echo 'şifreli mesaj' | tr 'A-Za-Z' 'N-Z'
```
  kodunu çalıştırıp bayrağı elde ediyoruz.

  **Öğrendiklerim
 
  Çoklu Kodlama (Nested Encoding): Verilerin güvenlik veya iletim amacıyla iç içe farklı algoritmalarla (Base64 -> Hex -> ROT13) kodlanabileceğini gördüm.


xxd Parametreleri: -r anahtarının tersine dönüştürme (reverse), -p anahtarının ise adres bilgisi olmadan yalın (plain) hex okuma yaptığını öğrendim. Komut sonuna eklenen ; echo "" ifadesinin ise terminal görünümünü düzenlemek için alt satıra geçtiğini kavradım.

ROT13 & URL Encoding: ROT13'ün sadece alfabe harflerini değiştirdiğini, %7B / %7D gibi URL kodlamalarının da bayrak parantezlerini ({ / }) temsil edebildiğini deneyimledim.
