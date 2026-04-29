
## Domande
- Qual è la differenza tra una query scritta direttamente nel codice e una query parametrizzata?
```text
La differenza risiede nel modo in cui vengono gestiti i valori. Nelle query scritte direttamente, i dati sono concatenati come testo all'interno dell'istruzione SQL. Nelle query parametrizzate, invece, il comando SQL rimane separato dai dati, che vengono trasmessi al database come variabili distinte. 
```

- Qual è il vantaggio di avere funzioni di supporto come esegui_select() ed esegui_dml()?
```text
Centralizzano la logica: esegui_dml() permette di gestire con un'unica funzione diverse operazioni di modifica (come insert e delete), mentre esegui_select() rende il codice più pulito, leggibile e riutilizzabile.
```

- In che senso i tre file non sono alternative equivalenti, ma evoluzioni progressive dello stesso codice?
```text
I tre file non sono alternative equivalenti perchè sono tre esempi di levelli diversi e non semplici varianti: si parte da un codice base con dati fissi (hardcoded), si evolve verso l'uso di variabili tramite query parametriche, per arrivare infine a una struttura logica superiore, ordinata e ottimizzata.
```


## Esercizi
Esercizi a partire dal **terzo file Python**.

### 1. Selezionare tutti i modelli di prodotto
Scrivere una funzione:

```python
seleziona_tutti_modelli(connection)
```

La funzione deve restituire tutte le righe della tabella `modelli_prodotto`

---
### 2. Visualizzare gli acquisti di un utente a partire dalla sua email

Scrivere una funzione:

```python

seleziona_acquisti_cliente(connection, email)
```

La query deve restituire almeno i seguenti campi:

* nome
* cognome
* email
* id_ordine
* data_ordine
* cod_seriale
* nome del modello
* categoria
* prezzo_vendita_effettivo
---

### 3. Contare quanti prodotti di un modello sono presenti a magazzino
Scrivere una funzione:

```python
conta_prodotti_modello(connection, cod_modello)
```

La funzione deve restituire il numero di prodotti presenti a magazzino associati a un determinato modello, identificato tramite il campo cod_modello.

---

### 4. Inserire un nuovo modello di prodotto
Scrivere una funzione:

```python
inserisci_modello(connection, cod_modello, nome, descrizione, categoria, prezzo_listino)
```
La funzione deve permettere di inserire un nuovo modello di prodotto

---

### 5. Aggiornare il prezzo di listino di un modello
Scrivere una funzione:

```python
aggiorna_prezzo_modello(connection, cod_modello, nuovo_prezzo)
```
La funzione deve permettere di modificare il prezzo di listino di un modello di prodotto, a partire dal suo codice

## Indicazioni operative

Per scegliere la funzione di supporto corretta:
- usare `esegui_select(...)` per le query `SELECT`;
- usare `esegui_dml(...)` per le query `INSERT`, `UPDATE` e `DELETE`.

Testare la funzione all'interno del main() e stampare a video il risultato
