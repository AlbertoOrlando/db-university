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

//
esercizio join mysql
//
select students.*, degrees.name
from students
join degrees
on degrees.id = students.degree_id
where degrees.name = "Corso di Laurea in Economia"
//
select degrees.*, departments.name
from degrees
join departments
on departments.id = degrees.department_id
where departments.name = "Dipartimento di Neuroscienze"
and degrees.level = "magistrale"
//
select courses.*, teachers.name, teachers.surname
from courses
join course_teacher
on courses.id = course_teacher.course_id
join teachers
on teachers.id = course_teacher.teacher_id
where teachers.id = 44
//
select students.name, students.surname, degrees.name, departments.name
from students
join degrees
on degrees.id = students.degree_id
join departments
on departments.id = degrees.department_id
order by students.name asc, students.surname asc
//
select degrees.name, courses.name, teachers.name, teachers.surname
from degrees
join courses
on degrees.id = courses.degree_id
join course_teacher
on courses.id = course_teacher.course_id
join teachers
on teachers.id = course_teacher.teacher_id
order by degrees.name asc
//
select departments.name, courses.name, teachers.name, teachers.surname
from departments
join degrees
on departments.id = degrees.department_id
join courses
on degrees.id = courses.degree_id
join course_teacher
on courses.id = course_teacher.course_id
join teachers
on teachers.id = course_teacher.teacher_id
where departments.name = "Dipartimento di Matematica"
order by teachers.name asc, teachers.surname asc