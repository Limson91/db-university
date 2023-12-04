# db-university

- Selezionare tutti gli studenti nati nel 1990; <br>
SELECT * <br>
FROM `students` <br>
WHERE YEAR(`date_of_birth`) = 1990; <br>


- Selezionare tutti i corsi che valgono più di 10 crediti; <br>
SELECT * <br>
FROM `courses` <br>
WHERE `cfu` > 10; <br>

- Selezionare tutti gli studenti che hanno più di 30 anni; <br>
SELECT * <br>
FROM `students` <br>
WHERE `date_of_birth` < DATE_SUB(CURRENT_DATE(), INTERVAL 30 year) <br>
ORDER BY `date_of_birth` DESC; <br>


- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea; <br>
SELECT * <br>
FROM `courses` <br>
WHERE `period` = 'I semestre' <br>
AND `year` = '1'; <br>


- Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20.06.2020;


- Selezionare tutti i corsi di laurea magistrale;


- Da quanti dipartimenti è composta l'università?


- Quanti sono gli insegnanti che non hanno un numero di telefono?
