# Moje docházka

Jednoduchá webová aplikace na evidenci pracovní docházky.

- **Frontend:** jeden soubor `index.html` (GitHub Pages)
- **Databáze a přihlášení:** Supabase (tabulka `attendance`, přihlášení odkazem na e-mail)

## Co umí

- zápis příchodu a odchodu jedním kliknutím, výběr kancelář / home office
- dovolená, svátek, nemoc jedním kliknutím (počítá se 8 h)
- měsíční přehled s týdenními součty, úprava a mazání záznamů
- fond = pracovní dny (po–pá) × 8 h; víkendová práce jde rovnou do přesčasu
- přesčas za měsíc, za rok (roční fond přesčasů) a celkem za celou historii
- grafy odpracovaných hodin, fondu a přesčasů

## Typy dne

| Kód | Význam |
|---|---|
| KANC | kancelář |
| HO | home office |
| DOV | dovolená |
| SV | svátek |
| NEM | nemoc |
| LEK | lékař |

## Zabezpečení

V kódu je jen veřejný (publishable) klíč Supabase. Data chrání pravidla Row Level Security:
každý uživatel vidí jen své záznamy a zapisovat může jen vlastník aplikace
(první přihlášený účet, tabulka `app_owner`).
