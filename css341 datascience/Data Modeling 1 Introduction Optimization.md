# Data Modelling 
---
Major modeling techniques for data science ['เราจะเลือก 1 ในหัวข้อของการทำ Modelling']
- Clustering 
- Classification 
- Regression 
- Asscoiation rule mining 
- **Optimization** 
- Dimensionality 


## What is Optimization 
> ว่าด้วยเรื่องเทคนิคทางคณิตศาสตร์ `ทำให้ผล f(x) ของ ค่าที่สุด ( **มากที่สุด** ไม่ก็ **น้อยที่สุด** )`
> > f(x) ขึ้นอยู่กับ objective function 
> > แบ่งเป็น 2 type = continuos , Discrete 
> 

### Continuos Optimization 
> การหาค่าเหมาะสมที่สุดของ f(x) ที่ต่อเนื่อง  แบ่งเป็น Constrained and Unconstrained

#### Components of a continuous optimization 
`Objective function` [ x^2 + y^3 >= 25 ]  # ส่วนมากมีส่วนของ min max 
`Descrision Version` [x1, x2, x3, x4 ] # ตัวแปรต่าง ๆ ที่มีผลต่อ objective function แต่ละตัวมีช่วงความเป็นไปได้ 
`Constrain` ขอบเขตความเป็นไปได้ ( Ineqality , Equality )
- `Ineqality` สมการกำหนดเขต
- `Equality` อสมการกำหนดขอบเขต 
- `bounary constraints` เงื่อนไขขอบเขตของ Descition Consteains  เท่านั้น

![[Screen Shot 2565-10-03 at 13.29.58.png | 200]]
<img alt="./image/plot" src="./image/Screen Shot 2565-10-03 at 13.29.58.png " width="400"/>

- Objective f (1)
- Decision variable ( x1, x2, x3, x4 )
- Boundary of decision variables (4)
- Constraints (2) (3)

#### Generic form 
- **minimize or maximize** f(x)
- subject to g(x) <= 0, i = 1,....,m (Inequality)
- subject to h(x) = 0, i = 1,....,p (Equality)

>>ในการเลือกรับประทานบราวนี่ ไอศกรีมช็อคโกแลต น้ำอัดลม และชีสเค้ก ควรเลือกรับประทานอย่างไรให้เสีย ค่าใช้จ่าย 
>น้อยที่สุด สมมติในแต่ละวันร่างกายต้องการพลังงานจากของหวานอย่างน้อย 500 แคลอรี และต้องการช็อคโกแลตอย่างน้อย 6 g >น้ำตาลอย่างน้อย 10 g และไขมันอย่างน้อย 8 g รายละเอียดแสดงดังตาราง![[Screen Shot 2565-10-03 at 13.41.25.png]]
>
`Objective function`   ควรเลือกรับประทานอย่างไรให้เสีย (ราคา) ค่าใช้จ่ายน้อยที่สุด
`decistion Variable`   จำวนวของขนมแต่ละประเภท  บราวนี่ , ไอศกรีมช็อค, น้ำอัดลม, ชีสเค้ก
`Boundaries`                   ไม่ติดลบ 
 `Constrains`                  ร่างกายต้องการพลังงานจากของหวานอย่างน้อย 500 แคลอรี มี 4 ข้อ 

#### Application of continuos optimization 
- **Financial prediction**  = Customer spending 
- **Portfolio optimization** = Mazimize return and Minimize risk 
- **Branch location planing** = Greater customer engagement 
- **Wind farm optimization**  = how to getting wind farm 
- **Structural optimization** 
- **Chemical reaction optimization**
- **Marginal cost and revenue optimization** 
- **Vehical Routing Ploblem (VRP)**
- **Humen-resouce allocation** 
- **Job-shop Scheduling** 
	

---



### Discreate  ( หาค่าความเหมาะสมของ f(x) โดยไม่มีการต่อเนื่อง )
- ตัวแปรจำนวนเต็ม ( Integer )
- ข้ออมูลเชิงการขัด ( conbinatorail variable )

---

## Optimzation  Fomuration 
[ process of optimization ] 
- Need for optimization 
- เลือก decision variable **พวก x1, x2, x3**
- กำหนด objective function **กำหนดค่าสมการ ที่จะทำให้ min max**
- กำหนดขอบเขตของแต่ละ variable **boundaries constrained**
- กำหนด constrains **พวก equality**
- เลือก optimization algorithm **วิธีการให้เลือกเยอะมาก** 
- execute the algorithm 

> >เมื่อรวมหัวของนกกระสา เต่า และหมึกจำนวนหนึ่ง จะรวมได้ 32 หัว และ รวมขาทั้งหมดได้ 80 ขา ถามว่าจะต้องมีเต่าและหมึกรวมกันอย่างน้อยกี่ตัว
> 
> 
> `decistion variable ` จำนวน นกx เต่าy หมึก z
> `objective function`  ถามว่าจะต้องมีเต่าและหมึกรวมกันอย่างน้อยกี่ตัว y + z min
> `constrained`
>  - `เงื่อนไขตัว` x + y + z = 32
>  - `เงื่อนไขของขา` 2x + 4y + 8z = 80
> `Boundary function` >= 0, integer 
> 


