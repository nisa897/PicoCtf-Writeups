# PicoCTF - Endianness Çözümü

## Soru Özeti
Soruda büyük ve küçük endian'ı öğrenmemiz isteniyor.
Ve nc komutuyla istenilen web sitesine bağlanarak bayrağı bulmamız isteniyor.

## Çözüm Yolu

## 1.adım 
nc komutuylaistenilen web sitesine terminalden bağlanıyoruz.

## 2.adım
Bize bir kelime verilmiş bu kelimeyi küçük endian a çevirmemiz isteniyor.
Kelimemiz ise mwrqr.
Büyük endian da mwrqr bu şekilde çevirecekken, küçük endianda rqrwm yani bunun ters çevrilmiş halinin sırasına göre endian a çevireceğiz.

## 3.adım
Bunun için cybershep.com sitesini kullanacağız.
Hex to yu seçip kelimenin tersini yazdım.

<img width="611" height="468" alt="image" src="https://github.com/user-attachments/assets/99465a3b-445b-49d9-a133-3ee20e70f0bb" />

Aldığımız çıktıda mwrqr kelimesinin küçük endian değerinin "72 71 72 77 6d" olduğunu görüyoruz.

<img width="533" height="122" alt="image" src="https://github.com/user-attachments/assets/575cba99-ab3d-4f94-b670-66bb352e51a4" />

## 4.adım
Devamında bizden büyük endian değerini istiyor.
Bunun için cybershef sitesinde yine hex to yu kullanarak kelimenin dü< kalini giriyoruz.
Büyük endian değerimizi " 6d 77 72 71 72 " olarak buluyoruz.
Bayrağı bulduk!!


**Öğrendiklerim**

Bilgisayarlar sayılar ve karakterleri hafızada saklarken baytlar halinde saklar.
Eğer bir veri birden fazla bayttan oluşuyorsa bu baytların hangi sırayla dizileceği Endianness kuralına bağlıdır.
Büyük endian kelimenin ya da karakterin yazıldığı sırayla yani soldan sağa doğru baytlarının sıralanmasıdır.
Küçük endian kelimenin ya da karakterin yazıldığı sıranın tersine göre yani sağdan sola doğru baytlarının sıralanmasıdır.
