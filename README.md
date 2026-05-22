```
 ____       _     _                                       
|  _ \ ___ | |___| | ____ _  __ _ _   _ _ __ ___  _ __ ___
| |_) / _ \| / __| |/ / _` |/ _` | | | | '__/ _ \| '_ ` _ \
|  __/ (_) | \__ \   < (_| | (_| | |_| | | | (_) | | | | | |
|_|   \___/|_|___/_|\_\__,_|\__, |\__,_|_|  \___/|_| |_| |_|
                            |___/
```

> Polski anti-slop skill dla Claude Code, Codex, Cursor i innych. Wycina AI-bełkot, łapie błędy gramatyczne, naprawia interpunkcję i kalki z angielskiego.

---

## Po co to

LLM-y piszą po polsku jak korpo-prezentacja z 2007: „w oparciu o", „stanowi kluczowy element", „dedykowane rozwiązanie adresujące potrzeby". Bełkot.

`polskagurom` to skill, który czyta twój tekst, wycina ten bełkot, sprawdza gramatykę i zwraca naturalną polszczyznę — **bez zmiany twojego stylu**.

## Instalacja

```bash
# do projektu
npx skills add wojtekwoz/polskagurom

# globalnie (wszędzie)
npx skills add wojtekwoz/polskagurom -g

# tylko do Claude Code
npx skills add wojtekwoz/polskagurom -g -a claude-code
```

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

## Co dostajesz

1. **Poprawiony tekst** jako plain text (do skopiowania bez czyszczenia)
2. **Listę zmian** w formacie `"przed" → "po"` z krótkim why
3. **Wątpliwości flagowane**, nie zgadywane — skill pyta zamiast nadinterpretować

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

## Co skill łapie

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
└── pleonazmy ─────────────  cofać się do tyłu, dzień dzisiejszy,
                             okres czasu, w pełni kompletny
```

## Struktura

```
skills/polskagurom/
├── SKILL.md              # workflow + frontmatter (entry point)
├── checklist.md          # 14-punktowa quick check (zawsze ładowana)
├── anti-slop.md          # kalki, AI-tells, korpomowa (on-demand)
└── grammar-reference.md  # 7 przypadków, rekcja, interpunkcja (on-demand)
```

Token-efficient: skill ładuje tylko checklist (mała). Reference czyta gdy widzi konkretny problem.

## Co skill **nie** robi

- **Nie formalizuje.** Casual zostaje casualem. Slang nie wycinany.
- **Nie zmienia tonu.** Anti-slop ≠ corporate filter.
- **Nie zmienia długości na siłę.** Tnie tylko bełkot, nie content.
- **Nie zgaduje.** Jak nie wie — pyta.

## Wsparcie agentów

Działa wszędzie gdzie działają skille przez `skills.sh`: Claude Code, Codex, Cursor, OpenCode + 50+ innych. Pełna lista: [skills.sh](https://skills.sh).

## Licencja

MIT — rób co chcesz.

## Autor

[@wojtekwoz](https://github.com/wojtekwoz) · [wozu.co](https://wozu.co)

Issues, suggestions, dodatkowe reguły → [GitHub Issues](https://github.com/wojtekwoz/polskagurom/issues).
