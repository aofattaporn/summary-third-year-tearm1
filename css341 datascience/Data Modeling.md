# Data Modelling 
---
## What is Optimization 
> ขึ้นอยู่กับ objective function 

#### Continuos Optimization 
- Objective function [ x^2 + y^3 >= 25 ]  # ส่วนมากมีส่วนของ min max 
- Descrision Version [x1, x2, x3, x4 ]
- Constrain 
	geneeric form of an optimization  
	[ minimize ]
	[ maximize ]


>ในการเลือกรับประทานบราวนี่ ไอศกรีมช็อคโกแลต น้ำอัดลม และชีสเค้ก ควรเลือกรับประทานอย่างไรให้เสีย ค่าใช้จ่าย 
น้อยที่สุด สมมติในแต่ละวันร่างกายต้องการพลังงานจากของหวานอย่างน้อย 500 แคลอรี และต้องการช็อคโกแลตอย่างน้อย 6 g น้ำตาลอย่างน้อย 10 g และไขมันอย่างน้อย 8 g รายละเอียดแสดงดังตาราง
`Objective function`   ควรเลือกรับประทานอย่างไรให้เสีย ค่าใช้จ่ายน้อยที่สุด
`decistion Variable`   จำวนวของขนมแต่ละประเภท 
`Boundaries`                   ความต้องการขั้นต่ำ
 `Constrains`                  ร่างกายต้องการพลังงานจากของหวานอย่างน้อย 500 แคลอรี

- Application of continuos optimization 
	- Financial prediction  = Customer spending 
	- Portfolio optimization = Mazimize return and Minimize risk 
	- Branch location planing = Greater customer engagement 
	- Winf farm optimization 
	- Structural optimization 
	- Chemical reaction optimization
	- Marginal cost and revenue optimization 
	- Vehical Routing Ploblem (VRP)
	- Humen-resouce allocation 
	- Job-shop Scheduling 
	
	


---


#### Discreate 

---
## Optimzation  Fomuration 
process of optimization 
- Need for optimization 
- เลือก decision variable 
- กำหนด objective function 
- กำหนดขอบเขตของแต่ละ variable 
- กำหนด constrains 
- เลือก optimization variable 
- execute the algorithm 

> เมื่อรวมหัวของนกกระสา เต่า และหมึกจำนวนหนึ่ง จะรวมได้ 32 หัว และ รวมขาทั้งหมดได้ 80 ขา ถามว่าจะต้องมีเต่าและหมึกรวมกันอย่างน้อยกี่ตัว
> `decistion variable ` จำนวน นก เต่า หมึก 
> `objective function`  ถามว่าจะต้องมีเต่าและหมึกรวมกันอย่างน้อยกี่ตัว
> `เงื่อนไขตัว` x + y + z = 32
> `เงื่อนไขของขา` 2x + 4y + 8z = 80
> `Boundary function` >= 0, integer 
> 

>