# Java Threads: Sequence Bell

Progetto Java per la gestione di una sequenza ordinata di eventi tramite programmazione concorrente.

## Descrizione
Il programma coordina tre thread diversi affinché emettano i suoni "DIN", "DON" e "DAN" in un ordine ciclico rigoroso, simulando il rintocco sincronizzato di una campana.



## Funzionamento dei Thread:
* **ThreadSuono (DIN)**: Attende il suo turno per emettere il primo rintocco della sequenza.
* **ThreadSuono (DON)**: Attende che il rintocco "DIN" sia stato completato.
* **ThreadSuono (DAN)**: Attende che il rintocco "DON" sia stato completato per chiudere il ciclo.

Il programma utilizza un monitor sulla classe `Campana` e una variabile di stato (`suonoCorrente`) per gestire i turni. I metodi `.wait()` e `.notifyAll()` garantiscono che solo il thread autorizzato proceda, mentre gli altri rimangono in attesa.

## Tecnologie e Concetti
* **Java Core**: Utilizzo della classe `Thread` e della struttura `ArrayList` per la gestione della sequenza.
* **Sincronizzazione a Turni**: Implementazione di una logica a stati per forzare l'ordine di esecuzione tra thread concorrenti.
* **Coordinamento**: Uso di `.notifyAll()` per risvegliare i thread e verificare la condizione di avanzamento della sequenza.
