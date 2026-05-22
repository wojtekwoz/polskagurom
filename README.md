```
 ____       _     _                                       
|  _ \ ___ | |___| | ____ _  __ _ _   _ _ __ ___  _ __ ___
| |_) / _ \| / __| |/ / _` |/ _` | | | | '__/ _ \| '_ ` _ \
|  __/ (_) | \__ \   < (_| | (_| | |_| | | | (_) | | | | | |
|_|   \___/|_|___/_|\_\__,_|\__, |\__,_|_|  \___/|_| |_| |_|
                            |___/
```

> Polski anti-slop skill dla Claude Code, Codex, Cursor i 50+ innych. Wycina AI-bełkot, naprawia gramatykę, zostawia twój styl.

LP: **[wojtekwoz.github.io/polskagurom](https://wojtekwoz.github.io/polskagurom/)**

---

## Problem

LLM-y piszą po polsku jak korpo-prezentacja z 2007: „w oparciu o", „stanowi kluczowy element", „dedykowane rozwiązanie adresujące potrzeby". Bełkot.

`polskagurom` czyta twój tekst, wycina najgorszy bełkot i łapie błędy gramatyczne. Sam też potrafi nasypać slopu — ale wyłapuje sporo i pomaga go unikać. Myślenia nie zastąpi: wynik trzeba przeczytać z głową.

## Instalacja

```bash
npx skills add wojtekwoz/polskagurom -g
```

Działa we wszystkich narzędziach wspieranych przez [skills.sh](https://skills.sh).

## Użycie

Wklej tekst i odpal:

```
/polskagurom
```

Opcjonalnie z kontekstem:

```
/polskagurom — to email do klienta
/polskagurom — to post na LinkedIn
/polskagurom — to tłumaczenie z angielskiego
```

Skill zwraca poprawiony tekst + listę zmian (`"przed" → "po"` z krótkim uzasadnieniem). Wątpliwości zaznacza, nie zgaduje.

## Przykład

**Wejście:**

```
W oparciu o przeprowadzoną analizę, należy podkreślić, że nasza
dedykowana platforma stanowi kluczowe rozwiązanie. Decyzja została
podjęta przez zespół w celu dostarczenia wartości klientom.
```

**Wyjście:**

```
Z analizy wynika, że nasza platforma realnie pomaga firmom.
Zespół zdecydował się ją zbudować, żeby dać klientom konkretną
wartość.
```

Wycięte: `w oparciu o`, `należy podkreślić`, `dedykowana`, `stanowi`, `kluczowe`, strona bierna, `w celu`, `dostarczenia wartości`.

## Co skill wyłapuje

```
├── kalki z angielskiego ─── w oparciu o, dedykowany, adresować,
│                            dostarczać wartość, insights, deep dive
├── AI-tells ──────────────  stanowi, posiada, kluczowy, ponadto,
│                            w kontekście, podsumowując, warto zauważyć
├── gramatyka ─────────────  rekcja (używać + D., pomagać + C.),
│                            przeczenie (B. → D.), aspekt, liczebniki
├── interpunkcja ─────────── przecinek przed że/który/żeby, myślnik vs
│                            łącznik, polskie cudzysłowy „..."
├── pisownia ──────────────  nie + część mowy, tę vs tą, wielkie/małe
└── pleonazmy *────────────  cofać się do tyłu, dzień dzisiejszy,
                             okres czasu, w pełni kompletny
```

*\* nie wiedziałem, że istnieje takie słowo xd*

## Czego skill **nie** robi

- **Nie formalizuje.** Casual zostaje casualem. Slangu nie tnie.
- **Nie zmienia tonu.** Anti-slop ≠ corporate filter.
- **Nie zmienia długości na siłę.** Tnie tylko bełkot, nie treść.
- **Nie zgaduje.** Jak nie wie — pyta.

## Razem

**Zapraszam do rozwijania skilla ze mną.** To pierwsza wersja i przed nami długa droga.

[Issues](https://github.com/wojtekwoz/polskagurom/issues) · [Pull requests](https://github.com/wojtekwoz/polskagurom/pulls)

## Licencja & autor

MIT — rób, co chcesz.

[@wojtekwoz](https://github.com/wojtekwoz) · [wozu.co](https://wozu.co)
