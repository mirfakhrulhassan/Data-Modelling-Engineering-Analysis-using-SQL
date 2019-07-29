% Data Engineering using SQL

# Creating Tables

**departments**

|        departments         |
|:--------------------------:|
|dept_no varchar primary key,|
|	dept_name varchar    |


**employees**

|        employees          |
|:-------------------------:|
|   emp_no int primary key, |
|	birth_date date,    |
|	first_name varchar, |
|	last_name varchar,  |
|	gender varchar,     |
|	hire_date date      |


**titles**

|         titles            | 
|:-------------------------:|
|	emp_no int,         |	
|	title varchar,      |
|	from_date date,     |
|	to_date date,       |
|foreign key (emp_no) references employees(emp_no) |


**dept_emp**

|           dept_emp        |
|:-------------------------:|
|	emp_no int,         |
|	dept_no varchar,    |
|	from_date date,     |
|	to_date date,       |
|	foreign key (emp_no) references employees(emp_no),|
|	foreign key (dept_no) references departments(dept_no),|
|	primary key(emp_no,dept_no)|


**dept_manager**

|       dept_manager        |
|:-------------------------:|
|	dept_no varchar,    |
|	emp_no int,         |
|	from_date date,     |
|	to_date date,       |
|foreign key (emp_no) references employees(emp_no),|
|foreign key (dept_no) references departments(dept_no),|
|primary key(dept_no,emp_no)|


**salaries**

|    salaries               |
|:-------------------------:|
|	emp_no int,         |
|	salary int,         |
|	from_date date,     |
|	to_date date,       |
|foreign key (emp_no) references employees(emp_no)|


# Adding  primary keys to tables 'titles' and 'salaries'

alter table titles
add column id serial primary key;


alter table salaries
add column id serial primary key;
