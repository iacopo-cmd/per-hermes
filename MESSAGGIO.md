# Messaggio da dare all'agente (Hermes)

Da incollare all'agente così com'è:

```
Installa la sonda di MiniBench Net su questa macchina. Scrivimi prima cosa fai, poi:
git clone https://github.com/iacopo-cmd/per-hermes.git && cd per-hermes && cat AGENTS.md
python3 -I minibench-net.py --installa-agente
Il comando fa 5 passi da solo (la chiave se la ricava la sonda: niente da approvare). Non chiedere niente a nessuno.
Quando finisce, mandami le righe dal [5/5] in giù. Se dice FERMO, mandami le righe esatte e fermati.
```

Dalla nostra parte non c'è niente da fare: l'iscrizione è automatica (v2), arriva un avviso, la macchina resta in quarantena
e passa da sola a «buona» dopo qualche giorno di dati coerenti. Se è una macchina nostra: `./minibench-chiave fiducia ID nostra`.
