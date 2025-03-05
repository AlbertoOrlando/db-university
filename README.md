esercizio select mysql db-university
//
select * from students where year(date_of_birth) = 1990
//
select * 
from courses
where cfu > 10
//
select * 
from students
where year(date_of_birth) < 1995
//
select * 
from courses
where year = 1
and period = 'I semestre'
//
from exams
where date = '2020-06-20'
and hour > '14:00:00'
//
select * 
from degrees
where level = 'magistrale'
//
select count(id) 
from departments
//
select count(id)
from teachers
where phone is null


esercizio group by mysql
//
select count(id), year(enrolment_date)
from students
group by year(enrolment_date)
//
select count(id), office_address
from teachers
group by (office_address)
//
select exam_id, avg(vote) as media_voti
from exam_student
group by exam_id
//
select count(id) as corsidilaurea, department_id
from degrees
group by department_id