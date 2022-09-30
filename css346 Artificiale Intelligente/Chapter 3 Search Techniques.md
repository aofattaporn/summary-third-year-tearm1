# Search Techniques 

## เกณในการวัดประสิทธิภาพของการค้นหา 
- **Completeness** - สามารถรับรองการค้นพบคำตอบได้  [ blind search ] สามารถทำได้ 
- **Optimality**   - สามารถรับรองการค้นหาคำตอบที่ดีที่สุดได้ [ path cost minimization ]
- **Time Complexity** - ระยะเวลาในการค้นหา 
- **Space Complexity** - พื้นที่หน่วยความจำที่ใช้ในการค้นหา 

## Type Searching 

### Blind Search
***Blind Search Techniques***  
เป็นการค้นหาโดยไม่มีเทคนิคการค้นหามาประกอบพิจารณา  ยากต่อการนำไปสู่คำตอบ / ง่ายในการเขียนโปรแกรม

![[Screen Shot 2565-09-26 at 16.03.18.png | 300]]
<img alt="./image/plot" src="./image/Screen Shot 2565-09-26 at 16.03.18.png" width="300"/>


#### Bidirectional Search
เป็นการค้นหาสองทิศทาง **สถานะเริ่มต้น**  และ **สถานะสิ้นสุด** พร้อม ๆ กัน 
( เน้นการอยากรู้ path ) ต้องรู้ว่าเป้าหมายของเราคืออะไร  ? 

![[Screen Shot 2565-09-26 at 16.25.47.png | 300]]
<img alt="./image/plot" src="./image/Screen Shot 2565-09-26 at 16.25.47.png" width="300"/>

- time complexity O(b^b/2) < O(b^2)
		- ถ้า BFS ใช้ memory ไป [1,111,111 node]
		- แล้ว Bidirectional search ใช้ไป [2,222 node]

#### Depth - Limited Search
ขีดเส้นจำกัดให้ DFS โดยมีค่า depth cutoof เป็นตัวจำกัดการค้นหา โดย เมื่อเทียบ DFS  O(b^d) and space O(bd)
โดยกำหนด DFS โดยการกำหนดชั้นเพื่อเปลี่ยนแถวมาค้นใหม่ 
 ![[Screen Shot 2565-09-26 at 17.59.58.png | 200]]

- Three possible outcomes : 
		- Solution ( [meet soliutions ])
		- Failure ( [no solutions] )
		- Cutoff ([ no solution within cutof ])
	
#### Iterative Deepening Search
> Provides the best of both ['BFS'] and ['DFS']

 ทำการ BFS ในชั้นที่ cutoof **K**  โดยมี space complexity is O(bd) or O(d)
**เมื่อ branching factor โตขึ้น จะเท่ากับจุดคคุ้มทุนของ ID**

#### SUMMARY 
	- BFS เจอคำตอบแน่ๆ แต่ [ เปลือง RAM ]
	- DFS ประหยัด RAM แต่ [ Neither complte, nor optimal ]
	- ID space complexity as DFS and time complexity as BFS 

--- 

### Heuristic Search 
> >***Heuristic Search Techniques***  
> เป็นการค้นหาโดยมีเทคนิคการค้นหามาประกอบพิจารณา  โดยในการพิจารณานั้นยอให้ขาดความสมบูรณ์ หรือไม่เจอคำตอบที่แท้จริงก็ตาม 
> 
> โดยมี `Heuristic function` ในการประเมินว่าเข้าใก้ล goal state มากแค่ไหน และเป็นตัวประเมินว่า เราจะสามารถหาคำตอบได้รวดเร็วแค่ไหน 
> 
> ![[Screen Shot 2565-09-26 at 16.03.42.png | 300]]
> <img alt="./image/plot" src="./image/Screen Shot 2565-09-26 at 16.03.42.png " width="300"/>
> >`Heuris tic function `  : พยามยามแตก state ออกมาและให้คะแนนหากทำดี 
> *** โดยพยายามไม่ให้ state นั้นเกิดการซ้ำกัน โดยใช้ `hash table` เช้าช่วยเช่น 2418563-7 เช็ค state exis
> *** ใช้ primary key ให้เป็นประโยชน์ โดยต้องการเช็คเร็วๆ เช็คผ่าน `index database`
> ![[Screen Shot 2565-09-26 at 20.31.08.png | 350]]
>  <img alt="./image/plot" src="./image/Screen Shot 2565-09-26 at 20.31.08.png " width="300"/>

