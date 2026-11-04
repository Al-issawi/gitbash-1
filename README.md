# Laboratorio Git Bash 1

Práctica de Git desde Git Bash con dos partes: ramas con publicación y merge; y tres commits seguidos de `reset` local y remoto.

## 1. Ramas, merge y GitHub

1. Inicialicé el repo y usé `main`.
2. Creé `feature/add-rama-page`, añadí `rama.html` y confirmé el cambio.
3. Subí `main` y la rama de característica a `origin`.
4. Fusioné la rama en `main`, hice push y borré la rama tanto local como remotamente.
5. Revisé el resultado con `git log --oneline`.

Comandos principales:

```bash
git init
git branch -M main
git add index.html
git commit -m "Add homepage for Git Bash practice"
git switch -c feature/add-rama-page
git add rama.html
git commit -m "Add feature page on branch"
git remote add origin https://github.com/Al-issawi/gitbash-1.git
git push -u origin main
git push -u origin feature/add-rama-page
git switch main
git merge feature/add-rama-page
git push origin main
git branch -d feature/add-rama-page
git push origin --delete feature/add-rama-page
git log --oneline
```

## 2. Tres commits y reset

Después de completar la parte de ramas, hice tres commits nuevos en `main` y los subí. Luego usé el SHA del primero de esos tres commits para quitar los otros dos localmente y actualizar el historial remoto:

```bash
git commit -m "Create first reset-practice commit"
git commit -m "Add second reset-practice commit"
git commit -m "Add third reset-practice commit"
git push origin main
git reset --hard <sha-del-primer-commit-del-ejercicio>
git push --force-with-lease origin main
git log --oneline
```

`--force-with-lease` actualiza el remoto comprobando que no haya cambiado desde el último fetch/push local. El historial final de `main` conserva la parte de ramas y el primer commit del ejercicio de reset.

## Archivos de historial

Los archivos `mdaliGitlog.txt` y `mdaliHistorial.txt` están en la carpeta `reset/` del laboratorio. El primero contiene la salida de `git log --oneline` después del reset; el segundo se generó con `history 50 > mdaliHistorial.txt` desde Git Bash.

## Repositorio

[Al-issawi/gitbash-1](https://github.com/Al-issawi/gitbash-1)
