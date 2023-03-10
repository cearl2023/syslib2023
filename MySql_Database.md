# Instructions for Accessing MySql Database

## Logging Into Database
```
mysql -u opacuser-p
```
- Enter password

```
show databases;
use opacdb;
show tables;
describe books;
```

## Show All Records in Table
```
select * from books;
```

## Commands for Database
```
select author from books;
select copyright from books;
select author, title from books;
select author from books where author like '%millet%';
select title from books where author like '%mbue%';
select author, title from books where title not like '%e';
select * from books;
alter table books add publisher varchar(75) after title;
describe books;
update books set publisher='Simon \& Schuster' where id='1';
update books set publisher='Penguin Random House' where id='2';
update books set publisher='W. W. Norton \& Company' where id='3';
update books set publisher='Knopf' where id='4';
select * from books;
delete from books where author='Julia Phillips';
insert into books
(author, title, publisher, copyright) values
('Emma Donoghue', 'Room', 'Little, Brown \& Company', '2010-08-06'),
('Zadie Smith', 'White Teeth', 'Hamish Hamilton', '2000-01-27');
select * from books;
select author, publisher from books where copyright < '2011-01-01';
select author from books order by copyright;
\q
```

### New Codes
```
update books set id='new number here' where id='old number here';
```
