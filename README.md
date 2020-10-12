# Pewlett_Hackard_Analysis


## Overview of Pewlett_Hackard_Analysis

 Bobby's manager has a new request: determine the number of retiring employees per title,
 and identify employees who are eligible to participate in a mentorship program. 
 Then, write a report that summarizes your analysis and helps 
 prepare Bobby’s manager for the “silver tsunami” as many current employees 
 reach retirement age.


## Resources
- Data Source: 
departments.csv
dept_emp.csv
dept_manager.csv
employees.csv
titles.csv
- Software: pgAdmin , VS code

## Pewlett_Hackard_Analysis Results:

-By using the ERD created in this module as a reference and the knowledge of 
SQL queries, a Retirement Titles table is created that holds all the titles of 
current employees who were born between January 1, 1952 and December 31, 1955. 
Because some employees may have multiple titles in the database—for example, due to 
promotions—it was  necessary to use the DISTINCT ON statement to create a table that 
contains the most recent title of each employee. Then, by using the COUNT() function 
the final table is created that has the number of retirement-age employees by most 
recent job title.



- By using the ERD created in this module as a reference and the knowledge of SQL
 queries, a mentorship-eligibility table is created that holds the current employees 
 who were born between January 1, 1965 and December 31, 1965.


  
## Pewlett_Hackard_Analysis Summary

- How many roles will need to be filled as the "silver tsunami" begins to make an impact?
90398 roles are going to be retired and these roles need to be filled as the "silver tsunmi".

- Are there enough qualified, retirement-ready employees in the departments to mentor the next 
generation of Pewlett Hackard employees?
As far as I concerned, use the query below shows that  in compare to the number of who is going 
to be retierd ,in some titles the number of mentors is not enough especially for 
Senior Staff , Senior Engineer and Technique Leader titles.


SELECT COUNT(me.title),me.title
--INTO tablename
FROM  mentorship_eligibilty AS me
GROUP BY me.title
ORDER by COUNT(me.title)DESC; 

![number of mentores:](Resources/number_of_mentores.png)
