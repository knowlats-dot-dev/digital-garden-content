---
title: " SQL for Data Analyst"
updated: 2026-03-31T05:58:09+07:00
tags:
  - data-science
  - course
  - note
---
คำสั่ง [[sql]] ที่ใช้ใน [[data-science]]

ส่วนหนึ่งของ [[course-data-science-bootcamp-12]]

# SELECT

```
SELECT
	firstname,
	lastname,
	firstname || ' ' || lastname AS fullname
	LOWER(firstname) || '@company.com' AS email
FROM customers;
```

คำสั่ง SELECT เป็นคำสั่งที่ใช้บ่อยที่สุด โดยทั่วไปมันใช้ในการเรียกดูข้อมูล มันสามารถใช้คำนวณข้อมูลได้ด้วย ตามตัวอย่างข้างบนเป็นการสร้างคอลัมน์ใหม่ (ที่ใช้แสดงข้อมูล) และต่อ string

ตัวอย่างข้างล่างเป็นการคำนวณจริง ๆ

```
SELECT
	name,
	milliseconds / 60000 AS minute,
	bytes / (1024*1024) AS mb
FROM track;
```

จะได้จำนวนเต็ม ถ้าอยากได้จำนวนทศนิยม เติม .0 ที่ตัวเลขในสูตร ก็จะได้ แต่จะได้หลายตำแหน่ง

เราสามารถครอบด้วย ROUND

```
SELECT
	name,
	ROUND(milliseconds / 60000.0, 2) AS minute,
	ROUND(bytes / (1024*1024.0), 2) AS mb
FROM track;

```

เราสามารถ Filter ได้ด้วย WHERE

```
SELECT
	firstname,
	lastname
FROM customers
WHERE age >= 60;
```
```

```

# CASE WHEN

แสดงข้อมูลตามเงื่อนไข เหมือนการทำ  `if-else` หรือ `switch`

```
SELECT 
	country,
	CASE 
		WHEN country IN ('Canada', 'USA') THEN 'America' 
		WHEN country IN ('Belgium', 'France', 'Italy') THEN 'Europe' 
		ELSE 'Other' 
	END AS region
FROM customers;
```

# DATE TIME

ดึง ปี เดือน วัน ใช้ STRFTIME() (มีใน SQLite เท่านั้น)

```
SELECT
	invoicedate,
	STRFTIME('%Y', invoicedate) AS year,
	STRFTIME('%m', invoicedate) AS month,
	STRFTIME('%d', invoicedate) AS day
FROM invoices;
```