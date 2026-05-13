# KSeF Connect — koncept integracji

Prototyp interfejsu integracji z Krajowym Systemem e-Faktur (KSeF). Agnostyczny — bez brandingu, neutralna paleta, gotowy do iteracji.

## Struktura

```
ksef/
├── code/
│   ├── index.html           # pojedynczy plik HTML (CSS + JS inline) — entry Pages
│   └── .nojekyll            # wyłącza Jekyll dla publikowanego artefaktu
├── .github/workflows/
│   └── pages.yml            # workflow: publikuje folder code/ na GitHub Pages
├── requirements.md          # wymagania / notatki
├── .gitignore
└── README.md
```

## Uruchomienie lokalne

Otwórz `code/index.html` w przeglądarce — działa bez serwera ani zależności.

## Publikacja na GitHub Pages

1. Utwórz repo na GitHubie (publiczne — Pages dla prywatnych wymaga planu Pro/Team).
2. Podlinkuj remote i wypchnij `main`:
   ```bash
   git remote add origin git@github.com:USER/REPO.git
   git push -u origin main
   ```
3. W repo: **Settings → Pages → Build and deployment**
   - Source: **GitHub Actions**
4. Workflow `Deploy GitHub Pages` uruchomi się automatycznie po pushu. Po chwili prototyp jest pod `https://USER.github.io/REPO/`.

Workflow pakuje zawartość folderu `code/` i publikuje ją jako root strony — czyli `code/index.html` staje się stroną główną pod czystym URL-em.

## Co jest w prototypie

Pełny obieg dwukierunkowy: pulpit z KPI i strumieniem zdarzeń, faktury wystawione (statusy KSeF, numer KSeF, UPO, kody błędów walidacji), faktury otrzymane, sesje API (interactive / batch), uwierzytelnianie (pieczęć kwalifikowana / token / profil zaufany), uprawnienia, kontrahenci z białą listą, ustawienia środowiska TEST/PROD.

Interakcje: klik w wiersz tabeli otwiera drawer szczegółu z timeline KSeF, przycisk „Nowa faktura" otwiera modal wysyłki, ⌘K fokusuje wyszukiwarkę, Esc zamyka.

## Konwencja commitów

Krótkie, opisowe komunikaty w trybie rozkazującym, np. `dodaj widok korekt`, `popraw kolory pill warn`, `rozbij CSS do osobnego pliku`.
