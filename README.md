# Relational_database_Project

CREATE DATABASE BookStore;
use BookStore;
/*==============================================================*/
/* Table: AUTHOR */
/*==============================================================*/
drop table if exists AUTHOR;
create table AUTHOR
(
AUTH_ID varchar(10) not null,
AUTH_NAME char(20) null,
AUTH_ADDRESS char(100) null,
constraint PK_AUTHOR primary key clustered (AUTH_ID)
);
/*==============================================================*/
/* Table: BOOK */
/*==============================================================*/
drop table if exists BOOK;
create table BOOK
(
BOOK_ID varchar(10) not null,
BOOK_PRICE float null,
BOOK_ISBN varchar(20) not null,
AUTH_ID varchar(10) null,
BOOK_TITLE varchar(50) null,
BOOK_YEAR integer null,
constraint PK_BOOK primary key clustered (BOOK_ID, BOOK_ISBN)
);
/*==============================================================*/
/* Table: CUSTOMER */
/*==============================================================*/
drop table if exists CUSTOMER;
create table CUSTOMER
(
CUST_ID varchar(10) not null,
CUST_NAME char(20) null,
CUST_ADDRESS varchar(200) null,
CUST_PHONE integer null,
CUST_EMAIL varchar(20) not null,
constraint PK_CUSTOMER primary key clustered (CUST_ID, CUST_EMAIL)
);
/*==============================================================*/
/* Table: HAVE */
/*==============================================================*/
drop table if exists HAVE;
create table HAVE
(
SHOP_ID varchar(10) not null,
BOOK_ID varchar(10) not null,
BOOK_ISBN varchar(20) not null,
constraint PK_HAVE primary key clustered (SHOP_ID, BOOK_ID, BOOK_ISBN)
);
/*==============================================================*/
/* Table: PUBLISHER */
/*==============================================================*/
drop table if exists PUBLISHER;
create table PUBLISHER
(
PUB_ID varchar(10) not null,
BOOK_ID varchar(10) null,
BOOK_ISBN varchar(20) null,
PUB_NAME char(30) null,
PUB_ADDRESS varchar(250) null,
PUN_PHONE integer null,
PUB_URL varchar(1024) null,
constraint PK_PUBLISHER primary key clustered (PUB_ID)
);
/*==============================================================*/
/* Table: SHOPPING_CART */
/*==============================================================*/
drop table if exists SHOPPING_CART;
create table SHOPPING_CART
(
SHOP_ID varchar(10) not null,
CUST_ID varchar(10) null,
CUST_EMAIL varchar(20) null,
constraint PK_SHOPPING_CART primary key clustered (SHOP_ID)
);
/*==============================================================*/
/* Table: STORED */
/*==============================================================*/
drop table if exists STORED_T;
create table STORED_T
(
WAR_ID varchar(10) not null,
BOOK_ID varchar(10) not null,
BOOK_ISBN varchar(20) not null,
constraint PK_STORED_T primary key clustered (WAR_ID, BOOK_ID, BOOK_ISBN)
);
/*==============================================================*/
/* Table: WAREHOUSE */
/*==============================================================*/
drop table if exists WAREHOUSE;
create table WAREHOUSE
(
WAR_ID varchar(10) not null,
WAR_NAME char(20) null,
constraint PK_WAREHOUSE primary key clustered (WAR_ID)
);
Inserting data in tables……..
SELECT * FROM bookstore.publisher;
Insert into Publisher (PUB_ID, BOOK_ID, BOOK_ISBN, PUB_NAME, PUB_ADDRESS, PUN_PHONE ,PUB_URL) values(01,'ABC1', 'ABCD1','Penguin Random House', 'Luchana 23 Madrid Spain',535819,'http://www.penguinrandomhouse.com/');
Insert into Publisher (PUB_ID, BOOK_ID, BOOK_ISBN, PUB_NAME, PUB_ADDRESS, PUN_PHONE ,PUB_URL) values(02, 'ABC2', 'ABCD2', 'Hachette Livre','50 Victoria Embankment',227000, 'https://www.hachette.com');
Insert into Publisher (PUB_ID, BOOK_ID, BOOK_ISBN, PUB_NAME, PUB_ADDRESS, PUN_PHONE ,PUB_URL) values(03,'ABC3', 'ABCD3', 'HarperCollins', 'The News Building London Bridge Street',2427737,'https://www.harpercollins.com/');
select * from author;
insert into Author values (01,'Cat Sebastian', '9296 Henry St. Auburndale FL 33823');
insert into Author values (02,'Lorraine Heath', '974 Broad Dr. Marcus Hook PA 19061');
insert into Author values (03,'Jill Shalvis','187 Cherry Rd. Reston VA 20191');
insert into Author values (04,'Kevin Kwan','13 Locust St. Round Lake IL 60073');
insert into Author values (05,'Elisabeth Noreback','26 Rock Creek Dr. Tuscaloosa AL 35405');
insert into Author values (06,'Pamela Brown', '409 Santa Clara Ave. Cedar Rapids IA 52402');
select * from book;
insert into book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ('B001', 384.00 ,'9706279318', 'A001' , 'A Gentleman Never Keeps Score' , 2018 );
insert into Book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ( 'B002', 94.50 ,'9728304828','A002' , 'Texas Glory ' , 2015 );
insert into Book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ( 'B003', 45.00 ,'9702833373','A003' , ' Texas Glory ' , 2017 );
insert into Book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ( 'B004', 234.50 ,'9703859383','A004' , 'Crazy Rich Asians' , 2018 );
insert into Book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ( 'B005', 23.60 ,'9793937483','A005' , 'Tell me you are mine' , 2015 );
insert into Book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ( 'B006', 200.60 ,'9729473047','A006' , 'The spy and the traitor' , 2010 );
insert into Book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ( 'B007', 145.00 ,'9703746264','A007' , 'Paradise Sky by Joe Lansdale' , 2016 );
insert into Book (BOOK_ID, BOOK_PRICE,BOOK_ISBN, AUTH_ID, BOOK_TITLE,BOOK_YEAR) values ( 'B008', 165.99 ,'9739482733','A008' , 'Meet Camaro from The Night Charter' , 2010 );
SELECT * FROM bookstore.customer;
insert into Customer values (115099561,'Karol Wilson', '75 Poplar Court
Eugene OR 97402',123456, 'emkw@mail.com');
insert into Customer values (45528305,'Richard Orson', '33 Richardson Dr. Chandler AZ 85224',89034, 'rior@mail.com');
insert into Customer values (2211600,'Loraine Williams', '8 Market St.
Portsmouth VA 23703',782927,'lowi@mail.com');
insert into Customer values (649373,'Scott Luka', '412 Pawnee Lane Kenosha, WI
53140',7682,'sclu@mail.com');
SELECT * FROM bookstore.warehouse;
insert into Warehouse values (01, 5393544, '530 Roosevelt Lane Hopewell Junction NY 12533');
insert into Warehouse values (02, 9759583,'9592 Applegate Road Bedford OH 44146');
insert into Warehouse values (03, 9958484,'21 Arch Ave. Grand Haven MI 49417');
SELECT * FROM bookstore.warehouse;
insert into Warehouse values ('WA01', 55521,' Roosevelt Lane Hopewell Junction NY 12533');
insert into Warehouse values ('WA02', 44393,'9592 Applegate Road Bedford OH 44146');
insert into Warehouse values ('WA03', 34938,'21 Arch Ave. Grand Haven MI 49417');
SELECT * FROM bookstore.shopping_cart;
insert into shopping_cart values ('S01',115099561,'emkw@mail.com');
insert into shopping_cart values ('S02',45528305,'rior@mail.com');
insert into shopping_cart values ('S03',2211600,'lowi@mail.com');
insert into shopping_cart values ('S04',649373,'sclu@mail.com');
SELECT * FROM WAREHOUSE_HAVE_BOOKS;
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA01','9728304828',15);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA01','9739482733',29);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA01','9729473047',151);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA02','9703859383',20);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA02','9793937483',383);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA02','9706279318',293);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA03','9702833373',393);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA03','9729473047',38);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA03','9706279318',48);
insert into warehouse_have_books (WH_CODE,Book_ISBN,count)
values('WA03','9739482733',29);
SELECT * FROM shoppingbaskets_have_books;
insert into shoppingbaskets_have_books values('9706279318','S01',1);
insert into shoppingbaskets_have_books values('9703746264','S01',1);
insert into shoppingbaskets_have_books values('9729473047','S01',1);
insert into shoppingbaskets_have_books values('9739482733','S02',1);
insert into shoppingbaskets_have_books values('9728304828','S02',1);
insert into shoppingbaskets_have_books values('9702833373','S02',2);
insert into shoppingbaskets_have_books values('9703859383','S02',1);
insert into shoppingbaskets_have_books values('9793937483','S03',1);
insert into shoppingbaskets_have_books values('9703859383','S03',1);
insert into shoppingbaskets_have_books values('9702833373','S03',1);
insert into shoppingbaskets_have_books values('9739482733','S04',1);
insert into shoppingbaskets_have_books values('9702833373','S04',1);
insert into shoppingbaskets_have_books values('9729473047','S04',1);
insert into shoppingbaskets_have_books values('9793937483','S04',1);

