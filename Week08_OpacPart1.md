# Journal for Week 8 - Create a Bare Bones OPAC Part 1

## This week is broken down into:
1. Create HTML page 'opacbb.html'
2. Create Search PHP page 'search.php'
3. Add two dates fields to Opacbb.html in script
4. Add entires to database opacdb in MySql

- Create HTML Page
  - nano opacbb.html
  - insert HTML code in nano and save

- Create Search page
  - nano search.php
  - insert HTML code into search.php and save

- Note: Make sure to double check using my external IP address and not professors. 

## Connect to MySql Server
- Insert command
  - mysql -u opacuser -p

- Run Insert command to enter new records 
  - insert into books 
  - (author, title, publisher, copyright) values
  - ('Emma Donoghue', 'Room', 'Little, Brown \& Company', '2010-08-06'),
('Zadie Smith', 'White Teeth', 'Hamish Hamilton', '2000-01-27');
 
