# db-university Join

- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia;
```MYSQL
SELECT `students`.`name`, `students`.`surname`, `degrees`.`name`
FROM `degrees`
INNER JOIN `students`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'corso di laurea in economia';
```

- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze;
```MYSQL
SELECT * 
FROM `degrees`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = 'dipartimento di neuroscienze'
AND `degrees`.`level` = 'magistrale';
```

- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44);
```MYSQL
SELECT `courses`.*, `teachers`.`name`, `teachers`.`surname`
FROM `courses`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `teachers`.`name` = 'Fulvio'
AND `teachers`.`surname` = 'Amato';
```

- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e al relativo dipartimento, in ordine alfabetico per cognome e nome;
```MYSQL
SELECT `students`.`surname`, `students`.`name`, `degrees`.*, `departments`.*
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname`;
```

- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti;
```MYSQL
SELECT `degrees`.`name` as 'Degree Name', `courses`.`name` as 'Course Name', CONCAT(`teachers`.`name`, ' ', `teachers`.`surname`)
FROM `degrees`
INNER JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`;
```

- Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54);
```MYSQL
SELECT concat(`teachers`.`name`, ' ', `teachers`.`surname`) as "Teacher Name", `departments`.`name` 
FROM `teachers`
INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
INNER JOIN `courses`
ON `course_teacher`.`course_id` = `courses`.`id`
INNER JOIN `degrees`
ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = 'dipartimento di matematica'
ORDER BY `teachers`.`surname`;
```

- BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18;