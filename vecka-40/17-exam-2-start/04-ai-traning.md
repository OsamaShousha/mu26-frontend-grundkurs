# 04 — AI-träning: Feedback på AI-kod & ägarskap

AI kan generera en “hel todo” på sekunder. Examinationen mäter om *du* kan sålla. Här tränar du **enklare feedback**: konkret rad → konkret ändring — samma färdighet kursplanen kräver.

Inga nya API:er. Samma lista, samma `set…`.

---

## Scenario — problem först

Du ber AI: *“Skriv min React-todo med lägg till, klar och ta bort.”*  
Du får tillbaka något i stil med:

```jsx
function addTodo() {
  todos.push({ text: input })
  setTodos(todos)
}

function toggle(i) {
  todos[i].done = !todos[i].done
  setTodos(todos)
}

function remove(i) {
  todos.splice(i, 1)
  setTodos(todos)
}

return todos.map((t) => <li>{t.text}</li>)
```

Det *kan* råka rita rader. Det är svagt mot Exam 2 *och* mot ägarskap:

- `push` / `splice` / `done =` **muterar**.  
- Inget `id`, ingen `key`.  
- `setTodos(todos)` samma array.  
- Ingen visuell klar-skillnad, ingen CSS-import.  
- Du kan inte peka “under huven” om du inte förstår varför det är fel.

**Vad du tränar:** Feedback-rader du kan återanvända i README (“jag fick X, jag ändrade till Y”).  
**Varför:** Muntan och kursens feedback-mål.  
**Vad det INTE är:** Att be om Redux “så det blir VG”.

---

## Din uppgift (ca 45–75 min)

### Steg 1 — Prompt
Skriv en egen prompt (eller jobba mot snutten) där du ber om todo-funktionerna. Spara prompten — den kan bli README-exemplet.

### Steg 2 — Granska (checklist)
- [ ] Mutation (`push`, `splice`, `objekt.fält =`)?  
- [ ] Map/filter + ny array in i `setTodos`?  
- [ ] `id` + `key`?  
- [ ] Klar-stil / `className`?  
- [ ] Extra API du inte kan förklara?  
- [ ] Kan du förklara varje funktion övergripande — och minst en under huven?

Skriv **minst tre** rader:  
`FEEDBACK: [vad jag ser] → [vad som måste ändras]`

### Steg 3 — Anpassa
Rätta **en** av funktionerna (add, toggle eller delete) i övningsappen *eller* skriv den rätta versionen i `FEEDBACK.md` bredvid prompten. Inte ett nytt bibliotek.

### Steg 4 — Reflektion (3 meningar)
1. Vad var svagt i AI-förslaget?  
2. Vad ändrade du (konkret)?  
3. Varför måste du kunna säga det högt på muntan?

---

## Klart-check (peka i DITT material)

- [ ] Tre FEEDBACK-rader sparade  
- [ ] Peka på en mutation du strök — *varför*  
- [ ] En rättad funktion du kan förklara  
- [ ] Reflektionens tre meningar — användbara i exam-README  

---

## Facit-riktning (titta efter du granskat själv)

Exempel på giltig feedback (dina egna ord får skilja sig):

- `FEEDBACK: todos.push + setTodos(todos) → ny array, t.ex. [...todos, nyttObjekt] med id.`  
- `FEEDBACK: todos[i].done = → map, nytt objekt för matchande id.`  
- `FEEDBACK: splice på index → filter på id.`  
- `FEEDBACK: map utan key → key={id} på raden.`  
- `FEEDBACK: ingen klar-stil → extra className när done är true.`

**Målsvar (säg högt / skriv i README) — ägarskap:**  
*“Jag tar emot AI-kod som utkast, skriver FEEDBACK-rader, och behåller bara det jag kan peka på i VS Code.”*

---

Nästa: [05 — Självtest](./05-sjalvtest.md).
