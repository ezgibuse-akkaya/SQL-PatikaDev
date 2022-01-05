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

## :brain: Ödev 3

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.
2-country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.
3-film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.
4-film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT country FROM country
WHERE country LIKE 'A%a' ;

SELECT country FROM country
WHERE country LIKE '_____%n' ;

SELECT title FROM film
WHERE title ILIKE '%T%T%T%T%' ;

SELECT * FROM film
WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99 ;
</details>

## :brain: Ödev 4

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.
2-film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?
3-film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
4-country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
5-city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?
### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT DISTINCT replacement_cost FROM film ;

SELECT COUNT(DISTINCT replacement_cost) FROM film ;

SELECT COUNT(*) FROM film
WHERE title LIKE 'T%' AND rating = 'G' ;

SELECT COUNT(*) FROM country
WHERE country LIKE '_____' ;

SELECT COUNT(*) FROM city
WHERE city ILIKE '%R' ;
</details>

## :brain: Ödev 5

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
2-film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.
3-customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT title , length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5 ;


SELECT title , length FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5 ;


SELECT * FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4 ;
</details>

## :brain: Ödev 6

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?
2-film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?
3-film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?
4-film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?
### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT ROUND(AVG(rental_rate),3) AS Avg_rental_rate FROM film ;


SELECT COUNT(title) FROM film
WHERE title LIKE 'C%' ;


SELECT  MAX(length) FROM film
WHERE rental_rate = 0.99 ;


SELECT COUNT(DISTINCT replacement_cost) FROM film
WHERE length > 150 ;
</details>
## :brain: Ödev 7

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
2-film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.
3-customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.
### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT rating , COUNT(title) AS Film_number FROM film
GROUP BY rating ;


SELECT replacement_cost , COUNT(title) AS Film_number FROM film
GROUP BY replacement_cost
HAVING COUNT(title) > 50 ;


SELECT store_id , COUNT(*) AS Customer_Number FROM customer
GROUP BY store_id ;


SELECT country_id , COUNT(city)  FROM city
GROUP BY country_id 
ORDER BY COUNT(city) DESC 
LIMIT 1 ;
</details>
## :brain: Ödev 8

### :question: SORU 
1-test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
2-Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
3-Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
4-Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
CREATE TABLE employee(
	id INTEGER ,
	name VARCHAR(50),
	birthday DATE ,
	email VARCHAR(100)
); 

SELECT * FROM employee ;

