# git tutorial
create database <name>;			// to create
create database mybd;

use <name>; 				//use it as main db
use mydb;

drop database <name>;  			//to delete
drop databse olddb;


alter database <name> read only =1; 		//makes it read only  ( there are read only / encryption)
alter databse olddb read only=1;

alter database <name> read only =0;		//makes it 

create table employee(			//creates the table 
	employee_id INT,
	first_name VARCHAR(50),
	last_name VARCHAR(50),
	hourly_pay DECIMAL(5,2),
	hire_date DATE
);
create table student(
	student_id INT,
	first_name VARCHAR(50),
	last_name VARCHAR(50),
	number DECIMAL;
	class_time DATE;
);


select * from employees; 			/to select table 
select * from student;

rename table employee to workers;		//renames the table 
rename table student to students;

drop table employee; 			//to drop table 
drop table students;


ALTER TABLE employees 			//to alter table 
ADD phone_number VARCHAR(15);	
ALTER TABLE students
ADD email VARCAHR(50);

ALTER TABLE employees			/use alter to rename phone_number to email;
rename column phone_number to email;
ALTER TABLE students
rename column number to phone_number;

alter table employees				// use alter to modify type in this case from varchar(15) to varchar(100)
modify column email varchar(100);
ALTER TABLE students
modify column email varchar(100);


alter table employees 			//use alter to modify position in column
modify email varchar(101) 
after last_name ;

alter table students
modify email varchar(100)
after last_name;

alter table employees 			//use alter to modify position in column to first 
modify email varchar(101) 
first ;

alter table employees 			// use alter to drop column from table 
drop column `S.N`;

//to insert data in table 

insert into employees					//use insert to enter values in table (employees)
values (2,'Squidward','Tentacles',15.00,'2023-01-03');

insert into employees
values 	(2,'Squidward','Tentacles',15.00,'2023-01-03'),	// use insert to enter multiple values at once; {note in format-:values ( ), ( ), ( );}
	(3,"Spongebog","Squarepants",12.50,"2023-01-04"),
	(4,'Patrik','Star',12.50,'2023-01-05'),
	(5,'Sandy','Cheeks',17.25,'2023-01-06');

insert into employees (employee_id,first_name,last_name)	//use insert to enter only specific columns 
values (6, "Sheldon", "plankton");

//select ways 

select last_name,first_name			//only select the specific searches 
from employees;

select * from employees			// only select where the conditions meets
WHERE  hourly_pay >= 15;
	
select * 					//only select the condition (!=) is the conditional 
from employees 
where employee_id !=1;

select * 					//using select for boolean false
from employees	
where hire_date is not null;


select * 					//using select for boolean true
from employees
where hire_date is  null;



update employees				// update table
set first_name = "Spongebob"
where employee_id=3;

delete from employees;			//deletes all the table

delete from employees			//delete table 
where employee_id=6;
select * from employees;
