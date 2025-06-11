1. Contare quanti iscritti ci sono stati ogni anno
```SQL
SELECT year(`enrolment_date`), count(*) AS `numero_iscritti`
FROM `students`
GROUP BY year(`enrolment_date`)
ORDER BY year(`enrolment_date`)
```
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```SQL
SELECT `office_address`, count(*) AS `insegnanti_nello_stesso_edificio`
FROM `teachers`
GROUP BY `office_address`
```
3. Calcolare la media dei voti di ogni appello d'esame
```SQL
SELECT `exam_id`, avg(`vote`) AS `media_esame`
FROM `exam_student`
GROUP BY `exam_id`
```
4. Contare quanti corsi di laurea ci sono per ogni dipartimento
```SQL
SELECT `department_id`, count(*) AS `corsi_per_dipartimento`
FROM `degrees`
GROUP BY `department_id`
```