>>ปัญหาการเลือกสารอาหารทางด้านโภชนาการทาง เช่น มีอาหารอยู่ทั้งหมด 4 เมนู สิ่งที่เราสนใจคือ เราควรจะทานอาหารเมนูใดจำนวนเท่าไร จีงจะได้สารอาหารประกอบด้วย โปรตีน วิตามินและ ธาตุเหล็ก ครบตามความต้องการของร่างกาย โดยที่เสียค่าใช้จ่ายน้อยที่สุด
>>![[Screen Shot 2565-10-03 at 14.09.41.png | 300]]
>
> `decistion variable ` ปริมาณอาหารที่กินไปในแต่ละ memu x1 x2 x3 x4 
> `objective function`   เสียค่าใช้จ่ายในการกินน้อยสุด min x1 + x2 + x3 + x4  
> `constrained 3 ข้อ`
>  - `ปริมาณโปรตีน`  80x1 + 120x2 + 60x3 + 100x4 > 700
>  - `ปริมาณวิตามิน`  30x1 + 0x2     + 10x3 + 10x4    > 250 
>  - `ปริมาณเหล็ก`    15x1  + 10x2   +  20x3 + 5x4    > 300
> `Boundary function` >= 0, floating 

### How complex is an optimization problem 
- **Fitness landscape ( or contour )** ลองเอา decistion variable มา plot เป็น กราฟ 
- จำนวนลักษณะของ Local optima 
- จำนวน decistion variable 
- ปัญหาที่ constraints/objective เป็น nonlinear 
- decistion variables มีความต่อเนื่อง 

## Solving continuous optimization 
### Differentiable functions 
#### Hessian matrix or second derivative 
- Univariate e.g. Newton's method 
#### Gradient or first derivative 
- สามารถ diff ได้ 
### Non Differentable functions 
> พวก y = x^ 1/3, y = |x|
#### Direct Algorithm 
เอา Gradient infomation is approximated directly 

#### Population-based stochastic algorithm ***
make use of **randomness** in the search procedure ( ใช้การ random ในการกระจายหาหลายจุด ) เลี่ยง local optima  ได้ดี
**Better avoid local optima** 
- Diiferentail evolution (DE)
- Genetic algorithms (GA)
- Ant Colony optimization (ACO)

## Differentail evolution (DE)
> เป็น search algoritms ที่เป็น Population-based stochastic algoritms  แบบ Continious
> อาศัยจุดคำตอบจำนวนมาก = candidate solutions call vectors 
> iteration ให้ cadidate วิ่งไปหาคำตอบที่ดีที่สุด  = converge ( Evotionary )
> Mutation -> CrossOver 
> ข้อดีคือ ไม่สนอะไรเลย หากคิด objectivve function ขึ้นมาได้ 
> 
> >- Initailize population ( หา candidate ) -> PopSize (จำนวน candidate)
> >- นำตัว candidate มาทำการ mutation  -> F (จำนวนการทำ mutation) -> มีหลายวิธี ( rand/1/bin )
> >- ทำการ corossover 
> >- แทนที่ตัวเดิม (หาดเทียบกับ target ละดีกว่า เช่น max min )
> > ![[Screen Shot 2565-10-03 at 15.18.40.png | 350]]
> > ![[Screen Shot 2565-10-03 at 14.40.50.png | 350]]


**ภายใน python มี scipy.optimize.differentail_evolution**

![[Screen Shot 2565-10-03 at 15.25.11.png | 400]]


## hands-on labs using Ptython's scipy 
### Part 1 Solving ( multivariable ) linear programming problems
> ค่าตัวแปร ( decistion variable ) ไม่มีตัวไหน ยกกำลังสองเลย 

ใช้ form ที่ scipy ต้องการ โดยใช้ **scipy.optimize.linprog **

![[Screen Shot 2565-10-03 at 15.32.36.png | 300]]


> > ![[Screen Shot 2565-10-03 at 17.26.45.png | 300]]
```python
import numpy as np
from scipy.optimize import linprog

#The coefficients of the linear objective function to be minimized.
	c = np.array([-29.0, -45.0, 0.0, 0.0])

#Each row of A_ub specifies the coefficients of a linear inequality constraint on x.
	lhs_ineq = np.array([[1.0, -1.0, -3.0, 0.0],
	                 [-2.0, 3.0, 7.0, -3.0]])

# Each element represents an upper bound on the corresponding value of A_ub @ x.
	rhs_ineq = np.array([5.0, -10.0])

# Each row of A_eq specifies the coefficients of a linear equality constraint on x.
	lhs_eq = np.array([[2.0, 8.0, 1.0, 0.0],
                 [4.0, 4.0, 0.0, 1.0]])

# Each element of A_eq @ x must equal the corresponding element of b_eq.
	rhs_eq = np.array([60.0, 60.0])

# defining the minimum and maximum values of that decision variable. 
# Use None to indicate that there is no bound. By default, bounds are (0, None)
# (all decision variables are non-negative).
	x0_bounds = (0, None)
	x1_bounds = (0, 5.0)
	x2_bounds = (-np.inf, 0.5)  # +/- np.inf can be used instead of None
	x3_bounds = (-3.0, None)
	bounds = [x0_bounds, x1_bounds, x2_bounds, x3_bounds]

# run the linprog() function to optimize the linear programming
	result = linprog(c, A_ub=lhs_ineq, b_ub=rhs_ineq, A_eq=lhs_eq, b_eq=rhs_eq, bounds=bounds)
	
	print(result)
```

### Part 2 find anser by gradient 

> scipy.optimize.minimize 
> ( เป็นการใช้ gradient )




### Part 3 DE from scipy library  
