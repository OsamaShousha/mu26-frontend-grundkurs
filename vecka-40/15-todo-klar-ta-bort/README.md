# 15 — Markera klar & ta bort

> **📖 Hur du använder materialet:** Detta GitHub-repo fungerar som din digitala kursbok. Du behöver inte klona något för att läsa — klicka på länkarna i webbläsaren.

**Den här mappen täcker:** markera rad som klar + ta bort rad (immutabel state), **måndag 28 september**.  
Pass i samma kalendervecka utan filer här får en rad i körschemat.

Ingen ny layout-teori. Ingen Vite-intro. Du ska redan kunna visa en lista och lägga till rader.

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

Saknar du lägg-till och `.map()`: ta [14-map-filter](../vecka-39/14-map-filter/) först.

---

### 🟣 3. Du siktar på VG / vill fördjupa dig (Stretch)
*Om du blev klar snabbt — frivilligt, inom kursplanen:*
- [ ] **Stretch i övningarna:** båda funktionerna i samma app + peka på *båda* `set…`-raderna i [03 — Övningar](./03-ovningar.md)
- [ ] **README-träning:** tre meningar: (1) varför objekt `{ id, text, done }`, (2) vad `.map()` gör vid toggle, (3) vad `.filter()` gör vid delete
- [ ] **Dokumentera:** i anteckningar: “State uppdateras *här*” — klistra in de två raderna och skriv *varför* de skapar ny array

---

## 🗣️ Målsvar att kunna utantill inför examinationen

När mappen är klar ska du kunna återge dessa med egna ord:

> **Toggle klar:** "Vi skapar en ny array där just den raden fått nytt `done`-värde — t.ex. med `.map()` som returnerar ett nytt objekt för matchande id, övriga oförändrade."

> **Ta bort:** "`setItems(items.filter((item) => item.id !== id))` — en ny array utan den raden."

> **Var state uppdateras:** "Uppdateringen sitter i `setItems` / `setTodos` — klicket anropar en funktion som skickar in den nya arrayen."

---

## 📝 Examination

**Examination 2 (ToDo)** kräver att användaren kan **markera som klar** och **ta bort** en uppgift. Muntligt i VS Code: du ska kunna peka på funktionerna och förklara var state byts ut. CSS för klar/oklar kommer i [16](../16-css-react/).

## 🏁 Nästa steg

När du är klar här: [16-css-react](../16-css-react/) — CSS i React och visuell skillnad klar vs oklar (ons 30/9).
