# 04 — AI-träning: CSS i React & ägarskap

AI kan spotta ur sig “snygg todo-CSS” på sekunder. Det betyder inte att *du* äger kopplingen. Här tränar du: **se vad som är svagt, ändra, förklara**.

Det är inte magi. Det är import + `className` + etikett för `done`.

---

## Scenario — problem först

Du ber AI: *“Styla min lista i React så den ser proffsig ut.”*  
Du får tillbaka något i stil med:

```jsx
<ul class="lista" style={{ display: "grid", gridTemplateColumns: "1fr 1fr 1fr" }}>
  <li style={{ textDecoration: item.done ? "line-through" : "none" }}>
    {item.text}
  </li>
</ul>
```

Ingen `import`. En kommentar: `/* glöm inte länka i index.html */`.

Det *kan* se “designat” ut. Det är svagt mot det här paketet:

- **`class=`** i JSX.  
- **Inline** `style=` blandar utseende in i logiken.  
- **`display: grid` + tre kolumner** är ett layoutsystem du inte ska gömma dig bakom här.  
- **Ingen importerad CSS-fil** — du kan inte peka på reglerna.  
- Klar-stil bara som inline gör debug-kedjan (Inspect → klass) meningslös.

**Vad du tränar:** Feedback + en CSS-fil *du* äger.  
**Varför:** Exam 2 kräver enkel layout + synlig klar/oklar — och att du kan förklara den.  
**Vad det INTE är:** “Grid såg proffsigt ut, alltså är det rätt nivå.”

---

## Din uppgift (ca 45–75 min)

### Steg 1 — Prompt
Skriv en egen prompt till AI (eller jobba bara mot snutten ovan) där du ber om styling för lista + klar vs oklar. Spara prompten.

### Steg 2 — Granska (checklist)
Gå igenom svaret (AI:ns eller snutten) och kryssa:

- [ ] Finns `import "./….css"`?  
- [ ] `className` eller `class`?  
- [ ] Inline `style=` överallt, eller klasser i fil?  
- [ ] Nytt layoutsystem (Grid-kurs) du inte kan försvara?  
- [ ] Klar-rader dolda (`display: none`) istället för synlig skillnad?  
- [ ] Kan du förklara varje regel muntligt?

Skriv **minst tre** konkreta feedback-punkter i formen:  
`FEEDBACK: [vad jag ser] → [vad som måste ändras]`

### Steg 3 — Anpassa
Flytta utseendet till **en CSS-fil du importerar**. Enkel layout. Extra klass vid `done`. Spara en kort `STIL.md` med: import-raden + klar-klassen + en mening om vad du strök från AI.

### Steg 4 — Reflektion (3 meningar)
1. Vad var fel eller svagt i AI-förslaget?  
2. Vad ändrade du?  
3. Varför är import + klass lättare att peka på än inline Grid?

---

## Klart-check (peka i DIN kod)

- [ ] Tre FEEDBACK-rader sparade  
- [ ] Peka på `import` och på klar-klassen  
- [ ] Peka på något du *tog bort* (t.ex. Grid eller `class=`) — varför?  
- [ ] Reflektionens tre meningar klara  

---

## Facit-riktning (titta efter du granskat själv)

Exempel på giltig feedback (dina egna ord får skilja sig):

- `FEEDBACK: class= → className i JSX.`  
- `FEEDBACK: ingen import → import './App.css' i komponenten.`  
- `FEEDBACK: grid tre kolumner → enkel lista/fält/knappar; inget nytt layoutsystem här.`  
- `FEEDBACK: all stil inline → klasser i CSS-fil så jag kan Inspect:a och förklara.`

**Målsvar (säg högt / skriv i README) — ägarskap:**  
*“Jag tar emot AI-CSS som utkast, flyttar den till en importerad fil med className, och stryker layout jag inte kan försvara.”*

---

Nästa: [05 — Självtest](./05-sjalvtest.md).
