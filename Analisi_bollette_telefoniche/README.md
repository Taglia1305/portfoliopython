# Calcolo della Bolletta Telefonica 📞

Progetto Python per l'analisi dei dati di traffico telefonico, pulizia dei dati (data cleaning) e generazione di report su costi e congestione delle celle.

## 📋 Descrizione del Progetto

Il sistema elabora un file di log (`telefonate.csv`) contenente i dettagli delle chiamate effettuate in un mese. Il software si occupa di filtrare le chiamate non valide, calcolare l'importo dovuto da ogni cliente e identificare le celle di rete con un carico di traffico superiore alla media.

### Struttura del file di input
Il file CSV presenta le seguenti colonne:
- **Cod_Chiamante**: Identificativo univoco del cliente chiamante.
- **Cod_Destinatario**: Identificativo univoco del cliente ricevente.
- **Cod_Cella_Chiamante**: Area di origine della chiamata.
- **Cod_Cella_Destinatario**: Area di destinazione della chiamata.
- **Inizio (GGI:HHI:MMI)**: Giorno, ora e minuto di inizio.
- **Fine (GGF:HHF:MMF)**: Giorno, ora e minuto di fine.

---

## 🛠️ Funzionalità Implementate

### 1. `ottieniDatiTelefonate(nomeFile)`
Questa funzione si occupa della lettura e della **pulizia dei dati**. Scarta le righe che iniziano con `#` (malfunzionamenti) e valida ogni record secondo i seguenti criteri:
- **No auto-chiamate**: Chiamante e Destinatario devono essere diversi.
- **Range Temporali**: I valori di giorni (1-31), ore (0-23) e minuti (0-59) devono essere validi.
- **Ordine Cronologico**: L'orario di inizio non può essere successivo a quello di fine.
- **Durata Massima**: Le chiamate oltre le 10 ore sono considerate errori e scartate.

**Output**: Una lista di tuple nel formato `(Cod_Chiamante, Cod_Destinatario, Cod_Cella_Chiamante, Cod_Cella_Destinatario, Durata_Minuti)`.

### 2. `calcolaBollette(datiChiamate)`
Calcola l'importo mensile per ogni cliente che ha effettuato almeno una chiamata.
- **Tariffa**: 0.10€ / minuto.
- **Bonus**: Ogni cliente riceve **20 minuti gratuiti** al mese.
- **Calcolo**: L'importo viene calcolato solo sui minuti eccedenti il bonus.

**Output**: Un dizionario `{Cod_Cliente: Importo_Euro}`.

### 3. `calcolaCelleCongestionate(datiChiamate)`
Analizza il carico di traffico per ogni cella telefonica.
- Considera solo le chiamate in **partenza** da una cella.
- Calcola la media delle chiamate effettuate per cella.
- Identifica come "congestionate" le celle con un numero di chiamate **maggiore della media**.

**Output**: Una lista contenente i codici delle celle congestionate.

---

## 🚀 Esempio di Utilizzo

```python
# Importa le funzioni e avvia l'analisi
dati = ottieniDatiTelefonate("telefonate.csv")

# Calcola i costi per ogni cliente
bollette = calcolaBollette(dati)

# Identifica le zone critiche
celle_critiche = calcolaCelleCongestionate(dati)

print(f"Bollette: {bollette}")
print(f"Celle critiche: {celle_critiche}")
