### 1. Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(`enrolment_date`) AS `anno`, COUNT(`id`) AS `iscritti_per_anno` <br>
FROM `students` <br>
GROUP BY YEAR(`enrolment_date`) <br>
ORDER BY `anno`; <br>

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT `office_address`, COUNT(\*) AS `num_insegnanti`
FROM `teachers`
GROUP BY `office_address`
HAVING `num_insegnanti` > 1;

3. Calcolare la media dei voti di ogni appello d'esame
4. Contare quanti corsi di laurea ci sono per ogni dipartimento
