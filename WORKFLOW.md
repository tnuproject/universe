# Universe workflow

## Mirrors

- `universe-main` -> VPS
- `universe-alt` -> GitHub

`pkg` prova prima `universe-main` e usa automaticamente `universe-alt` se il mirror principale non contiene `repo.txt` o il pacchetto richiesto.

## Porting package

1. Fork upstream in `https://github.com/tnuproject/<package>`
2. Clona il repo del pacchetto
3. Applica patch locali TNU
4. Prepara build one-command nel repo (`./build.sh`)
5. L'utente pusha le modifiche

## Publish in Universe

1. Clona il repo patchato del pacchetto
2. Esegui la build dei binari prebuilt
3. Crea il payload installabile nella directory archivio del pacchetto
4. Aggiorna `repo.txt`
5. Sincronizza `universe-main` e `universe-alt`

## Formato repo

Ogni riga in `repo.txt`:

`name|version|arch|description|archive`

`archive` punta a una directory installabile copiata da `pkg install <package>` sulla root `/`.

## Installazione

```sh
pkg update
pkg install nano
pkg install doom
```