# Digital Serie A - Analisi Stagione 2008-09
Benvenuti nel repository dedicato all'analisi statistica del campionato di
calcio italiano di Serie A per la stagione 2008-2009. Questo progetto utilizza
Python per trasformare dati grezzi in informazioni utili e classifiche
dinamiche.
---
## Obiettivi del Progetto
L'applicazione è stata sviluppata per automatizzare il calcolo delle prestazioni
delle squadre, risolvendo problemi complessi di gestione dati attraverso:
* **Parsing dei Dati**: Elaborazione di una lista di tuple contenente i
risultati storici.
* **Logica di Punteggio**: Calcolo automatico dei punti (Vittoria: 3, Pareggio:
1, Sconfitta: 0).
* **Statistiche Avanzate**: Estrazione del numero di vittorie, pareggi e
sconfitte per ogni club.
## Funzionalità Tecniche
Il cuore del software risiede in tre funzioni principali sviluppate in Python:
1. **`calcola_punti(squadra)`**: Analizza ogni partita della lista `li`,
identifica se la squadra ha giocato in casa o trasferta e accumula il punteggio
totale.
2. **`stat_squadra(squadra)`**: Restituisce una tupla dettagliata con il
conteggio di Vittorie, Pareggi e Sconfitte (V, P, S).
3. **`classifica_finale()`**: Scansiona l'intero dataset, identifica tutte le
squadre univoche e genera un dizionario completo dei punti stagionali.
## Struttura del Dataset
I dati sono organizzati in una lista chiamata `li`. Ogni elemento è una tupla
così composta:
`("DATA", "CASA", "TRASFERTA", GOL_CASA, GOL_TRASFERTA)`
*Esempio: ("31/8/08", "Udinese", "Palermo", 3, 1)*
## Come Utilizzare il Progetto
1. Aprire il file `.ipynb` (Jupyter Notebook).
2. Eseguire la cella di inizializzazione dei dati.
3. Utilizzare le funzioni integrate per interrogare il database:
```python
v, p, s = stat_squadra("Inter")
print(f"Risultati Inter: {v}V, {p}P, {s}S")

---
**Autore:** Taglia1305
**Tecnologie:** Python 3, Markdown, Jupyter Notebook
