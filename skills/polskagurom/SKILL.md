---
name: polskagurom
description: Polish-language proofreading skill for AI-generated text. Eliminates AI slop, fixes grammar (cases, verb rection, aspect), punctuation, and English calques. Use when user pastes Polish text to improve, asks to translate EN→PL naturally, or wants to remove "AI feel" from generated Polish content. Triggers on requests like "popraw ten tekst", "przetłumacz na polski", "this Polish sounds off".
license: MIT
metadata:
  author: wojtekwoz
  version: '0.1.0'
---

# Polskagurom

Skill do poprawiania polskich tekstów. Wycina AI-slop, łapie błędy gramatyczne, naprawia interpunkcję i kalki z angielskiego. Domyślnie zachowuje treść i intencję — pracuje tylko nad językiem.

Dwa tryby:
- **Poprawa** — user wkleja polski tekst → poprawiasz
- **Tłumaczenie** — user wkleja tekst po angielsku → tłumaczysz porządną polszczyzną (bez kalek)

---

## Krok 1 — Wczytaj checklistę (zawsze)

Przeczytaj: `checklist.md` (sibling file, krótka — 14 punktów, mało tokenów)

## Krok 2 — Pierwszy przebieg po tekście

Zidentyfikuj kategorię problemów. Jeśli widzisz:

- **AI-slop, kalki, wodolejstwo** → wczytaj `anti-slop.md`
- **Wątpliwości gramatyczne** (rekcja, przypadki, liczebniki, interpunkcja, pisownia "nie", aspekt) → wczytaj `grammar-reference.md`
- **Oba** → wczytaj oba

**Nie czytaj reference jeśli tekst jest prosty i nie masz wątpliwości.** Checklist + zdrowy rozsądek wystarczą.

## Krok 3 — Poprawiona wersja

Zwróć poprawiony tekst jako **plain markdown bez bloku cytatu i bez ```** (żeby user mógł skopiować bez czyszczenia).

Zasady:
- Zachowaj treść, sens i intencję. Tylko język.
- Nie zmieniaj długości tekstu dla zasady — zmieniaj tylko gdy wycinasz słop lub redundancje.
- Jeśli user ma już swój styl (casual, slang) — zachowaj go. Anti-slop ≠ formalizacja. Cel: naturalna polszczyzna w stylu autora.

## Krok 4 — Lista zmian

Po poprawionym tekście dodaj sekcję **Zmiany:** z 3-7 bulletami w formacie:

- `"przed" → "po"` — krótkie wyjaśnienie (kalka, przypadek, słop, etc.)

Bez teorii. Tylko co i dlaczego.

## Krok 5 — Wątpliwości

Jeśli czegoś nie jesteś pewien (regionalizm, świadomy wybór stylistyczny, slang celowy) — zostaw oryginał i dopisz w **Zmiany:**:

- `"X" — zostawiam, ale sprawdź: [krótkie pytanie]`

## Użycie

User wkleja tekst i pisze `/polskagurom` — zwracasz poprawioną wersję + listę zmian.

Opcjonalnie user może dopisać kontekst: `/polskagurom — to email do klienta` / `to post na LinkedIn` / `to tłumaczenie z angielskiego`.
