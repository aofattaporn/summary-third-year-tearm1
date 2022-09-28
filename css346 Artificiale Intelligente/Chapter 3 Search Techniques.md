# Search Techniques 

## เกณในการวัดประสิทธิภาพของการค้นหา 
- **Completeness** - สามารถรับรองการค้นพบคำตอบได้  [ blind search ] สามารถทำได้ 
- **Optimality**   - สามารถรับรองการค้นหาคำตอบที่ดีที่สุดได้ [ path cost minimization ]
- **Time Complexity** - ระยะเวลาในการค้นหา 
- **Space Complexity** - พื้นที่หน่วยความจำที่ใช้ในการค้นหา 

## Type Searching 

#### Blind Search
> ***Blind Search Techniques***  
> เป็นการค้นหาโดยไม่มีเทคนิคการค้นหามาประกออบพิจารณา 
> ยากต่อการนำไปสู่คำตอบ / ง่ายในการเขียนโปรแกรม
> 
> ![[Screen Shot 2565-09-26 at 16.03.18.png | 300]]

- **[ Bidirectional Search] ** 
	>  เป็นการค้นหาสองทิศทาง ['สถานะเริ่มต้น'] และ ['สถานะสิ้นสุด'] พร้อม ๆ กัน 
	>  ( เน้นการอยากรู้ path ) ต้องรู้ว่าเป้าหมายของเราคืออะไร  ? 
	>  ![[Screen Shot 2565-09-26 at 16.25.47.png | 300]]

	- time complexity O(b^b/2) < O(b^2)
		- ถ้า BFS ใช้ memory ไป [1,111,111 node]
		- แล้ว Bidirectional search ใช้ไป [2,222 node]

- **[ Depth - Limited Search] ** 
	> ขีดเส้นจำกัดให้ DFS โดยมีค่า depth cutoof เป็นตัวจำกัดการค้นหา 
	> โดย เมื่อเทียบ DFS  O(b^d) and space O(bd)
	> โดยกำหนด DFS โดยการกำหนดชั้นเพื่อเปลี่ยนแถวมาค้นใหม่ 
	> ![[Screen Shot 2565-09-26 at 17.59.58.png | 200]]

	- Three possible outcomes : 
		- Solution ( [meet soliutions ])
		- Failure ( [no solutions] )
		- Cutoff ([ no solution within cutof ])
	
- **[Iterative Deepening Search]**
	> Provides the best of both ['BFS'] and ['DFS']

	- ทำการ BFS ในชั้นที่ cutoof **K**  โดยมี space complexity is O(bd) or O(d)
		**เมื่อ branching factor โตขึ้น จะเท่ากับจุดคคุ้มทุนของ ID**

- ***[SUMMARY]*** 
	- BFS เจอคำตอบแน่ๆ แต่ [ เปลือง RAM ]
	- DFS ประหยัด RAM แต่ [ Neither complte, nor optimal ]
	- ID space complexity as DFS and time complexity as BFS 

--- 

#### Heuristic Search 
> ***Heuristic Search Techniques***  
> เป็นการค้นหาโดยมีเทคนิคการค้นหามาประกอบพิจารณา  โดยในการพิจารณานั้นยอให้ขาดความสมบูรณ์ หรือไม่เจอคำตอบที่แท้จริงก็ตาม 
> 
> โดยมี `Heuristic function` ในการประเมินว่าเข้าใก้ล goal state มากแค่ไหน และเป็นตัวประเมินว่า เราจะสามารถหาคำตอบได้รวดเร็วแค่ไหน 
> 
> ![[Screen Shot 2565-09-26 at 16.03.42.png | 300]]
> `Heuris tic function `  : พยามยามแตก state ออกมาและให้คะแนนหากทำดี 
> *** โดยพยายามไม่ให้ state นั้นเกิดการซ้ำกัน โดยใช้ `hash table` เช้าช่วยเช่น 2418563-7
> ![[Screen Shot 2565-09-26 at 20.31.08.png | 350]]

###### Hill Climbing Search 
> จะไปตามเส้นทาง heuristic ดีตลอด จนกว่าจะใกล้เคียงกับ goal state มากที่สุด 

ข้อเสียก็คือ `ปีนขึ้นอย่างเดียวไม่มีการปีนลง`

![[Screen Shot 2565-09-26 at 20.56.37.png | 200]] ![[Screen Shot 2565-09-26 at 20.56.51.png | 500]]

##### Simulated Annealing 
##### Tabu

---

#### Game Search 

---

