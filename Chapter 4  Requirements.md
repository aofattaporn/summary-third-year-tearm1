# Requirements 
เวลาที่เราจะสร้างอะไร คุณต้องรู้ก่อนว่า **คุณต้องรู้ก่อนว่าคุณต้องการอะไรบ้าง** โดยเนื้อหามักจะเกี่ยวกับ การได้บ้าง เนื่องจาก Requirements ที่แท้จริงและประเภทของ Requiremetns นั้นเอง และมีการวิเคราะห์อย่างไรบ้าง 

> Defination :  การได้มาของ Characteristics ของระบบโดยต้องตอบ **โจทย์ทั้ง** explicit and **Implicit**

- **Explit Need** ความต้องการของ user ที่สามารถเห็นได้ด้วยตาเปล่า 
- **Implicit Need** ความต้องการของ user ที่ไม่สามารเห็นได้ด้วยตา *( ยากต่อการแปลงเป็น requirements )*

#### domain for design solfware 

![[Screen Shot 2565-09-28 at 14.50.04.png | 300]]

- **Ploblem domain** ยุ่งเกี่ยวกับการ เก็บข้อมูล โดยการอธิบายปัญหาของ customer และนำมา วิเคราะห์ 
	- โดยที่ สิ่งที่ ==user บอก = customer problem statement != requirements !== 
	- ไม่ควรเอาที่ user บอกนั้นมาทำ solution ในการแก้ปัญหาจริง เพราะสำหรับบางคน อาจมี bias !! 
	- นำ ==Requirements ( customer problem ที่ทำการวิเคราะห์แล้ว ) --> Specification --> Program== 
- **Software (solution) domain** 

#### Problem Analysis 
- **Problem** User is delayed to work and needs help 
	- Cause A Traffic is unpredicable 
	- Cause B User is unfamiliar with the route 
	- Cause C USe has a habit of starting rate 