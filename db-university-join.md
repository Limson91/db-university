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

- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44);

- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e al relativo dipartimento, in ordine alfabetico per cognome e nome;

- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti;

- Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54);

- BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18;