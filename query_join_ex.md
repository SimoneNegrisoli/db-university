### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT `students`.`name` AS `nome_studente`, `students`.`surname` AS `cognome_studente`, `degrees`.`name` AS `corso`
FROM `students`
JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT `departments`.`name` AS `dipartimento`, `degrees`.`name` AS `corso_di_laurea`, `degrees`.`level` AS `classe_di_studi`
FROM `degrees`
JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `degrees`.`level` = 'magistrale' AND `departments`.`name` = 'Dipartimento di Neuroscienze'

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT `teachers`.`name` AS`nome`, `teachers`.`surname` AS `cognome`, `courses`.`name` AS `nome_del_corso`
FROM `teachers`
JOIN `course_teacher`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses`
ON `course_teacher`.`course_id` = `courses`.`id`
WHERE `teachers`.id = 44

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT `students`.`surname` AS `cognome`, `students`.`name` AS`nome`, `departments`.`name` AS `facolta`, `degrees`.`name` AS`corso_di_laurea`
FROM `students`
JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`
JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
ORDER BY `students`.`surname`

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT `teachers`.`surname` AS `cognome_insegnante`, `teachers`.`name` AS `nome_insegnante`, `degrees`.`name` AS `nome_corso_di_laurea`, `courses`.`name` AS `materie`
FROM `degrees`
JOIN `courses`
ON `courses`.`degree_id` = `degrees`.`id`
JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
ORDER BY `nome_corso_di_laurea`

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
