--Lab ในชั้นเรียนวันที่ 6 สิงหาคม 2569
--ใช้ ฐานข้อมุล Northwind เพื่อ Query ข้อมูลต่อไปนี้
select*from Products
select*from Employees
select*from custoers

--1.ต้องการ คำนำหน้า ชื่อ นามสกุล พนักงาน ที่อยู่ในเมือง London
select TitlefCourtesy ,firstname, lastname
from Employees
where location = 'London'

--2.ข้อมูล รหัสสินค้า ชื่อสินค้า ราคา จำนวน ของสินค้าที่มีจำนวนน้อยกว่า 30
select ProductsID,ProductsName,UnitPrice from 

--3.รหัสลูกค้า ชื่อบริษัท เบอร์โทรศัพท์ ของลูกค้าที่อยู่ในประเทศต่อไปนี้
--    Sweden, Germany, France, Spain, UK
select CustomerID,CompanyName,phone
from Customers
where Custry in('sweden','Germany','France','Spain','UK')
--4.ข้อมูลลูกค้าที่ไม่มีหมายเลขโทรสาร (Fax)
select * from Customers
where fax is NULL;
--5.ข้อมูลสินค้าที่มีจำนวนสินค้าต่ำกว่าจุดสั่งซื้อ และ มีจำนวนที่สั่งซื้อแล้ว
select * from Products where UnitsInStock < Reorderlevel
and UnitsOnOrder > 0;
--6.ชื่อ นามสกุล พนักงานที่เข้าทำงานในปี 1992
select firstname, lastname
from Emloyees
wher YEAR(HireDate) = 1992

--7.ต้องการข้อมูลสินค้าที่มีราคาตั้งแต่ 20-70
select * from Products
where UnitPrice between 20 and 70;

--8.ข้อมูลลูกค้าที่มีชื่อบริษัทขึ้นต้นด้วย S และอยู่ประเทศ Mexico
select CustomerID, CompanyName,Countryfrom 
from dbo.Customers
and Coutry = 'Mexico';
--9.ข้อมูลลูกคาที่มีตำแหน่งของผู้ที่ประสานงานเป็น Manager
select * from Customers
where ContactTitle like '%Manager%';
