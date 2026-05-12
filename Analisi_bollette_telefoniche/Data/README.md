# Cartella Dati

Questa cartella contiene i file necessari per l'esecuzione e il test del software di calcolo delle bollette telefoniche.

## File: `telefonate.csv`

Il file `telefonate.csv` raccoglie i log grezzi delle chiamate effettuate nel mese solare. È un file di testo in formato CSV (Comma-Separated Values) che utilizza il punto e virgola (`;`) come separatore.

### Struttura dei Record
Ogni riga (ad eccezione dell'intestazione) rappresenta una singola chiamata con i seguenti campi:

| Campo | Tipo | Descrizione |
| :--- | :--- | :--- |
| **Cod_Chiamante** | `int` | ID univoco del cliente che avvia la chiamata. |
| **Cod_Destinatario** | `int` | ID univoco del cliente che riceve la chiamata. |
| **Cod_Cella_Chiamante** | `int` | Identificativo della cella radio di origine. |
| **Cod_Cella_Destinatario** | `int` | Identificativo della cella radio di destinazione. |
| **Inizio** | `string` | Formato `GGI:HHI:MMI` (Giorno:Ora:Minuto). |
| **Fine** | `string` | Formato `GGF:HHF:MMF` (Giorno:Ora:Minuto). |

### Regole di Formattazione e Vincoli
Per essere considerato valido dal software, il dataset deve rispettare i seguenti criteri:
1. **Commenti**: Le righe che iniziano con il carattere `#` vengono interpretate come log di sistema/errori delle celle e ignorate.
2. **Integrità Temporale**: 
   - I giorni devono essere compresi tra `1` e `31`.
   - Le ore tra `0` e `23`.
   - I minuti tra `0` e `59`.
3. **Logica di Chiamata**: Record con `Cod_Chiamante` uguale a `Cod_Destinatario` sono considerati anomalie.

## ⚠️ Note sulla Pulizia Dati
I dati contenuti in questa cartella potrebbero presentare intenzionalmente degli errori (es. chiamate che finiscono prima di iniziare o durate superiori alle 10 ore) per testare la robustezza degli algoritmi di filtraggio implementati nella funzione `ottieniDatiTelefonate`.
