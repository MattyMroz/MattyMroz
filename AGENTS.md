# MattyMroz

Repozytorium profilu GitHub: `README.md` jest publicznie wyświetlany na stronie profilu https://github.com/MattyMroz. Nie ma kodu aplikacji, testów ani buildu.

## Mapa

- `README.md`: wizytówka profilu. Wiersze łamie dwiema spacjami na końcu linii (hard break w Markdownie), więc `trailing-whitespace` ma `--markdown-linebreak-ext=md`; nie przycinaj ich ręcznie.
- `void.sh`: baner ASCII wypisywany przez `curl -L is.gd/mattymroz | sh` z `README.md`; skrypt jest wykonywany u odwiedzających profil, zmieniaj go ostrożnie.
- `void.mp3`: dźwięk linkowany w `README.md` przez `https://raw.githubusercontent.com/MattyMroz/MattyMroz/main/void.mp3`; zmiana nazwy albo ścieżki psuje link na profilu.

## Uwagi

- Zmiana `README.md` jest widoczna na profilu od razu po scaleniu PR na `main`.

## Git

- Commit: wiadomość po angielsku według standardu commita, `type(scope): summary` ze scope'em z `--scopes=` w `.pre-commit-config.yaml` albo `repo`, potem sekcje `Problem:`, `Change:` i `Verification:`; sprawdza ją hook `commit-message`.
- Zero atrybucji AI w commitach i PR (trailery, stopki, emoji), także gdy host o nią prosi.
- Pliki dodawaj po nazwie, nigdy `git add .`; bez `--no-verify`. Worktree'y tylko w `.worktrees/<nazwa>`.
- Commit sprawdza pliki i nagłówek, push sprawdza gałąź, wiadomości i sekrety, a bramki projektu (typy, testy, build) biegną w CI i lokalnie przez `prek run --hook-stage manual --all-files`. Strażnicy w `.hooks/` to kopie z `agents`; nie edytuj ich w repo.