#### Hill Climbing Search 
> จะไปตามเส้นทาง heuristic ดีตลอด จนกว่าจะใกล้เคียงกับ goal state มากที่สุด 

แบบอื่นๆ ของ Hill Climbing 
- **Steepast accent hill climbing** (ดูค่าลูกที่มีค่าที่ดีทีสุด แล้วไปทางนั้น )
ข้อเสียก็คือ `ปีนขึ้นอย่างเดียวไม่มีการปีนลง`

![[Screen Shot 2565-09-26 at 20.56.37.png | 200]]
<img alt="./image/plot" src="./image/Screen Shot 2565-09-26 at 20.56.37.png " width="300"/>
![[Screen Shot 2565-09-26 at 20.56.51.png | 500]]

#### Simulated Annealing  Search
> เป็นรูปแบบหนึ่งของ `hill climbing` ซึ่งยอมให้ไปในทิศทางที่ **ไม่ดีในช่วงเริ่มแรก** ของกระบวนการค้นหา 

เป็นกระวนการที่สามารถ **แก้ปัญหา Local Maximum**   จาก `Hill climbing` ได้ 
เปรียบกับการยอมให้มีการเลือกเส้นทางที่แย้บ้าง โดยเฉพาะในช่วงแรกของการค้นหา โดยใช้ **สมาการในการค้นหา** โดยในตัวอย่างใช้การเทียบกับ rand(0, 1)

![[Screen Shot 2565-09-30 at 16.20.34.png | 300]]
<img alt="./image/plot" src="./image/Screen Shot 2565-09-30 at 16.20.34.png " width="300"/>
<img alt="./image/plot" src="./image/Screen Shot 2565-09-30 at 16.34.16.png " width="300"/>
![[Screen Shot 2565-09-30 at 16.34.16.png | 200]]


##### Tabu

---

#### Tabu Search 
> Tabu แปลว่า ต้องห้าม ( กำหนดตามหน่วยความจำ ) ซึ่งจะปรับไปตามสภาพแวดล้อมและเวลา 

หน่วยความจำปรับตัว ( adaptive memory ) -> สำหรับการค้นหาอย่างมีประสิทธิภาพ 
การสำรวจแบบตอบสนอง ( responsie exploration ) -> เส้นทางเลวให้ข้อมูลเยอะกว่า 

หน่วยความจำที่ใช้ memory 
- **recency-beswd memory** 
- **frequency-based memory**

ความระเอียดความหลากหลาย ( intensification & diversification)
- เพิ่มความค้นหาแบบระเอียดในการค้นหาบริเวณใกล้เคียง 
- ค้นหาเพิ่มเติมในบริเวณที่แตกต่างกันจากคำตอบที่ดีที่เคยพบ 

Tabu ใช้หน่วยความจำสองแบบในการเปลี่ยนค่าใน memory 
- **short term memory** เป็นหน่วยความจำตามเวลา  N*(x)
	- เก็บคำตอบเร็ว ๆ นี้ ( solution attribute )
	- คุณสมบัติที่พบเร็ว ๆ นี้กำหนดเป็น ( tabu-active )

	![[Screen Shot 2565-10-01 at 00.20.30.png | 300]]
	<img alt="./image/plot" src="./image/Screen Shot 2565-10-01 at 00.20.30.png " width="300"/>
- **long teerm memory** หน่วยความจำตามความถี่  N(x)
	- ใช้สำหรับหาคำตอบใหม่ โดยที่ตัดออกจากค่าที่ได้จาก   ( short term momory )
	- ต้องไม่ใกล้เคียงต่อความทรงจำภายในอดีต 




### Game Search  
#### to [[Chapter 4 Game Search]]

---

