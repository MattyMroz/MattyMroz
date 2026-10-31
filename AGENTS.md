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

- Commit: nagłówek Conventional Commits po angielsku, `type(scope): opis`, ze scope'em z listy w `.pre-commit-config.yaml`; po pustej linii streszczenie „co i dlaczego”; potem sekcja `Validation:` z kontrolami uruchomionymi na finalnym indeksie. Format: https://github.com/MattyMroz/agents/blob/main/presets/hooks/references/commit-message.md
- Kontrole uruchamiaj przez `mm-validate run "<kontrola>" -- <komenda>`, blok `Validation:` bierz z `mm-validate list`. Hooki `conventional-pre-commit` i `commit-validation` odrzucą inny commit.
- Pliki dodawaj po nazwie, nigdy `git add .`; bez `--no-verify`. Worktree'y tylko w `.worktrees/<nazwa>`.
