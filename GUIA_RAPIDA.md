# Guia ràpida de Git per al taller

Canvia `N` pel número de la teua issue i `nom` per una paraula que descriga la pantalla.

## Començar una història

```bash
git switch main
git pull
git switch -c historia/N-nom
cp pantalles/_plantilla.md pantalles/0N-nom.md
```

## Guardar i pujar

```bash
git add pantalles/0N-nom.md README.md
git commit -m "Afig la pantalla X (#N)"
git push -u origin historia/N-nom
```

Després, en GitHub: **Compare & pull request**. Comprova que el *base repository* és **el teu fork**. Escriu `Closes #N` en la descripció.

## Després de fusionar

```bash
git switch main
git pull
```

## Si la PR té conflictes

```bash
git switch historia/N-nom
git merge main
# obri el fitxer, deixa les dues línies i esborra <<<<<<<, ======= i >>>>>>>
git add README.md
git commit -m "Resol el conflicte del menú"
git push
```

## Si has fet commit en main per error

```bash
git switch -c historia/N-nom
git switch main
git reset --hard origin/main
```
