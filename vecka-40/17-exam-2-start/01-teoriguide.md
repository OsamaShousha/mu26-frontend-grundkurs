# 01 — Teoriguide: Examination 2-start

> **Så använder du denna guide:** Här slipar du **målsvar** du ska kunna säga högt / skriva i README. Tar du paketet från noll — läs klart, gör sen [03 — Övningar](./03-ovningar.md) och [04 — AI-träning](./04-ai-traning.md). Se också [mappens README](./README.md).

Vi börjar med **vad som går sönder** om du lämnar in övningsappen och hoppas — sedan går vi igenom kraven, hur du ger enkel feedback på AI-kod, och hur du startar *ditt* repo. Det är inte magi. Det är en checklista + ägarskap.

Inga nya React-API:er. Tekniken du behöver finns redan.

---

## Problemet först — “kan jag inte bara lämna in den här?”

Många tänker nu: “Övningslistan funkar. Jag byter namn och pushar.” Andas.

**Dåligt läge:** Du har en app du halvförstår. README är tom. På muntan öppnar du VS Code och fastnar på `setTodos`. Eller: du klistrar in AI-kod du inte kan peka i.

Två olika saker:

1. **Provköket** — övningsappen där du *testar* hela flödet.  
2. **Rätten med ditt namn** — eget GitHub-repo, byggd från grunden, README du kan stå för, muntligt i VS Code.

Examinationen är (2). (1) är där du smakar av innan du sätter namnbrickan.

---

## Provkök och namnbricka

**Metafor:** I ett **provkök** kör du hela rätten: tillsätt, smaka, bocka av, släng det som inte ska med. Du hittar vad som saknas *innan* gästen kommer. **Examinationen** är samma rätt, men i *din* kökslåda (eget repo) med namnbricka på dörren (README) och du som förklarar receptet högt (muntligt i editorn).

**Vad det är:** Testa flödet i övningen → ge feedback på AI-utkast → starta eget publikt repo.  
**Varför det finns:** Exam 2 mäter *din* app och *din* förklaring — inte att någon övningsfil råkar finnas.  
**Om det saknas / vad det INTE är:** Övningsmappen är INTE inlämningen. Nytt API “för VG” är INTE krav. Kopiera-klistra utan att kunna peka är INTE ägarskap.

**Målsvar (säg högt / skriv i README) — Exam 2 i en mening:**  
*“Individuell React-todo: lägg till, visa, markera klar med synlig skillnad, ta bort, enkel CSS — plus eget GitHub, README-reflektion och muntligt i VS Code (G övergripande / VG under huven).”*

---

## Funktionskrav — vad appen ska göra

Du ska kunna **göra** detta i din exam-app:

| Krav | Vad du gör | Vad du ser när det är klart |
|------|------------|-----------------------------|
| Lägga till | Skriv i textfält, klicka knapp | Ny rad i listan |
| Visa listan | — | Alla skapade rader syns |
| Markera klar | Checkbox eller knapp per rad | Tydlig visuell skillnad klar vs oklar |
| Ta bort | Radera-knapp per rad | Raden är borta |
| Enkel layout | CSS i projektet | Går att förstå hur den används |

**Vad det är:** Observerbara handlingar — inte “en snygg todo-känsla”.  
**Varför det finns:** Godkänt = appen gör raderna ovan.  
**Om det saknas:** En av raderna röd = inte G än.

---

## Inlämning, README, muntligt

**Repo:** Eget **publikt** GitHub-repository. Inlämning = länken i Moodle.

**README:** Kort reflektion, ca **3–5 meningar**:

- Hur hittade du lösningar när du körde fast? (dokumentation, tutorials, Google, AI …)  
- Om du använde AI: **ett exempel** på prompt/utmaning där du **anpassade** koden så den passade *din* app.

**Muntligt i VS Code** (inte webbläsar-demo som enda bevis):

- **G:** 2–3 valfria funktioner, **övergripande** hur koden fungerar.  
- **VG:** samma golv + **under huven** — logik, hur data rör sig, totalt ägarskap. Ren struktur (komponenter, namn, state/props) räknas in.

**Vad det INTE är:** “Jag visade appen i Chrome.” Editorn är rummet.  
**Vad ägarskap är:** AI ok som verktyg. Kod du inte kan förklara → underkänt.

**Målsvar (säg högt / skriv i README) — ägarskap:**  
*“AI får användas, men jag måste kunna förklara och försvara koden i VS Code. Annars saknas ägarskap.”*

**Målsvar (säg högt / skriv i README) — G vs VG:**  
*“G: övergripande om 2–3 funktioner i VS Code. VG: under huven — state, props, varför ny array — plus ren struktur.”*

---

## Enklare feedback på AI-kod

Kursen kräver att du kan ge **enklare feedback** på AI:s (eller annans) kod: vad funkar, vad måste ändras *innan* du använder den.

**Metod — tre frågor:**

1. **Vad ska snutten göra?** (lägg till / toggle / delete / stil)  
2. **Kan jag förklara varje del?** Om nej: antingen lär du den eller stryker den.  
3. **Minst en konkret ändring** innan den får komma in i *din* app.

Bra feedback pekar: `FEEDBACK: [rad/idé] → [vad som måste ändras]`.

**Vad det är:** Granskning, inte “AI sa att det var best practice”.  
**Varför det finns:** Du ska kunna sålla mutation, fel namn, extra API, kod utan `key`.  
**Om det saknas / vad det INTE är:** Det är INTE att skriva en recension av verktyget. Det är INTE ett nytt React-API.

**Målsvar (säg högt / skriv i README) — AI-feedback:**  
*“Bra feedback pekar på konkret rad/idé: t.ex. muterar state, saknar key, fel prop-namn — och säger vad som ska ändras innan koden används.”*

---

## Starta eget exam-repo

1. Nytt **publikt** repo på GitHub (ditt namn i slugen hjälper, t.ex. `fornamn-todo`).  
2. Klona. Öppna mappen i VS Code.  
3. Skapa React-appen **från grunden** där — inte zip från övningsmappen som “inlämning”.  
4. Första commit när skelettet finns. Push. Kolla att github.com visar filerna.

Övningsappen får vara **facit för flödet** du redan testat. Koden du lämnar in ska vara *din* i *det* repot.

---

## Vanliga missar

| Miss | Rättare tanke |
|------|----------------|
| Lämna in övningsrepot | Eget repo, byggt för examinationen |
| README: “Jag använde AI” | 3–5 meningar + *ett* konkret anpassningsexempel |
| Muntligt bara i webbläsaren | VS Code, 2–3 funktioner |
| Nytt bibliotek “för VG” | VG = djup i *din* kod, inte fler API:er |
| AI-kod in utan FEEDBACK | Minst en sak att ändra/förstå först |
| “Jag gör README i v41” | Börja utkast nu så reflektionen blir sann |

---

## Checkpoint (privat)

Skriv i Docs/anteckningar — för dig:

1. Exam 2 i en mening.  
2. Fem funktionskrav.  
3. G vs VG på muntan.  
4. En FEEDBACK-rad du *skulle* ge en svag AI-snutt.

När du kan säga svaren högt utan att titta: gå vidare.

---

## Nästa steg

Gå till [02 — Visuellt](./02-visuell.md), sedan övningarna.
