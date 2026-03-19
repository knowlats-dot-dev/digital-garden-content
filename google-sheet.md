---
title: Google Sheet
updated: 2026-03-20T02:08:25+07:00
tags:
  - tools
  - data-science
  - bootcamp
---
[[tools]]
Part of [[course-data-science-bootcamp-12]]

# 101
## Why Google Sheet?

- **Store** Structured Data
- **Analyze** Data
- Chart & **Present** Data

## Manually Input

- พิมพ์ข้อมูลบน Cell โดยตรง
- เพิ่มข้อมูลแบบ Array 
	- ใส่ ={data1, data2, data3} ใน Cell แรก มันจะกระจายข้อมูลไปยัง Cell ข้าง ๆ ต่อกัน 
	- พิมพ์ ; แทน , มันจะกระจายในแนวตั้ง
	- สามารถใส่เป็น Matrix แค่ใส่ , และ ; 
		- มีข้อจำกัดคือ ต้องใส่ให้ทุกแถว และทุกคอลัมน์มีจำนวนเท่ากันหมด เช่น ใส่ 3 แถว แถวละ 2 ตัวเท่ากัน ไม่งั้นจะขึ้น `#VALUE!`

## Cell Reference
| การพิมพ์ในช่อง formula | ความหมาย                                                                                                                       |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| A1                     | ไม่มีการล็อก Cell - เวลากดเลื่อน Cell เพื่อก้อปสูตร มันจะปรับตามตำแหน่งที่อยู่เลย                                              |
| $A$1                   | Absolutely reference - ไม่ว่าจะกดเลื่อนออกที่ไหน มันจะคงตำแหน่งนี้เสมอ กด `F4` เพื่อ Lock Cell แบบนี้                          |
| A$1                    | กดเลื่อนด้านข้าง (Column) มันจะเปลี่ยนตำแหน่งตัวซ้าย แต่ถ้ากดเลื่อนขึ้นลง มันจะได้ค่าเดิมเพราะมีการล็อกตำแหน่งแถว (Row) เอาไว้ |
| $A1                    | กดเลื่อนลง (Row) จะเปลี่ยนตำแหน่งตัวขวา แต่ถ้ากดเลื่อนไปทางขวาซ้าย จะได้ค่าเดิมเพราะมีการล็อกตำแหน่งคอลัมน์ (Column) เอาไว้    |
## Keyboard Shortcut

https://support.google.com/docs/answer/181110
## What is function 

หน้าที่ของ Function คือ เปลี่ยนจาก Input -> Output

ลักษณะการพิมพ์คือ = functionName(value, reference, ...)

ตัวอย่าง Analysis Function

- =COUNTA( employee ) 
- =MIN( salary )
- =MAX( salary )
- =AVERAGE( salary ) 
- =SUM( salary )

### Array Formula

เราสามารถพิมพ์ Formula ได้โดยไม่ต้องก้อปโดยพิมพ์กำหนด Range (`cellRefStart:cellRefEnd`) ในสูตร แล้วกด

- Windows : `CTRL+SHIFT+ENTER`
- Mac: `CMD+SHIFT+ENTER` (command)

มันจะมี `=ArrayFormula()` ครอบสูตรของเรา จากนั้นกด Enter มันจะคำนวณผลตามสูตรและใส่ Cell ตามแนว Range ที่กำหนด

### IF

`=IF(condition, value_if_true, value_else)`

Nested If (Old,Not recommended)

`=IF(condition, value_if_true, IF(condition2, value_if_true, ...))`

IFS

`=IFS(condition, value_if_true, condition2, value_if_true, ...)`

AND, OR, NOT ใช้ใน IF ได้ แต่ใช้ร่วมกับ ArrayFormula ไม่ได้

### Switch

`=SWITCH(range, value1, result1, value2, result2, ...)`

### Median

หาค่ากลางใน range

Step

1. Sort ด้วย `=SORT(range)`
2. `=MEDIAN(range)`

###  AVERAGEIF and SUMIF

- AVERAGEIF ใช้หาค่าเฉลี่ยเมื่อ `range` มี condition ตามเกณฑ์ `=AVERAGEIF(range_if, condition, range_to_cal)`
- SUMIF ใช้หาผลรวมเมื่อ `range` มี condition ตามเกณฑ์ `=SUMIF(range_if, condition, range_to_cal)`