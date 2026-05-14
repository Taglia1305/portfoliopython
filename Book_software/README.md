# Book Software - Gestione Biblioteca Digitale
Questo progetto Python è stato sviluppato per simulare un sistema di gestione
per una biblioteca digitale. Il software permette di organizzare un catalogo di
libri, gestire i prestiti e monitorare le disponibilità attraverso l'uso di
strutture dati dinamiche.
---
## Obiettivi del Progetto
Il software risolve le problematiche comuni della gestione di un archivio
librario, focalizzandosi su:
* **Catalogazione**: Organizzazione dei libri per titolo, autore e codice
identificativo.
* **Gestione Stato**: Monitoraggio in tempo reale dei libri disponibili e di
quelli in prestito.
* **Interattività**: Sistema di ricerca e aggiornamento dei dati tramite
funzioni dedicate.
## Funzionalità Principali
Il sistema si basa su una logica procedurale strutturata:
1. **Inserimento e Aggiornamento**: Funzioni per aggiungere nuovi titoli al
catalogo e aggiornare le informazioni esistenti.
2. **Sistema di Ricerca**: Algoritmi per filtrare i libri in base a criteri
specifici (autore, genere o disponibilità).
3. **Gestione Prestiti**: Logica per cambiare lo stato di un libro da
"disponibile" a "prestato", evitando conflitti nei dati.
4. **Reportistica**: Visualizzazione chiara dell'intero inventario della
biblioteca.
## Struttura dei Dati
Il progetto utilizza principalmente **Dizionari** e **Liste di Dizionari** per
rappresentare ogni libro come un oggetto complesso:
```python
libro = {
"titolo": "Esempio Libro",
"autore": "Autore Esempio",
"stato": "disponibile"
}
```
## Come Utilizzare il Progetto
1. Aprire il file principale (es. `main.py` o il notebook dedicato).
2. Inizializzare il database della biblioteca.

3. Utilizzare le funzioni di interfaccia per gestire i volumi:
```python
# Esempio: aggiunta di un libro
aggiungi_libro("Il Nome della Rosa", "Umberto Eco")
mostra_catalogo()
```
---
**Autore:** Taglia1305
**Tecnologie:** Python 3, Gestione Dizionari, GitHub
