# SQL-PatikaDev
[Patika.dev](https://app.patika.dev/egitimler) adresindeki "SQL" eğitiminde kullandığım kaynak kodları içeren bir repo.

Bu README dosyasında bu eğitimdeki ödevlerin cevaplarını bulacaksınız.
## :brain: Ödev 1 

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
2-film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
3-film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
4-customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
5-film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>

SELECT title , description FROM film ;

SELECT * FROM film 
WHERE  length > 60 AND length < 75 ;

SELECT * FROM film 
WHERE  rental_rate = 0.99 AND (replacement_cost = 12.99 OR replacement_cost = 28.99) ;

SELECT last_name FROM customer 
WHERE  first_name = 'Mary' ;

SELECT * FROM film 
WHERE  length <= 50 AND NOT(rental_rate = 2.99 OR rental_rate = 4.99) ;
</details>

## :brain: Ödev 2

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
2-.actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)
3-film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT  * FROM film
WHERE replacement_cost BETWEEN  12.99 AND  16.99 ;

SELECT first_name , last_name FROM actor
WHERE first_name IN('Penelope' , 'Nick' , 'Ed') ;

SELECT * FROM film 
WHERE rental_rate IN(0.99 , 2.99 , 4.99) AND  replacement_cost IN(12.99 , 15.99 , 28.99) ;
</details>
