# SQL2
<<<<<<< HEAD
=======
# Домашнее задание к занятию "`SQL2`" - `Klochkov Vladimir`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1
* [link to screen](https://github.com/Klochkov777/SQL2/blob/master/screens/1.png)

### Задание 2
* [link to screen](https://github.com/Klochkov777/SQL2/blob/master/screens/2.png)

### Задание 3

* [link to screen](https://github.com/Klochkov777/SQL2/blob/master/screens/3.png)


простыня всех запросов:

* SELECT s.store_id, s2.first_name, s2.last_name, a.address, COUNT(c.customer_id) from store s 
JOIN staff s2 on s.store_id = s2.store_id 
JOIN customer c on s.store_id = c.store_id 
JOIN address a on a.address_id  = s.store_id
GROUP by s.store_id, s2.first_name, s2.last_name, a.address
HAVING COUNT(c.customer_id) > 300;

* select COUNT(*) as 'count of films'
from film f
WHERE f.`length` > (
	select AVG(f2.`length`) 
	from film f2);

* SELECT EXTRACT(MONTH FROM p.payment_date) AS payment_month, 
SUM(p.amount) AS total_amount, COUNT(r.rental_id) AS count_rentals 
FROM payment p 
JOIN rental r ON p.rental_id = r.rental_id 
GROUP BY payment_month 
ORDER BY total_amount 
DESC  
limit 1;
