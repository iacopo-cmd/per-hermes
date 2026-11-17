# Istruzioni per l'agente: installa la sonda di MiniBench Net (Hermes)

Sei un agente (Hermes) in un container Linux, probabilmente senza root. Il tuo compito: installare e accendere la sonda di
**MiniBench Net**, che misura CPU, steal e rete di questa macchina e manda i risultati al nostro server.
Non serve configurare niente: `config.env.esempio` è già compilato per te. Non modificare i file di questa cartella.

## Si fa con UN comando
```bash
python3 -I minibench-net.py --installa-agente
```
Fa da solo 5 passi e li stampa: [1/5] verifica, [2/5] chiave, [3/5] primo test della CPU, [4/5] demone in background, [5/5] rapporto.
- Al passo 2 la sonda chiede la chiave al server e **aspetta da sola** che la approviamo (di solito 1-2 minuti, al massimo 3 ore).
  Tu non devi chiedere niente a nessuno: aspetta che il comando vada avanti.
- Il passo 3 dura qualche minuto e carica la CPU: è normale.
- Tutto resta nella cartella `dati/` accanto al client (config, chiave, stato, `demone.log`).

## Regole
- PRIMA di lanciarlo, scrivi all'umano: «lancio la sonda di MiniBench Net (5 passi, qualche minuto)».
- Quando finisce, scrivi all'umano le righe dal `[5/5]` in giù. Se si ferma con **FERMO**, riporta le righe esatte e fermati.
- La chiave è un segreto: non aprire né stampare `dati/chiave` e `dati/stato/sale`. Non installare pacchetti, non aprire porte.
- Se il container riparte, rilancia lo stesso comando: riprende da dove era (non chiede una chiave nuova).

## Per controllare dopo
```bash
tail -5 dati/demone.log      # righe «check n.X: 201», «ping n.X: 201», «test n.X: 201»
```
