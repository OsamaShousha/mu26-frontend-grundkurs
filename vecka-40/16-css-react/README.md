# 16 — CSS i React

> **📖 Hur du använder materialet:** Detta GitHub-repo fungerar som din digitala kursbok. Du behöver inte klona något för att läsa — klicka på länkarna i webbläsaren.

**Den här mappen täcker:** CSS-fil i React, enkel layout (lista / input / knappar), visuell skillnad klar vs oklar, **onsdag 30 september**.  
Pass i samma kalendervecka utan filer här får en rad i körschemat.

Ingen ny Grid-kurs. Ingen Figma. Inga nya state-handlers — du ska ha en fungerande lista med toggle.

---

## 🗺️ Veckans körschema

| Dag / Tillfälle | Före passet (Förberedelse) | Live i Teams | Efter passet (Eget arbete) |
| :--- | :--- | :--- | :--- |
| **Mån 28/9 — Klar / ta bort** | Skumma [15 — teoriguide](../15-todo-klar-ta-bort/01-teoriguide.md) ~15 min | Toggle + delete | [15-todo-klar-ta-bort](../15-todo-klar-ta-bort/) |
| **Ons 30/9 — CSS i React** | Ha fungerande lista. Skumma [16 — teoriguide](../16-css-react/01-teoriguide.md) | Layout + klar-stil | [16-css-react](../16-css-react/) |
| **Fre 2/10 — Exam 2-start** | Läs Exam 2-briefen (Moodle) ~10–15 min | AI-feedback + eget repo | [17-exam-2-start](../17-exam-2-start/) |

Spåren nedan gäller **den här mappen**.

---

## 🎯 Välj din väg i materialet

### 🟢 1. Du var med på live-passet (Repetition & Praktik)
*Om du hängde med på skärmen och förstod koncepten:*
1. [ ] **Bygg med fingrarna:** [03 — Övningar](./03-ovningar.md)
2. [ ] **Träna kritiskt tänkande:** [04 — AI-träning](./04-ai-traning.md)
3. [ ] **Kontrollera dina målsvar:** [05 — Självtest](./05-sjalvtest.md) utan facit först  
*( [01 — Teoriguide](./01-teoriguide.md) som uppslagsverk bara om du kör fast.)*

---

### 🟡 2. Du missade passet eller börjar från noll (Ta ikapp-spåret)
*Om du var sjuk, hade förhinder eller känner att grunderna inte sitter:*
1. [ ] **Förstå koncepten:** [01 — Teoriguide](./01-teoriguide.md) från start till mål
2. [ ] **Få överblick:** [02 — Visuellt](./02-visuell.md)
3. [ ] **Koda själv:** [03 — Övningar](./03-ovningar.md)
4. [ ] **Granska & anpassa:** [04 — AI-träning](./04-ai-traning.md)
5. [ ] **Slutkontroll:** [05 — Självtest](./05-sjalvtest.md)

Saknar du toggle `done`: ta [15-todo-klar-ta-bort](../15-todo-klar-ta-bort/) först.

---

### 🟣 3. Du siktar på VG / vill fördjupa dig (Stretch)
*Om du blev klar snabbt — frivilligt, inom kursplanen:*
- [ ] **Stretch i övningarna:** Inspect-runda när stil “inte tar” i [03 — Övningar](./03-ovningar.md)
- [ ] **README-träning:** tre meningar: (1) hur CSS-filen kopplas in, (2) `className` vs `class`, (3) hur klar-raden ser annorlunda ut
- [ ] **Dokumentera:** i anteckningar: “Stilen saknades — jag hittade det genom att …” (import / className / Inspect)

---

## 🗣️ Målsvar att kunna utantill inför examinationen

När mappen är klar ska du kunna återge dessa med egna ord:

> **CSS i React:** "Vi importerar en CSS-fil i komponenten (`import './App.css'`). I JSX använder vi `className`, inte `class`."

> **Klar vs oklar:** "Klar rad får en extra klass så användaren ser skillnad — t.ex. genomstruken text och nedtonad färg."

> **Debug:** "Om stil saknas: spara → kolla import → kolla `className` → Inspect: finns klassen på elementet? Överskrivs den?"

---

## 📝 Examination

**Examination 2** kräver **enkel, städad layout** och att det **syns tydligt** vilka uppgifter som är klara. Det här paketet är den grunden. Inget nytt layoutsystem krävs.

## 🏁 Nästa steg

När du är klar här: [17-exam-2-start](../17-exam-2-start/) — testa hela flödet, AI-feedback och starta eget exam-repo (fre 2/10).
