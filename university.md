Modellizzare la struttura di una tabella per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi **Dipartimenti** (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni **Dipartimento** offre più **Corsi di Laurea** (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni **Corso di Laurea** prevede diversi **Corsi** (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni **Corso** può essere tenuto da diversi **Insegnanti**;
- ogni **Corso** prevede più appelli d'**Esame**;
- ogni **Studente** è iscritto ad un solo **Corso di Laurea**;
- ogni **Studente** può iscriversi a più appelli di **Esame**;
- per ogni appello d'**Esame** a cui lo **Studente** ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.

departments
degree courses
courses 
teachers
students
exams

## departments

- departments_id | BIGINT | NOT_NULL | UNIQUE | AI
- name
- rector

## degree_courses

- deg_course_id | BIGINT
- name
- students_number
- teachers_number
- classes
- number_exams

## courses 

- course_id | BIGINT
- name
- credit
- teacher
- class
- lessons_number
- students_number

## teachers

- teachers_id | BIGINT
- name
- surname
- email
- age
- courses_name
- courses_id

## students

- deg_course_id
- students_id | BIGINT
- name
- surname
- freshman_number 
- cfu_numbers

## exams

- exams_id
- teacher_id
- student_id
- courses_id
- date
- vote
- number_of_appeals

## Relationship:

oneToMany => departments & degree_courses
oneToMany => degree_courses & courses
manyToMany => courses & teachers (+ pivot tabella )
oneToMany => degree_course & student
oneToMany => students & exams 




