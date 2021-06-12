# HCI-project
Quick repo for my Human–computer interaction project

## Attenzione: 
###### i dati riportati sono puramente illustrativi, ogni progetto deve essere unico nel suo genere.

## Introduzione
I notebook python permettono, una volta raccolti tutti i dati, di creare tutti i grafici utili al report finale e tutte le statistiche necessarie in un solo click.

Nello specifico ```stats_ium.ipynb``` si occupa sia statistiche e grafici su efficacia ed efficienza degli user test sia sui grafici e prioritizzazione delle euristiche violate. 
```Stats quest utente.ipynb``` invece si occupa delle statistiche e dei grafici per il quesitonario somministrato ai 24 utenti.


## Requirements
- ```Python3```, testato utilizzando la versione 3.9.5
- ```Jupyter Notebook``` o sistema equivalente
- ```pandas``` per la gestione dei dataframe
- ```numpy``` per operazioni su vettori, matrici e altro
- ```matplotlib``` per i grafici
- ```seaborn``` per i grafici
- ```scipy``` per le statistiche

## Istruzioni

Sono necessari degli step iniziali per permettere il corretto funzionamento di entrambi i notebook. 

#### Modifiche sul codice
In entrambi, tra le primissime righe di codice, è necessario specificare il nome dei sistemi confrontati (attualmente riportati come Apple Music e Tidal).

#### Come riportare i dati

I dati raccolti devono essere riportati in un CSV. Nello specifico devono essere presenti diverse tabelle che vedremo nel dettaglio:

##### ```users-time.csv```:
In questo file CSV vanno riportati tutti i dati riguardo i task effettuati con gli utenti sui due sistemi. Nello specifico è necessario seguire lo standard riportato in tabella

|           | Task 1 s1 | Task 2 s1 | Task 3 s1 | Task 1 s2 | Task 2 s2 | Task 3 s2 | Sesso | Eta | Lavoro         | Istruzione |
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-------|-----|----------------|------------|
| Utente 1  | 0.00-C    | 0.00-A    | 0.00-F    | ...       | ...       | ...       | M     | 22  | Impiegato      | Diploma    |
| Utente 2  | 0.00-A    | ...       | ...       | ...       | ...       | 0.00-F    | F     | 52  | Data scientist | Laurea     |
| ...       | ...       | ...       | ...       | ...       | ...       | ...       | ...   | ... | ...            | ...        |
| Utente 12 | 0.00-F    | ...       | ...       | 0.00-F    | 0.00-A    | 0.00-C    | M     | 31  | Professore     | Phd        |

- Il nome di ogni colonna deve essere riscritto rispettando lo standard ```Task <numero task qui> <nome sistema qui>```
- Ogni tempo viene indicato con il formato ```1.23-X``` dove ```1``` sono i minuti, ```.23``` i secondi e ```X``` è un carattere tra ```C```, ```A``` e ```F``` che indicano rispettivamente un task completato correttamente, un task in cui l'utente è stato aiutato e un task non concluso.
- Nelle colonne ```Sesso```, ```Eta```, ```Lavoro``` e ```Istruzione```, come facilmente intuibile, vengono riportate le informazioni personali relative a ogni utente.

È comunque fornito nella stessa repo un file di esempio esplicativo e funzionante

##### ```Quest eu <nome sistema 1>.csv``` e ```Quest eu <nome sistema 2>.csv```:

In questo file csv sono riportate tutti i problemi riscontrati nei sistemi dagli esperti di usabilità e di dominio. Nello specifico la tebella è strutturata nel seguente modo:

|              | Problema               | Expert 1 | ... | Expert n | Euristiche | Id valutatori |
|--------------|------------------------|----------|-----|----------|------------|---------------|
| Cod. probl 1 | Descrizione problema 1 | [0-4]    | ... | [0-4]    | [E1-E10] + | Id1           |
| ...          | ...                    | ...      | ... | ...      | ...        | ...           |
| Cod. probl n | Descrizione problema n | [0-4]    | ... | [0-4]    | [E1-E10] + | Id1-Id2       |


Nel dettaglio:
- Gli indici della tabella (prima colonna) sono i codici identificativi dei problemi
- La seconda colonna ```Problema``` contiene una breve descrizione del problema riscontrato
- Dalla terza colonna sono elencati con ```Expert X``` tutti i valutatori (esperti di dominio e di usabilità) con i rispettivi voti dati da 0 a 4 per ogni problema riscontrato. Il valore ```X``` deve essere sostituito con il numero identificativo del valutatore
- La colonna ```Euristiche``` contiene l'elenco delle euristiche violate. Un esempio utilizzando le euristiche di Nielsen: se il problema viola l'euristica 7 scriverò ```E7```: se il problema viola l'euristica 2, 3 e 5 scriverò ```E2-E3-E5```
- L'ultima colonna ```Id valutatori``` contiene tutti gli id dei valutatori che hanno trovato il rispettivo problema. Esempio: il valutatore esperto di usabilità 2 e il valutatore esperto di dominio 1 ha trovato il problema quindi scriverò ```EU2-ED1```

Anche qui sono comunque forniti nella stessa repo dei files di esempio esplicativi e funzionanti

##### ```Questionario <nome sistema 1>.csv``` e ```Questionario <nome sistema 2>.csv```:

Questi file sono relativi ai questionari effettuati dai 24 utenti. Il questionario adottato è [UEQ](https://www.ueq-online.org).

La tabella ha la seguente struttura:

|                               | Utente 1          | ... | Utente 24  |
|-------------------------------|-------------------|-----|------------|
| genere                        | Maschio           | ... | Femmina    |
| eta                           | 25                | ... | 32         |
| situazione lavorativa         | Studente          | ... | Lavoratore |
| istruzione                    | Laurea Magistrale | ... | Diploma    |
| fastidioso-piacevole          | [1-7]             | ... | [1-7]      |
| incomprensibile-comprensibile | [1-7]             | ... | [1-7]      |
| ...                           | ...               | ... | ...        |
| conservativo-innovativo       | [1-7]             | ... | [1-7]      |
| NPS                           | [0-10]            | ... | [0-10]     |

Ogni colonna rappresenta la compilazione di un questionario
- nelle prime 4 righe vengono riportate le informazioni personali
- nelle successive righe viene riportato il punteggio che ogni utente ha dato come risposta alla domanda del questionario UEQ
- nell'ultima riga viene riportato la risposta alla domanda *Quanto consiglieresti ad un amico il sistema s da 0 a 10?*

## Contatti

In caso di problemi o domande (non attinenti all'insegnamento/esame): d.scalena [at] campus.unimib [dot] it


