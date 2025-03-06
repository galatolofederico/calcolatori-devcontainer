# DevContainer per Calcolatori Elettronici

Questo è un ambiente di sviluppo containerizzato per il corso di [Calcolatori Elettronici](https://calcolatori.iet.unipi.it/) della Scuola di Ingegneria dell'Università di Pisa.

## Caratteristiche

Il DevContainer include tutti gli strumenti necessari per completare le esercitazioni e la prova pratica del corso, tra cui:

- **libce**: Libreria di supporto per gli esempi I/O e il nucleo
- **QEMU modificato**: Versione patchata di QEMU per il corso
- **Toolchain completa**: Include compilatori e strumenti necessari (gcc, g++, etc.)
- **Tool per scaricare esami**: Utility per scaricare automaticamente le prove d'esame passate

## Utilizzo dello script `scarica-esame`

Il container include uno script `scarica-esame` per gestire il download degli esami passati:

```bash
# Visualizzare tutte le date disponibili
scarica-esame list

# Scaricare l'esame di una data specifica
scarica-esame yyyy-mm-dd
```

## Ambiente preconfigurato

Questo DevContainer include:

- **Build tools**: gcc/g++ con supporto multilib per compilazione a 32/64 bit
- **Debugger**: GDB per il debug dei programmi
- **Librerie**: Tutte le dipendenze necessarie per compilare ed eseguire il nucleo e gli esempi
- **Percorsi**: PATH già configurato per utilizzare gli strumenti del corso

## Come iniziare

1. Assicurati di avere Docker e VS Code con l'estensione Dev Containers installati
2. Clona questo repository e aprilo in VS Code
3. Quando richiesto, seleziona "Reopen in Container"
4. Usa lo script `scarica-esame` per scaricare gli esami di tuo interesse
5. Inizia a lavorare sugli esercizi!

## Licenza e contributi

Questo progetto è rilasciato sotto licenza [GPLv3](https://www.gnu.org/licenses/gpl-3.0.txt).

Pull Request da parte degli studenti sono benvenute!
In caso di problemi o suggerimenti, sentiti libero di aprire una Issue sul repository.
I contributi degli studenti sono particolarmente apprezzati per migliorare questo ambiente e renderlo più utile per i futuri studenti del corso.