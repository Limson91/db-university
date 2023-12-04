# db-university

- Selezionare tutti gli studenti nati nel 1990;
    SELECT *
    FROM `students`
    WHERE YEAR(`date_of_birth`) = 1990; 


- Selezionare tutti i corsi che valgono più di 10 crediti;
    SELECT *
    FROM `courses`
    WHERE `cfu` > 10; 

- Selezionare tutti gli studenti che hanno più di 30 anni;
    SELECT *
    FROM `students`
    WHERE `date_of_birth` < DATE_SUB(CURRENT_DATE(), INTERVAL 30 year)
    ORDER BY `date_of_birth` DESC;


- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea;


- Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20.06.2020;


- Selezionare tutti i corsi di laurea magistrale;


- Da quanti dipartimenti è composta l'università?


- Quanti sono gli insegnanti che non hanno un numero di telefono?
