### 1. Selezionare tutti gli studenti nati nel 1990 (160)

SELECT \* <br>
FROM `students` <br>
WHERE YEAR(`date_of_birth`) = '1990'; <br>

### 2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT \* <br>
FROM `courses` <br>
WHERE `cfu`> '10'; <br>

### 3. Selezionare tutti gli studenti che hanno più di 30 anni

SELECT \*
FROM `students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURRENT_DATE) > 30;

### 4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

SELECT \* <br>
FROM `courses` <br>
WHERE `year`= 1 AND `period` = 'I semestre'; <br>

### 5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

SELECT \* <br>
FROM `exams` <br>
WHERE `date` = '2020/06/20' AND `hour`> '14:00'; <br>

### 6. Selezionare tutti i corsi di laurea magistrale (38)

SELECT \* <br>
FROM `degrees` <br>
WHERE `level`= 'magistrale'; <br>

### 7. Da quanti dipartimenti è composta l'università? (12)

SELECT COUNT(`id`) <br>
AS `numero_dipartimenti` FROM `departments`; <br>

### 8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT COUNT(`phone`) <br>
AS `insegnanti_con_numero_di_telefono` FROM `teachers` ;
