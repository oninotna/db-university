1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```SQL
SELECT 
`students`.*,
`degrees`.`name` AS `degree_name`
FROM `students`
INNER JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`
WHERE `degrees`.`name` = "corso di laurea in economia"
```
2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze
```SQL
SELECT 
`degrees`.*
FROM `degrees`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = "dipartimento di neuroscienze"
```
3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```SQL
SELECT 
`courses`.*
FROM `courses`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
WHERE `teachers`.`name` = "fulvio" AND `teachers`.`surname` = "amato"
```
4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome
```SQL
SELECT 
`students`.*,
`degrees`.*,
`departments`.*
FROM `students`
INNER JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
ORDER BY `students`.`surname`, `students`.`name`
```
5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```SQL
SELECT 
`degrees`.*,
`courses`.*,
`teachers`.*
FROM `degrees`
INNER JOIN `courses`
ON `degrees`.`id`= `courses`.`degree_id`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
ORDER BY `degrees`.`name`, `courses`.`name` 
```
6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)
```SQL
SELECT 
`teachers`.*,
`departments`.`name`
FROM `teachers`
INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
INNER JOIN `courses`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `degrees`
ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = "dipartimento di matematica"
```
7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18.
```SQL
```

