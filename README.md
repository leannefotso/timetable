# timetable
/* script sql creation d'un objet vue*/
CREATE VIEW emploisdetemps AS 
SELECT DISTINCT C.codeCours, T.jourCoursDate  FROM Cours C
JOIN Typehoraire T
ON C.codeCours= T.crsCodeCours
JOIN Jourcours J
ON J.dateJourCours=T.jourCoursDate
JOIN Coursdeclasse cls
ON  T.crsCodeCours=cls.crsCodeCours
JOIN Classe Cl
ON cl.specialiteNomSpec=cls.classSpecialiteNomspec
WHERE T.jourCoursDate 
IN ('lundi','mardi','mercredi','jeudi','vendredi','samedi')

/*script interactif enregistrer le mot de passe*/
alter table etudiant add password varchar(50);
update etudiant set password = ora_hash(matricule) where matricule = valeur;

alter table enseignants add password varchar(50);
update enseignants set password = ora_hash(matricule) where matricule = valeur;

/*script produire un etat HTML de l'emploi de temp*/