---------
insert into employee (id, name, birthday, email) values (1, 'Brena', '1929/07/09', 'bcrat0@deviantart.com');
insert into employee (id, name, birthday, email) values (2, 'Madelon', '1941/03/19', 'mknowler1@stanford.edu');
insert into employee (id, name, birthday, email) values (3, 'Dari', '2005/08/22', 'dfraniak2@cargocollective.com');
insert into employee (id, name, birthday, email) values (4, 'Kerrie', '1916/09/06', 'kminet3@google.com.au');
insert into employee (id, name, birthday, email) values (5, 'Blaine', null, 'bsarsons4@acquirethisname.com');
insert into employee (id, name, birthday, email) values (6, 'Liz', '1908/05/06', 'lklisch5@deviantart.com');
insert into employee (id, name, birthday, email) values (7, 'Kirstyn', '1974/11/28', 'kwandrach6@jimdo.com');
insert into employee (id, name, birthday, email) values (8, 'Aron', '1994/03/15', 'alukesch7@ebay.co.uk');
insert into employee (id, name, birthday, email) values (9, 'Manfred', '1933/06/09', 'mduncan8@nhs.uk');
insert into employee (id, name, birthday, email) values (10, 'Shellysheldon', '1901/04/23', 'ssharples9@blogger.com');
insert into employee (id, name, birthday, email) values (11, 'Mikael', null, 'mrydinga@vinaora.com');
insert into employee (id, name, birthday, email) values (12, 'Arlina', '1937/11/07', 'aspelsburyb@smugmug.com');
insert into employee (id, name, birthday, email) values (13, 'Godwin', '1935/03/26', 'glennoxc@google.nl');
insert into employee (id, name, birthday, email) values (14, 'Rafaello', '2006/02/25', 'rmcgeownd@bbc.co.uk');
insert into employee (id, name, birthday, email) values (15, 'Tremayne', null, 'tcuste@state.gov');
insert into employee (id, name, birthday, email) values (16, 'Cherish', '2001/09/18', 'cwressellf@de.vu');
insert into employee (id, name, birthday, email) values (17, 'Kaye', '1918/07/05', 'kaudissg@accuweather.com');
insert into employee (id, name, birthday, email) values (18, 'Serene', '1970/01/20', null);
insert into employee (id, name, birthday, email) values (19, 'Abrahan', null, 'ahuoti@vinaora.com');
insert into employee (id, name, birthday, email) values (20, 'Ibrahim', null, 'ihachardj@telegraph.co.uk');
insert into employee (id, name, birthday, email) values (21, 'Mandel', null, 'mclarsonk@myspace.com');
insert into employee (id, name, birthday, email) values (22, 'Jessamine', '1960/10/08', 'jpatridgel@imageshack.us');
insert into employee (id, name, birthday, email) values (23, 'Wayne', '1905/05/24', null);
insert into employee (id, name, birthday, email) values (24, 'Cesare', null, 'ctwigginsn@bizjournals.com');
insert into employee (id, name, birthday, email) values (25, 'Callie', '1914/02/03', 'ccolleero@about.com');
insert into employee (id, name, birthday, email) values (26, 'Elyssa', '1990/05/20', 'ecossorp@census.gov');
insert into employee (id, name, birthday, email) values (27, 'Filip', '1988/04/27', 'fernshawq@typepad.com');
insert into employee (id, name, birthday, email) values (28, 'Brynna', '1925/10/02', 'bcordeletter@cnn.com');
insert into employee (id, name, birthday, email) values (29, 'Grethel', '1906/09/15', 'gnorthwoods@51.la');
insert into employee (id, name, birthday, email) values (30, 'Lemmie', '1983/11/05', 'lkeatest@arizona.edu');
insert into employee (id, name, birthday, email) values (31, 'Tuck', null, 'tgodrichu@simplemachines.org');
insert into employee (id, name, birthday, email) values (32, 'Tiphani', '1971/09/07', null);
insert into employee (id, name, birthday, email) values (33, 'Ardella', '1902/01/03', 'abottjerw@seattletimes.com');
insert into employee (id, name, birthday, email) values (34, 'Verile', '1907/06/28', 'vmquhargex@freewebs.com');
insert into employee (id, name, birthday, email) values (35, 'Lazar', null, 'lgershomy@artisteer.com');
insert into employee (id, name, birthday, email) values (36, 'Lorette', '1979/10/30', 'lashmolez@reuters.com');
insert into employee (id, name, birthday, email) values (37, 'Caye', null, null);
insert into employee (id, name, birthday, email) values (38, 'Donovan', '1935/07/12', 'dbierling11@arizona.edu');
insert into employee (id, name, birthday, email) values (39, 'Ira', '1992/05/09', 'iscampion12@umn.edu');
insert into employee (id, name, birthday, email) values (40, 'Genna', '2004/03/05', null);
insert into employee (id, name, birthday, email) values (41, 'Rosamund', '1984/07/08', 'rhalewood14@sina.com.cn');
insert into employee (id, name, birthday, email) values (42, 'Shaw', '2021/02/13', 'sfitzalan15@cloudflare.com');
insert into employee (id, name, birthday, email) values (43, 'Janetta', '1947/05/27', 'jacreman16@t-online.de');
insert into employee (id, name, birthday, email) values (44, 'Alvis', '1945/02/21', 'adominichetti17@linkedin.com');
insert into employee (id, name, birthday, email) values (45, 'Bride', null, null);
insert into employee (id, name, birthday, email) values (46, 'Desiri', '1984/03/20', 'djopke19@qq.com');
insert into employee (id, name, birthday, email) values (47, 'Tracy', '1940/01/22', 'tshilton1a@gov.uk');
insert into employee (id, name, birthday, email) values (48, 'Phaedra', '1901/08/17', 'pmowsdale1b@bloglovin.com');
insert into employee (id, name, birthday, email) values (49, 'Ellswerth', null, 'etomik1c@phoca.cz');
insert into employee (id, name, birthday, email) values (50, 'Cleon', '1997/10/09', 'chodges1d@fastcompany.com');

SELECT * FROM employee ;
-------

