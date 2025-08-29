---
trigger: always_on
alwaysApply: true
---
## กฏการตั้งชือ Table และ Field ในการออกแบบฐานข้อมูล
1. ชื่อ Table  รูปแบบการตั้งขื่อ  TXXYName
	1.1 T = แทน ความหมายTable จะกำหนด Fixed เป็น T เสมอ
	1.2 XX= แทน ชื่อย่อของระบบ สามารถสร้างใหม่เองได้ ความยาว 2 ตัวอักษร เช่น
		PS หมายถึงกลุ่ม POS
		FN หมายถึงกลุ่ม Finance 
		TK หมายถึงกลุ่ม Ticket
		FB หมายถึงกลุ่ม Food and Beverage
		CN หมายถึงกลุ่ม Center สำหรับใช้งานทุกระบบ เช่น TCNMPdt หลักต่างๆ
		AP หมายถึงกลุ่ม Accounts payable เช่น TAPTOrder
		AR หมายถึงกลุ่ม Accounts receivable เช่น TARTSiHD,TARTSiDT
	1.3	Y= แทนตัวอักษรตำแหน่งที่ 3 เสมอ ประกอบด้วย
		M  กรณีข้อมูลเป็นส่วนที่นำไปใช้ในระบบ เช่น ชื่อสินค้า เครื่องจุดขาย พนักงาน ลูกค้า
	    T  กรณีข้อมูลที่เป็นประวัติการทำรายการและมักมีวันที่เป็น ตัวอ้างอิงเหตการณ์ เช่น เอกสารการขาย ใบสั่งซื้อ 
	    S  กรณีข้อมูลเป็นการ Config System ระบบ จัดการโดย Programmer   
	1.4 Name = แทนความหมายชื่อตารางยาวไม่เกิน 12 ตัวอักษร	เช่น	TARTSiHD >> Name =SiHD
	
2. ชื่อ Field รูปแบบการตั้งขื่อ  FXAbcName
		F: Table fixed เป็นตัวแรกของชื่อตารางเสมอ
		2.1 F = แทน ความหมาย Field จะกำหนด Fixed เป็น F เสมอ
		2.2 X = แทน Data Type ของข้อมูลที่จะจัดเก็บใน Field ประกอบด้วย
			T หมายถึงข้อมูลที่เป็น Text String หรือ ข้อความตัวอักษรประกอบ
			D หมายถึงข้อมูลที่เป็น Date datetime format datetime
			N หมายถึงข้อมูลที่เป็น ตัวเลขแบบที่ไม่มี ทศนิยม
			C หมายถึงข้อมูลที่เป็น ตัวเลขแบบที่่มี ทศนิยม
		2.3 Abc = แทนชื่อย่อของชื่อตาราง ใช้ 3 ตัวอักษร ทุก Field ใน ตาราง ที่ไม่ใช้ Forieng key จะต้องเป็นค่าเดียวกัน เช่น 
			ตารางสินค้า Name =Pdt ดังนั้น Abc = Pdt
			ตารางโปรโมชั่น Name=Promotion ดังนั้น Abc = Pmt
			ตารางธนาคาร Name =Bank ดังนั้น Abc = Bnk
		2.4 Name = แทนความหมายชื่อ Field ยาวไม่เกิน 10 ตัวอักษร  เช่น
			Code ,CstDOB  , Amt , Age,Promotion,Coupon 
		2.5 ตัวอย่างเมือเอาเงือนไข 2.1-2.4 มาสร้าง
		     ตาราง TFNMBank (FTBnkCode,FTBnkName,FCBnkAmt,FDBnkRegis)   