# MattyMroz

Repozytorium profilu GitHub: `README.md` jest publicznie wyświetlany na stronie profilu https://github.com/MattyMroz. Nie ma kodu aplikacji, testów ani buildu.

## Mapa

- `README.md`: wizytówka profilu. Wiersze łamie dwiema spacjami na końcu linii (hard break w Markdownie), więc `trailing-whitespace` ma `--markdown-linebreak-ext=md`; nie przycinaj ich ręcznie.
- `void.sh`: baner ASCII wypisywany przez `curl -L is.gd/mattymroz | sh` z `README.md`; skrypt jest wykonywany u odwiedzających profil, zmieniaj go ostrożnie.
- `void.mp3`: dźwięk linkowany w `README.md` przez `https://raw.githubusercontent.com/MattyMroz/MattyMroz/main/void.mp3`; zmiana nazwy albo ścieżki psuje link na profilu.

## Uwagi

- Zmiana `README.md` jest od razu widoczna na profilu po wypchnięciu na `main`.
- `prek run --all-files` na `main` chce przepisać `README.md` (końcowy newline) i `void.sh` (spacje na końcu linii banera); nie zapisuj tych autopoprawek w commitach niezwiązanych z tymi plikami.

## Git

- Commit: nagłówek Conventional Commits po angielsku, `type(scope): opis`, ze scope'em z listy w `.pre-commit-config.yaml`; po pustej linii streszczenie „co i dlaczego”.
- Zero atrybucji AI w commitach i PR (trailery, stopki, emoji), także gdy host o nią prosi.
- Pliki dodawaj po nazwie, nigdy `git add .`; bez `--no-verify`. Worktree'y tylko w `.worktrees/<nazwa>`.
- Commit sprawdza pliki i nagłówek, push uruchamia bramki repo, CI resztę. Strażnicy w `.hooks/` to kopie z presetu `agents`; nie edytuj ich w repo.