/*  QUERIES  */
1) Which book is being sell more right now?
select B.BOOK_ISBN, B.BOOK_TITLE,sum(UNK) as maxbooks from BOOK B,
shoppingbaskets_have_books SB
where SB.BOOK_ISBN=B.BOOK_ISBN
group by BOOK_ISBN, BOOK_TITLE
order by maxbooks desc
LIMIT 1

2) Which customer is buying more books?
select maxnumber, Customer
from (select sum(UNK) as maxnumber, CUST_NAME as Customer
from customer C, shopping_cart SB,shoppingbaskets_have_books SBB
where C.CUST_EMAIL=SB.CUST_EMAIL
and SB.SHOP_ID=SBB.SHOP_ID
group by CUST_NAME
order by maxnumber desc) mysums
LIMIT 1

3) Which warehouse has Texas Glory in stock?
select W_CODE, W_ADDRESS
from warehouse W, warehouse_have_books WB, book B
where WB.WH_CODE=W.W_CODE
and WB.BOOK_ISBN = B.BOOK_ISBN
and B.BOOK_TITLE = 'Texas Glory';

4) Which author has more books on sell?
select AUTH_NAME,count(BOOK_TITLE) as numberbooks
from author A, book B
where A.AUTH_ID=B.AUTH_ID
group by AUTH_NAME
order by numberbooks desc
LIMIT 1

5) Which publisher offers less books?
select P.PUB_NAME, count(BOOK_TITLE) as numberofbooks
from Publisher P, Book B
where P.PUB_ID=B.PUB_ID
group by P.PUB_ID
order by numberofbooks desc
LIMIT 1
