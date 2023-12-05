# db-university Group

- Contare quanti iscritti ci sono stati ogni anno;
```MYSQL
SELECT YEAR(`enrolment_date`) as `anno`, COUNT(id) as `iscritti`
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio;

- Calcolare la media dei voti di ogni appello d'esame;

- Contare quanti corsi di laurea ci sono per ogni dipartimento;