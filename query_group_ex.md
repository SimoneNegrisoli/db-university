### 1. Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(`enrolment_date`) AS `anno`, COUNT(`id`) AS `iscritti_per_anno` <br>
FROM `students` <br>
GROUP BY YEAR(`enrolment_date`) <br>
ORDER BY `anno`; <br>

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT `office_address`, COUNT(\*) AS `num_insegnanti` <br>
FROM `teachers` <br>
GROUP BY `office_address` <br>
HAVING `num_insegnanti` > 1; <br>

### 3. Calcolare la media dei voti di ogni appello d'esame

SELECT `exam_id` , AVG(`vote`) AS `media_voti` <br>
FROM `exam_student` <br>
GROUP BY `exam_id`; <br>

### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT COUNT(`id`) AS `numero_corsi`, `department_id` <br>
FROM `degrees` <br>
GROUP BY `department_id`; <br>
