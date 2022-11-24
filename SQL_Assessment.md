Q-1. Write an SQL query to fetch “FIRST_NAME” from Worker table using the alias name as <WORKER_NAME>.
Ans:select First_Name ='WORKER_NAME' from Worker; 
Q-2. Write an SQL query to fetch “FIRST_NAME” from Worker table in upper case.
Ans: select upper(FIRST_NAME) from Worker;
Q-3. Write an SQL query to fetch unique values of DEPARTMENT from Worker table.
Ans: select DISTINCT DEPARTMENT from Worker;
Q-4. Write an SQL query to print the first three characters of  FIRST_NAME from Worker table.
Ans: select SUBSTRING(FIRST_NAME,1,3) from Worker;
Q-5. Write an SQL query to find the position of the alphabet (‘a’) in the first name column ‘Amitabh’ from Worker table.
Ans: select POSITION("a" in FIRST_NAME) from Worker;
Q-6. Write an SQL query to print the FIRST_NAME from Worker table after removing white spaces from the right side.
Ans: select RTRIM(FIRST_NAME) from WORKER;
Q-7. Write an SQL query to print the DEPARTMENT from Worker table after removing white spaces from the left side.
Ans: select LTRIM(DEPARTMENT) from Worker;
Q-8. Write an SQL query that fetches the unique values of DEPARTMENT from Worker table and prints its length.
Ans:  select length(DEPARTMENT) from (Select DISTINCT DEPARTMENT from Worker)
Q-9. Write an SQL query to print the FIRST_NAME from Worker table after replacing ‘a’ with ‘A’.
Ans: select REPLACE(FIRST_NAME,'a','A') from Worker;
Q-10. Write an SQL query to print the FIRST_NAME and LAST_NAME from Worker table into a single column COMPLETE_NAME. A space char should separate them.
Ans: SELECT FIRST_NAME+SPACE(1)+LAST_NAME as COMPLETE_NAME from Worker;
Q-11. Write an SQL query to print all Worker details from the Worker table order by FIRST_NAME Ascending.
Ans: select * from Worker order by FIRST_NAME;
Q-12. Write an SQL query to print all Worker details from the Worker table order by FIRST_NAME Ascending and DEPARTMENT Descending.
Ans : Select * from Worker Order by FIRST_NAME and DEPARTMENT DESC;
Q-13. Write an SQL query to print details for Workers with the first name as “Vipul” and “Satish” from Worker table.
Ans: select * from Workers where FIRST_NAME in ("Vipul","Satish");
Q-14. Write an SQL query to print details of workers excluding first names, “Vipul” and “Satish” from Worker table.
Ans: select * from Worker where NOT FIRST_NAME in("Vipul","Satish");
Q-15. Write an SQL query to print details of Workers with DEPARTMENT name as “Admin”.
Ans:  select * from Worker where DEPARTMENT="ADMIN";
Q-16. Write an SQL query to print details of the Workers whose FIRST_NAME contains ‘a’.
Ans: select * from Worker where FIRST_NAME like "%a%";
Q-17. Write an SQL query to print details of the Workers whose FIRST_NAME ends with ‘a’.
Ans: select * from Worker where FIRST_NAME like "%a";
Q-18. Write an SQL query to print details of the Workers whose FIRST_NAME ends with ‘h’ and contains six alphabets.
Ans: select * from Worker where FIRST_NAME like "%h" and length(FIRST_NAME)=6;
Q-19. Write an SQL query to print details of the Workers whose SALARY lies between 100000 and 500000.
Ans: select * from Worker where SALARY BETWEEN 100000 and 500000;
Q-20. Write an SQL query to print details of the Workers who have joined in Feb’2014.
Ans: select * from Worker where monthname(JOINING_DATE)='FEB' and year(JOINING_DATE)=2014;
Q-21. Write an SQL query to fetch the count of employees working in the department ‘Admin’.
Ans: Select Count(*) from Worker where DEPARTMENT="Admin"
Q-22. Write an SQL query to fetch worker names with salaries >= 50000 and <= 100000.
Ans: Select FIRST_NAME +SPACE(1)+LAST_NAME as WORKER_NAME from Worker where SALARY between 50000 and 100000
Q-23. Write an SQL query to fetch the no. of workers for each department in the descending order.
Ans: select COUNT(*)  as WORKER_COUNT from Workers group by DEPARTMENT order by COUNT DESC;
Q-24. Write an SQL query to print details of the Workers who are also Managers.
Ans: select * from Worker inner join TITLE on Workers.WORKER_ID= TITLE.WORKER_REF_ID;
Q-25. Write an SQL query to fetch duplicate records having matching data in some fields of a table.
Ans : 
Q-26. Write an SQL query to show only odd rows from a table.
Ans: Select * from Worker where mod(WORKER_ID,2)=0;
Q-27. Write an SQL query to show only even rows from a table.
Ans: select * from Worker where not mod(WORKER_ID,2)=0;
Q-28. Write an SQL query to clone a new table from another table.
Ans: create table clone_table select * from Worker;
Q-29. Write an SQL query to fetch intersecting records of two tables.
Ans: select * from Worker INNER JOIN TITLE on Worker.WORKER_ID=Title.WORKER_REF_ID;
Q-30. Write an SQL query to show records from one table that another table does not have.
Ans: select * from worker left join Title on WORKER.WORKER_ID =TITLE.WORKER_REF_ID where TITLE.WORKER_REF_ID=null
