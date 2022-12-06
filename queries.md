## Esercizio del 05/12/2022
- Selezionare tutti gli studenti nati nel 1990 (160)

```sql
SELECT * FROM `students` WHERE YEAR (`date_of_birth`)=1990;
```

- Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT * FROM `courses` WHERE `cfu` > 10;
```

- Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT * FROM `students` WHERE YEAR(`date_of_birth`)<=1992;
```

- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

```sql
SELECT * FROM `courses` WHERE `year` = 1 AND `period` = 'I semestre';
```

- Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

```sql
SELECT * FROM `exams` WHERE `date` = '2020/06/20' AND `hour` > '14%';
```

- Selezionare tutti i corsi di laurea magistrale (38)

```sql
SELECT * FROM `degrees` WHERE `level` = 'magistrale';
```

- Da quanti dipartimenti è composta l'università? (12)

```sql
SELECT COUNT(`id`) AS TotalDepartments FROM `departments`;
```

- Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```sql
SELECT * FROM `teachers` WHERE `phone` IS NULL;
```

## Esercizio del 06/12/2022

## Group By:

- Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT year(`enrolment_date`) AS 'Year of Enrollment',COUNT(`id`) AS 'Number of Enrollments' FROM `students` GROUP BY year(`enrolment_date`);
```

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT `office_address`, COUNT(id) AS 'Teachers Number' FROM `teachers` GROUP BY `office_address`;
```

- Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT `exam_id` AS 'Exam Appeal', AVG(`vote`) AS 'Average Appeal' FROM `exam_student` GROUP BY `exam_id`;
```

- Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT `department_id` AS 'Departments Number', COUNT(`id`) AS 'Degrees Number' FROM `degrees` GROUP BY `department_id`;
```