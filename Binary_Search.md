# PicoCTF - Binary Search Çözümü

## Soru Özeti
Meydan okumanın başında nc komutuyla terminalden web sitesine bağlanmamız isteniyor.
guessing_game.sh adında bir dosya verilmiş bayrağı bulmamız isteniyor.

## Çözüm Yolu

##1.adım
soruda bize verilen kod ile istenilen qeb sitesine istenilen portla bağlanıyoruz.
<img width="521" height="53" alt="image" src="https://github.com/user-attachments/assets/4ba456f9-90db-4740-b80f-2ed71dc4f224" />

Sayı tahmin oyunu başlıyor!!

##2.adım
  guessing_game.sh dosyasında ise sayı tahmin oyunun kaynak koduna erişiyoruz.
  0-1000 random bir sayı tutuluyor her seferinde.
  10 deneme hakkımız var.
  Her seferinde sayıyı arttırmamız ya da azaltmamız için bize bilgi veriyor.
  Bundan faydalanarak soruda da bizden istediği gibi sıcak soğuk oyunu oynayacağız.

##3.adım
Her seferinde ikili arama yaparak arama alanını iki eşit parçaya bölüyorum.
Çıkan higher veya lower komutuna göre üstte kalan yarıyı ya da altta kalan yarıyı seçip tekrar arama alanını ikiye ayırıp devam ediyorum.

<img width="338" height="286" alt="image" src="https://github.com/user-attachments/assets/055efd8d-c060-4d88-8d75-132483fc1628" />

Önce 500 ü denedim lower çıktısı aldığım için sayının 0-499 aralığında olduğunu anladım.

Sonra 250 yi denedim lower çıktısı aldığım için sayının 0-249 aralığında olduğunu anladım.

125 i deneyince higher çıktısı aldığım için sayının 126-249 aralığında olduğunu anladım.

187 yi deneyince higher çıktısı aldığım için sayının 187-249 aralığında olduğunu anladım.

219 u deneyince higher çıktısı aldığım için sayının 219-249 aralığında olduğunu anladım.

235 i deneyince higher çıktısı aldığım için sayının 235-249 aralığında olduğunu anladım.

242 i deneyince lower çıktısı aldığım için sayının 235-242 aralığında olduğunu anladım.

238 i deneyince deneyince higher çıktısı aldım.

239 u deneyince bayrağı buldum!!

**Öğrendiklerim**
Arama alanını ikiye bölerek basit bir şekilde sayı tahmin oyununda sayıyı tahmin edebiliriz.
