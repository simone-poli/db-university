Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi `Dipartimenti` (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più `Corsi di Laurea` (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi `Corsi` (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi `Insegnanti`;
- ogni Corso prevede più `appelli d'Esame`;
- ogni `Studente` è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente










# university

## entità
- dipartimenti
- corsi_laurea
- corsi
- insegnanti
- studenti
- esami



### dipartimenti
- id
- materia
- luogo


### corsi_laurea
- id
- materia
- dipartimenti_id
- studenti_matricola


### corsi
- id
- materia
- data
- aula
- corsiLaurea_id
- insegnanti_id


### insegnanti
- id
- nome
- cognome
- materia


### studenti
- id
- nome
- cognome
- matricola


### esami
- id
- esito(voto)
- corso_id


