Group by:
1. Contare quanti iscritti ci sono stati ogni anno 
SELECT COUNT(id) AS number_students, YEAR(enrolment_date) AS 'year'  
FROM students
GROUP BY year



2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio 
SELECT COUNT(*) AS number_teachers , office_address 
FROM teachers
GROUP BY office_address



3. Calcolare la media dei voti di ogni appello d'esame 
SELECT AVG(vote) AS Average_vote, exam_id AS exam
FROM exam_student
group by exam


4. Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(*) AS number_degrees, departments.name AS department 
FROM degrees, departments
GROUP BY department