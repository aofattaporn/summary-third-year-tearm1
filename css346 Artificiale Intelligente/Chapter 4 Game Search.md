# Game Search 
## การเล่นเกม 
การที่เล่นจะเป็น **tic-tac-toe** / **snack 4** / **othello**  จะเล่นยังไงให้พวกนี้เล่นดีที่สุด 
### Types of Game AI 
- Single search  define by 4 state of problem 
- Game search ( Adversary Search )
	- Initail state 
	- Successor function 
	- Terminal Test 
	- Utilly / payoff function 

### Classes of Games ( ประเภทของเกม ) 
- Deterministic ( เห็นสถานะการทำเกมเดาอนาคตได้ ) v. Non-deteministic ( เดาไม่ได้ random )
- Perfect Infomation ( รู้สถาการณ์ทั้งหมดในเกม ) v. Imperfect infomation ( ไม่รู้สถาการณ์ทั้งหมด )
- Zero-sum ( มีผู้แพ้ผู้ชนะ ) v. Non-zero sum ( win ทั้งคู่ )

![[Screen Shot 2565-10-01 at 15.16.13.png | 400]]

<img alt="./image/plot" src="./image/Screen Shot 2565-10-01 at 15.16.13.png " width="300"/>

## Adversarial Searc ( การค้นหาแบบปรปักษ์ ) 
> เป็นเทคนิคการค้นหาในการเล่นเกม `แบบมีฝ่ายตรงข้าม` เท่านั้น โดย AI จะมีการคิดว่า 
สิ่งที่ไม่สามารถคาดเดาได้ -> **มองโลกในแง่ร้ายที่สุด** 
เวลามีจำกัด -> **ได้เท่าไหร่ก็เอาแค่นั้น ไม่ก็ประมาณค่าเอา** 
> > ทุก ๆ ครั้งที่ทำการเล่น  AI จะแตก state ลงไปเรื่อย ๆ เพื่อหาความเป็นไปได้ทั้งหมด  = memory เยอะเท่าไหร่ AI ยิ่งเก่งเท่านั้น 
---


### Minimax 
#### การทำงานของ Minimax Alogorithm
- มีการทำ DFS ไปในชั้นที่ N ใด  = DLS -> space compaxity O(bd)
- Utility Function เพื่อหาค่าของคามดี node นั้น ๆ 
- ส่งค่าไปให้ node บนในการตัดสินใจ 
	- **parent Max **  จะคืนค่า max โหนดลูก
	- **parent Min ** จะคืนค่า min โหนดลูก 
- ใช้เทคนิคของ recursive ( เน้นในการ กิน memory ) 

**Max** ต้องทำคะแนนให้มากที่สุด (Player)
**Min** Max คะแนนน้อยที่สุด  (AI)

> > เป็นการเลือกเส้นทางที่ให้ค่าน้อยมากที่สุด 


![[Screen Shot 2565-10-02 at 15.55.33.png | 300]]

<img alt="./image/plot" src="./image/Screen Shot 2565-10-02 at 15.55.33.png " width="300"/>

แก้ให้เขียนโดยเป็น double Recursive 

![[Screen Shot 2565-10-02 at 15.56.59.png | 300]]

![[Screen Shot 2565-10-02 at 16.03.10.png | 300 ]]
<img alt="./image/plot" src="./image/Screen Shot 2565-10-02 at 16.03.10.png " width="300"/>

<img alt="./image/plot" src="./image/Screen Shot 2565-10-02 at 15.56.59.png " width="300"/>

#### การวัดประสิทธิภาพ 
- Complete = ถ้าความลึกในชั้น terminal มี memory พอ เจอชัวๆ !!
- Optimal = คู่แข่งยิ่งเก่ง AI เก่งตาม 
- Time = O(b^m)
- space = O(bm)

> ในกรณีหมากรุก มีคำตอบเกินกว่าที่ computer จะรับไหม ไม่ optimal ขึ้นอยู่กับ  HDD

## การแตกกิ่งแบบ alpha beeta 

> Alpha-Brta Cut off คือการตัดสาขาที่ไม่มีผลต่อการตัดสินใจเลือกทิ้งไป 
> >ปรับปรุงจาก Mini max โดยไม่คำนวณในบางกิ่ง 
> > a และ b ลงไปแต่ละ node ที่กำลังค้นหา 
> > a เก็บค่าที่ดีที่สุดของ Max โหนดที่เคยหามา  ค่าไม่มีทางเพิ่มขึ้น
> > b เก็บค่าที่ดีที่สุดของ min โหนดที่เคยเห็นมา  ค่าไม่มีทางลดลง 
> 
> ---
hint : ทุกครั้งที่แตก state เช็คจาก a และ b 

ควรแตก state ให้ operation มีการเรียงกัน ( critical palce )

![[Screen Shot 2565-10-02 at 16.24.48.png | 300]]

<img alt="./image/plot" src="./image/Screen Shot 2565-10-02 at 16.24.48.png " width="300"/>