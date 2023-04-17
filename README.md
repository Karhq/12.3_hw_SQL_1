# Домашнее задание к занятию «SQL. Часть 1» - Карпов Роман

Задание можно выполнить как в любом IDE, так и в командной строке.

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

#### Ответ:  
```sql
SELECT DISTINCT district from address
where district like 'K%a' and district not like '% %'
```
![Скрин](https://github.com/Karhq/12.3_hw_SQL_1/blob/main/Nom1.png)

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

#### Ответ:  
```sql
select payment_id, payment_date, amount, CAST(payment_date AS DATE) from payment
where payment_date between '2005-06-15' and '2005-06-19' and amount > 10
order by payment_id desc
```
![Скрин](https://github.com/Karhq/12.3_hw_SQL_1/blob/main/Nom2.png)  

### Задание 3

Получите последние пять аренд фильмов.

#### Ответ:  
```sql
select rental_id, rental_date, return_date, customer_id from rental
order by rental_date desc
limit 5
```
![Скрин](https://github.com/Karhq/12.3_hw_SQL_1/blob/main/Nom5.png)  


### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

#### Ответ:  
```sql
select lower(first_name), replace(first_name, 'LL', 'PP') from customer
where first_name = 'Kelly' or first_name = 'Willie'
```
![Скрин](https://github.com/Karhq/12.3_hw_SQL_1/blob/main/Nom6.png)  




