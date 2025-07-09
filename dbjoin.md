Join:
1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia 
SELECT `degrees`.`name`, students.* 
FROM students
JOIN degrees ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'




2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze 
SELECT `degrees`.`name`,
`degrees`.`level`,
`degrees`.`address`,
`degrees`.`email`,
`degrees`.`website`,
`departments`.`name` AS departments_name
FROM degrees
JOIN departments ON `degrees`.`department_id` = `departments`.`id`
WHERE `degrees`.`name` 	= 'Corsi di Laurea Magistrale%' 
AND `departments`.`name` = 'Dipartimento di Neuroscienze'


3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT `teachers`.`name`, 
`teachers`.`surname`,
`courses`.*
FROM course_teacher
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
WHERE `teachers`.`id` = 44



4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome 
SELECT `students`.`name` AS student_name,
`students`.`surname` AS student_surname,
`students`.`fiscal_code`,
`students`.`registration_number`,
`degrees`.`name` AS degree,
`departments`.`name` AS department

FROM students
JOIN degrees ON `students`.`degree_id` = `degrees`.`id`
JOIN departments ON `degrees`.`department_id` = `departments`.`id`
ORDER BY student_surname



5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti 
SELECT `courses`.*, 
`teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`, 
`degrees`.`name` AS `degree_name`
FROM courses
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`
JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`


6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54) 
SELECT `teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teachers_surname`,
`departments`.`name` AS `department`
FROM `teachers`
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica'




7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.