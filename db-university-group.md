# db-university Group

- Contare quanti iscritti ci sono stati ogni anno;
```MYSQL
SELECT YEAR(`enrolment_date`) as `anno`, COUNT(id) as `iscritti`
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio;
```MYSQL
SELECT COUNT(`office_address`)as numero, `office_address` as indirizzo
FROM `teachers`
GROUP BY `office_address`;
```

- Calcolare la media dei voti di ogni appello d'esame;
```MYSQL
SELECT `exam_id`, AVG(`vote`) 
FROM `exam_student`
GROUP BY `exam_id`;
```

- Contare quanti corsi di laurea ci sono per ogni dipartimento;
```MYSQL
SELECT `department_id`, COUNT(*) as 'numero_corsi' 
FROM `degrees`
GROUP BY `department_id`;
```