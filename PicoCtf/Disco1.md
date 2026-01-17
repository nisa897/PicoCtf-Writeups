# PicoCTF - Disco 1 Çözümü 

## Soru Özeti
Elimizde disko-1.dd.gz adında bir dosya var bu dosyadan bayrak bulmamız isteniyor.

## Çözüm Yolu

Dosyanın sonundaki .gz den bu dosyanın sıkıştırılmış olduğunu anlıyoruz.

```bash
zcat disko-1.dd.gz | strings | grep "CTF{"
```
Komutuyla bayrağı elde ederiz.

## Öğrendiklerim 
1. .gz ile biten sıkıştırılmış dosyaları çıkarmadan sadece strings komutu ile okuyamayız.
2. zcat dosyayı diskte açmadan içeriğini doğrudan okur ve bir sonraki komuta "akar" (stream) şeklinde gönderir.
   