UPDATE employee
SET name = 'Lebron James' ,
	birthday = '1986-02-12' ,
	email = 'lebronjam@gmail.com'
WHERE id = 5 ;

SELECT * FROM employee ;
UPDATE employee
SET name = 'Damian Lillard' ,
	birthday = '1992-12-11' ,
	email = 'dami12345@gmail.com'
WHERE name LIKE '%t%t%' 
RETURNING * ;

UPDATE employee
SET name = 'Last Man' ,
	birthday = '1997-02-03' ,
	email = 'lastman23@ggmail.com'
WHERE id > 49 ; 

SELECT * FROM employee ;
UPDATE employee
SET name = 'Stephen Curry' ,
	birthday = '1989-12-05' ,
	email = 'stephen89@gswmail.com'
WHERE id > 40 AND birthday > '2000-01-01' ; 

SELECT * FROM employee ;
UPDATE employee
SET name = 'Kareem Abdulcabbar' ,
	birthday = '1945-07-05' ,
	email = 'kareem99@gswmail.com'
WHERE id < 15 AND birthday > '1905-01-01' 
RETURNING * ; 
-----
DELETE FROM employee
WHERE name = 'Kareem Abdulcabbar' 
RETURNING * ;

DELETE FROM employee
WHERE birthday IS NULL
RETURNING * ;

DELETE FROM employee
WHERE email IS NULL
RETURNING * ;

DELETE FROM employee
WHERE id > 33 ;

SELECT * FROM employee ;
DELETE FROM employee
WHERE birthday > '1980-01-01' 
RETURNING * ;
</details>

## :brain: Ödev 9

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
2-customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
3-customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
SELECT city.city , country.country FROM city
INNER JOIN country ON city.country_id = country.country_id ;

SELECT payment.payment_id , customer.first_name , customer.last_name FROM payment
INNER JOIN customer ON payment.customer_id = payment.customer_id;

SELECT rental.rental_id , customer.first_name , customer.last_name FROM rental
INNER JOIN customer ON rental.customer_id = customer.customer_id;
</details>
  
## :brain: Ödev 10

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.
1-city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
2-customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.
3-customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT city.city , country.country FROM city
LEFT JOIN country   ON  city.country_id = country.country_id ;

SELECT  payment.payment_id , customer.first_name , customer.last_name FROM payment
RIGHT JOIN customer   ON  payment.customer_id = customer.customer_id ;

SELECT  rental.rental_id , customer.first_name , customer.last_name FROM rental
FULL JOIN customer   ON  rental.customer_id = customer.customer_id ;
</details>
  
## :brain: Ödev 11

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.
2-actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.
3-actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.
4-İlk 3 sorguyu tekrar eden veriler için de yapalım.
### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
------  Soru 1 ------

(SELECT first_name FROM actor)

UNION

(SELECT first_name FROM customer);

------  Soru 2 ------

(SELECT first_name FROM actor)

INTERSECT

(SELECT first_name FROM customer);

------  Soru 3 ------

(SELECT first_name FROM actor)

EXCEPT

(SELECT first_name FROM customer);


------  Soru 4 ------
--
(SELECT first_name FROM actor)

UNION ALL

(SELECT first_name FROM customer);

--
(SELECT first_name FROM actor)

INTERSECT ALL

(SELECT first_name FROM customer);
</details>
  
## :brain: Ödev 12

### :question: SORU 
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

1-film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
2-film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
3-film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.
4-payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

### :green_square: CEVAP

<details>
<summary>Kodu görmek için tıklayınız.</summary>
SELECT COUNT(*) AS Longer_Films  FROM film
WHERE length >(SELECT AVG(length) FROM film) ;

SELECT COUNT(*) AS Heighest_Ren_Rate_Number FROM film 
WHERE rental_rate = (SELECT MAX(rental_rate) FROM film) ;

SELECT * FROM film 
WHERE rental_rate = (SELECT MIN(rental_rate) FROM film) 
AND replacement_cost = (SELECT MIN(replacement_cost) FROM film) ;

SELECT first_name , last_name , SUM(amount) AS Maximum_Shopping FROM customer
INNER JOIN payment ON customer.customer_id = payment.customer_id
GROUP BY payment.customer_id , customer.first_name ,customer.last_name
ORDER BY SUM(amount) DESC
LIMIT 10 ;
</details>
