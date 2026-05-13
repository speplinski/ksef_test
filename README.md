# KSeF Connect — koncept integracji

Prototyp interfejsu integracji z Krajowym Systemem e-Faktur (KSeF). Agnostyczny — bez brandingu, neutralna paleta, gotowy do iteracji.

## Struktura

```
ksef/
├── code/
│   └── prototyp-ksef.html   # pojedynczy plik HTML (CSS + JS inline)
├── requirements.md          # wymagania / notatki
├── .gitignore
└── README.md
```

## Uruchomienie

Otwórz `code/prototyp-ksef.html` w przeglądarce — działa lokalnie, bez serwera ani zależności.

## Co jest w prototypie

Pełny obieg dwukierunkowy: pulpit z KPI i strumieniem zdarzeń, faktury wystawione (statusy KSeF, numer KSeF, UPO, kody błędów walidacji), faktury otrzymane, sesje API (interactive / batch), uwierzytelnianie (pieczęć kwalifikowana / token / profil zaufany), uprawnienia, kontrahenci z białą listą, ustawienia środowiska TEST/PROD.

Interakcje: klik w wiersz tabeli otwiera drawer szczegółu z timeline KSeF, przycisk „Nowa faktura" otwiera modal wysyłki, ⌘K fokusuje wyszukiwarkę, Esc zamyka.

## Konwencja commitów

Krótkie, opisowe komunikaty w trybie rozkazującym, np. `dodaj widok korekt`, `popraw kolory pill warn`, `rozbij CSS do osobnego pliku`.
