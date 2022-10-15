# Financial Optimization 
> การจัด port ทางการเงินที่เหมาะที่สุด มีความเสี่ยงน้อย และได้กำไรเยอะ 


## What is Portfolio Optimization 
> > `pandas_datareader`

" Dont put all your eggs in one basket  "
ควรกระจายความเสี่ยงในการลงทุน = **portfolio selection problrm** 
การกระจายลงสิททรัพ โดยเพื่อให้ได้กำไรที่สูงสุด และความเสี่ยงต่ำสุด 


> Matkowiz's mean-varience (MV) model 
> - expect return = การได้มาจากการลงทุน 
> - varriance =  การได้คืนมาจาก expect return 

### Definitors 
**Portfolio** กลุ่มของสินทรัพย์ที่ลงทุดได้ หุ้น or bra
**Port weight** น้ำหนักที่ลงไปในแต่ละสินทรัพย์ 
**Expected return** ผลตอบแทนแบบท่วงน้ำหนักตาม wright ( ค่าเฉลี่ยตามตัดถ่วงน้ำหนัก )
**volatillity (risk)** ความเสี่ยงในการลงทุน 

>> ![[Screen Shot 2565-10-04 at 09.35.35.png | 300]]
>
>![[Screen Shot 2565-10-04 at 09.36.07.png | 400]]

```python 
from pandas_datareader 
import data as web 
import datetime as dt  
import pandas as pd  
import numpy as np

ticker = ['MSFT']
start = dt.datetime(2017, 1, 1)  
end = dt.datetime(2021, 12, 30)  
data = web.DataReader(ticker, 'yahoo', start, end) stocks = pd.DataFrame(data)  
stocks[ticker] = data['Adj Close'].pct_change()

```
---

## Steps of portfolio selection 
- คำนวณ  แลตอบแทนของ **Portfolio returns ** 
- คำนวณหา **Portfolio risk** ( ความผันผวนของรีเทิร์น )
	- คำนวฯ Covarriance matrix return 
	- คำนวณ Portfolio varriance  ( ความแปรปรวนของผลตอบแทนของพอร์ต )
	- Portfolio risk -> sqrt(Portfolio varriance )
- คำนวฯ Sharp ratio -> เอามาสร้างเป็น ratio ระหว่าง **Protfolio returns ** กับ **Portfolio risk**

### คำนวณ Portfolio returns 
- take หาค่าเฉลี่ยของ หุ้นแต่ละตัว 
- ลงน้ำฟหนักที่ใช้ลงใน port 

> 
![[Screen Shot 2565-10-04 at 09.55.00.png | 500]]


### คำนวณ Port risk 
ใช้เป็นความแปรปรวนข้องเกี่ยวจากหลาย ๆ ตัวแปร 
>>![[Screen Shot 2565-10-04 at 09.59.29.png]]

#### คำนวฯ Covarriance matrix return  ใน python 
#### คำนวณ portfolio variance from covariancee matrix (cov_mat)
![[Screen Shot 2565-10-04 at 10.04.42.png]]
####

### Sharp ratio 
**sharp ratio** is the average return earbed in excess of the risk free 

---


## Python code for portfolio selection 


```python

# define variable
	new_york = [
	    'ABBV', 'ACN', 'AVGO', 'BAC', 'BUD', 'C', 'CAT', 'CMCSA', 'CRM', 'CVX', 'DIS', 'DHR',
	    'FB', 'GE', 'GM', 'GOOG', 'GS', 'HD', 'HSBC', 'IBM', 'INTC', 'JNJ', 'JPM', 'KO', 'LLY',
	    'MA', 'MCD', 'MMM', 'MRK', 'MSFT', 'NFLX', 'NKE', 'NVDA', 'ORCL', 'PFE', 'PG', 'PYPL', 'QCOM',
	    'RY', 'SAP', 'SHOP', 'TRV', 'TSM', 'TXN', 'UNH', 'UPS', 'V', 'VZ', 'WFC', 'WMT', 'XOM'
	]
	
	bangkok = [
	    'ADVANC.BK', 'AOT.BK', 'AMATA.BK', 'BANPU.BK', 'BAY.BK', 'BBL.BK', 'CENTEL.BK', 'CK.BK', 
	    'CPALL.BK', 'CPF.BK', 'CPN.BK', 'DTAC.BK', 'EGCO.BK', 'INTUCH.BK', 'KBANK.BK', 'KCE.BK', 
	    'KTB.BK', 'LH.BK', 'MINT.BK', 'PSL.BK', 'PTT.BK', 'PTTEP.BK', 'PTTGC.BK', 'QH.BK', 'SCC.BK'
	]

# Parameter settings for this program!
	RF = 0.01        # risk-free interest, for calculating Sharpe ratio
	n_ports = 200    # number of trial (randomized) portfolio to be created
	#tickers = ['INTC', 'KO', 'BAC', 'BUD', 'TSLA', 'AAPL', 'AMZN', 'GOOG', 'K', 'SJM', 'CPALL.BK', 'PTT.BK']
	tickers = ['TSLA', 'AAPL', 'AMZN', 'GOOG', 'K', 'SJM', 'INTC', 'KO', 'BAC', 'BUD', ]
	
	start = dt.datetime(2018, 1, 1)
	end   = dt.datetime(2022, 6, 30)


```

---