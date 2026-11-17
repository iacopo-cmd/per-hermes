# Messaggio da dare all'agente (Hermes)

Da incollare all'agente così com'è:

```
Installa la sonda di MiniBench Net su questa macchina. Scrivimi prima cosa fai, poi:
git clone https://github.com/iacopo-cmd/per-hermes.git && cd per-hermes && cat AGENTS.md
python3 -I minibench-net.py --installa-agente
Il comando fa 5 passi da solo e al passo 2 aspetta che approviamo la chiave: tu aspetta, non chiedere niente.
Quando finisce, mandami le righe dal [5/5] in giù. Se dice FERMO, mandami le righe esatte e fermati.
```

Dalla nostra parte, quando l'agente è al passo 2: `./minibench-chiave richieste` → `./minibench-chiave approva N`,
poi, appena la chiave è ritirata, `./minibench-chiave elenco` → `./minibench-chiave fiducia ID nostra` (il primo test aspetta fino a un'ora).
