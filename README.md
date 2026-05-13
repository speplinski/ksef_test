# KSeF Connect — koncept integracji

Prototyp interfejsu integracji z Krajowym Systemem e-Faktur (KSeF). Agnostyczny — bez brandingu, neutralna paleta, gotowy do iteracji.

**Live preview:** https://speplinski.github.io/ksef_test/  
**Repo:** https://github.com/speplinski/ksef_test

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

Repo jest skonfigurowane do publikacji przez GitHub Actions. Workflow pakuje zawartość folderu `code/` i wystawia ją jako root strony (czyli `code/index.html` staje się stroną główną pod czystym URL-em).

```bash
# pierwszy push
git push -u origin main

# kolejne zmiany
git add -A
git commit -m "opis"
git push
```

Jednorazowo w repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**. Po pushu w zakładce **Actions** uruchomi się workflow „Deploy GitHub Pages". Po ok. minucie strona jest dostępna pod https://speplinski.github.io/ksef_test/.

## Co jest w prototypie

Pełny obieg dwukierunkowy: pulpit z KPI i strumieniem zdarzeń, faktury wystawione (statusy KSeF, numer KSeF, UPO, kody błędów walidacji), faktury otrzymane, sesje API (interactive / batch), uwierzytelnianie (pieczęć kwalifikowana / token / profil zaufany), uprawnienia, kontrahenci z białą listą, ustawienia środowiska TEST/PROD.

Interakcje: klik w wiersz tabeli otwiera drawer szczegółu z timeline KSeF, przycisk „Nowa faktura" otwiera modal wysyłki, ⌘K fokusuje wyszukiwarkę, Esc zamyka.

## Konwencja commitów

Krótkie, opisowe komunikaty w trybie rozkazującym, np. `dodaj widok korekt`, `popraw kolory pill warn`, `rozbij CSS do osobnego pliku`.


Coś zmieniam.
