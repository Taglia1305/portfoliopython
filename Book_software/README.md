# Book Software - Gestione Biblioteca Digitale Interattiva
Questo progetto Python simula un sistema di gestione per una biblioteca digitale
basato interamente sull'interazione in tempo reale. A differenza dei sistemi
statici, questo software non richiede dataset esterni in ingresso, ma viene
popolato dinamicamente dall'utente durante l'esecuzione.
---
## Obiettivi e Filosofia del Progetto
Il software è progettato come un **applicativo in-memory**, dove l'intera
struttura dei dati viene costruita e gestita durante la sessione di lavoro:
* **Popolamento Dinamico**: Il sistema parte da uno stato vuoto, lasciando
all'utente il compito di inserire i volumi e creare il catalogo.
* **Ciclo Operativo Continuo**: Utilizza un menu interattivo gestito da un ciclo
infinito (`while True`) che permette operazioni multiple senza interruzioni.
* **Gestione Stato**: Monitoraggio immediato delle disponibilità e dei prestiti.
## Architettura del Software
Il cuore del sistema è un menu di comando che permette di accedere alle seguenti
funzioni:
1. **Inserimento Manuale**: L'utente inserisce titolo e autore per
registrare un nuovo libro nel database temporaneo.
2. **Ricerca e Filtro**: Algoritmi che scansionano la memoria locale per
trovare titoli o autori specifici.
3. **Gestione Prestiti**: Modifica dello stato dei libri (Disponibile/In
Prestito) con validazione immediata.
4. **Report di Sessione**: Visualizzazione completa del catalogo creato
dall'utente durante il runtime.
## Note Tecniche
* **Data Storage**: Il catalogo è salvato in una lista di dizionari all'interno
della memoria RAM (Runtime-only).
* **Interfaccia**: Terminale interattivo con controllo degli input dell'utente.
* **Control Flow**: Struttura a cicli continui e condizionali nidificati.
---
**Autore:** Taglia1305
**Tecnologie:** Python 3, Dynamic Data Management, User Interaction
**Tecnologie:** Python 3, Gestione Dizionari, GitHub
