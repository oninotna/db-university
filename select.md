1. Selezionare tutti gli studenti nati nel 1990 (160)
```SQL
SELECT *
FROM `students`
WHERE year(`date_of_birth`) = 1990
```
2. Selezionare tutti i corsi che valgono più di 10 crediti (479)
```SQL
SELECT *
FROM `courses`
WHERE `cfu` > 10
```
3. Selezionare tutti gli studenti che hanno più di 30 anni
```SQL
SELECT * 
FROM `students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) >= 30
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)
```SQL
SELECT * 
FROM `courses`
where `period` = "I semestre" AND `year` = 1
```
5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)
```SQL
SELECT * 
FROM `exams`
where hour(`hour`) > 13 AND date(`date`) = "2020-06-20"
```
6. Selezionare tutti i corsi di laurea magistrale (38)
```SQL
SELECT * 
FROM `degrees`
where `level` = "magistrale"
```
7. Da quanti dipartimenti è composta l'università? (12)
```SQL
SELECT count(*) 
FROM `departments`
```
8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
```SQL
SELECT count(*) 
FROM `teachers`
WHERE `phone` is null
```