# checkRepoSync.sh

## Descrizione

`checkRepoSync.sh` è uno script Bash progettato per semplificare la gestione e la sincronizzazione delle repository Git locali e remote. Esso fornisce una serie di funzioni che automatizzano i comuni compiti legati a Git, riducendo così la necessità di eseguire manualmente una serie di comandi.

## Funzionalità

- Verifica lo stato di sincronizzazione tra la repository locale e la remota.
- Offre opzioni per sincronizzare la repository locale con la remota e viceversa.
- Gestisce conflitti di merge e rebase.

## Requisiti

- Git (versione >= 2.0 consigliata per le migliori prestazioni)
- Bash (versione 4.0 o superiore)

## Installazione

1. Clona la repository sul tuo sistema locale:

```bash
git clone https://github.com/tuo-username/checkRepoSync.git
```

2. Assegna i permessi di esecuzione allo script:

```bash
chmod +x checkRepoSync.sh
```

## Dettagli Tecnici

Lo script utilizza diversi comandi Git per ottenere informazioni sulla repository e per eseguire le operazioni di sincronizzazione. Ecco alcuni dei comandi chiave utilizzati:

- `git fetch origin`: Recupera i dati dalla repository remota ma non li applica al branch locale.
- `git rev-parse @` e `git rev-parse @{u}`: Ottengono l'ultimo commit dal branch locale e remoto, rispettivamente.
- `git merge-base @ @{u}`: Trova l'ultimo commit comune tra il branch locale e il branch remoto.

Le funzioni principali dello script sono:

- `check_repo_status`: Verifica lo stato della repository e determina quale azione è necessaria (sincronizzazione, nessuna azione, ecc.).
- `sync_local_with_remote` e `sync_remote_with_local`: Eseguono la sincronizzazione effettiva tra le repository locali e remote.

## Utilizzo

Esecuzione base dello script:

```bash
./checkRepoSync.sh
```

Questo eseguirà lo script e fornirà un resoconto sullo stato di sincronizzazione tra la tua repository locale e quella remota. Seguendo le istruzioni a schermo, sarà possibile effettuare diverse operazioni di sincronizzazione.

### Opzioni   **(TODO: Non ancora implementate)**

Lo script supporta diverse opzioni per un controllo più fine:

- `-l, --local`: Sincronizza la repository locale con quella remota.
- `-r, --remote`: Sincronizza la repository remota con quella locale.
- `--rebase`: Utilizza il rebase invece del merge durante la sincronizzazione.
- `-f, --force`: Forza la sincronizzazione senza conferma dell'utente.

## Esempi

1. Eseguire lo script senza opzioni per ottenere una panoramica dello stato della repository:

```bash
./checkRepoSync.sh
```

    Questo mostrerà se la repository locale è avanti, indietro o sincronizzata con la remota.

2. Sincronizzare la repository locale con la remota:

```bash
./checkRepoSync.sh -l
```

3. Sincronizzare la repository remota con quella locale:

```bash
./checkRepoSync.sh -r
```

Nota: Per ulteriori dettagli sulle opzioni disponibili, consultare la sezione "Utilizzo" o eseguire `./checkRepoSync.sh --help`.

## Licenza

Questo progetto è rilasciato sotto la Licenza GPLv3. Per maggiori dettagli, vedi il file [LICENSE](LICENSE).
