# 04 — AI-träning: Immutabel lista & ägarskap

AI kan klistra in en “klart-knapp” på sekunder. Det betyder inte att *du* äger state-bytet. Här tränar du samma färdighet som muntan kräver: **se vad som är svagt, ändra, förklara**.

Det är inte magi att “granska AI”. Det är samma metod som i teoriguiden — id → map eller filter → `setItems`.

---

## Scenario — problem först

Du ber AI: *“Lägg till markera klar och ta bort på min lista.”*  
Du får tillbaka något i stil med:

```js
function toggle(i) {
  items[i].done = !items[i].done
  setItems(items)
}

function remove(i) {
  items.splice(i, 1)
  setItems(items)
}
```

Det *kan* råka se ut att funka. Det är ändå svagt mot det här paketets krav:

- `items[i].done = …` skriver på **originalet**.  
- `splice` klipper i **samma** array.  
- `setItems(items)` skickar ofta **samma referens** tillbaka.  
- Index `i` är inte `id` — efter en delete pekar “rad 2” på fel sak.  
- Inget förklarar *var* state byts.

**Vad du tränar:** Feedback på AI-kod + handlers *du* äger.  
**Varför:** Muntligt kräver att *du* pekar: map vs filter, och `setItems`.  
**Vad det INTE är:** “Det visades på skärmen, alltså är koden rätt.”

---

## Din uppgift (ca 45–75 min)

### Steg 1 — Prompt
Skriv en egen prompt till AI (eller jobba bara mot snutten ovan utan ny AI) där du ber om toggle + delete för en packlista eller läslista. Spara prompten.

### Steg 2 — Granska (checklist)
Gå igenom svaret (AI:ns eller snutten) och kryssa:

- [ ] Muteras objekt/array på plats (`done =`, `push`, `splice`)?  
- [ ] Används `.map()` för toggle och `.filter()` för delete?  
- [ ] Matchas raden med **`id`** — eller bara index?  
- [ ] Finns `setItems` / `setTodos` med *ny* array?  
- [ ] Extra API du inte kan förklara (reducer, context, library)?  
- [ ] Kan du peka på raden där state uppdateras och säga varför?

Skriv **minst tre** konkreta feedback-punkter i formen:  
`FEEDBACK: [vad jag ser] → [vad som måste ändras]`

### Steg 3 — Anpassa
Skriv (eller rätta i [03](./03-ovningar.md)) **två handlers du äger** — en toggle, en delete. Inga mutationer. Spara dem i `HANDLERS.md` i projektmappen (kod + en rad kommentar *du* skrivit: var byts state).

### Steg 4 — Reflektion (3 meningar)
Skriv i anteckningar eller samma `HANDLERS.md`:

1. Vad var fel eller svagt i AI-förslaget (eller snutten)?  
2. Vad ändrade du?  
3. Varför spelar immutabel uppdatering roll när du ska förklara koden?

---

## Klart-check (peka i DIN kod)

- [ ] Tre FEEDBACK-rader sparade  
- [ ] Peka på `set…`-raden och säg *varför* den är bytet  
- [ ] Peka på något du *tog bort* från AI-listan — varför behövdes det inte?  
- [ ] Reflektionens tre meningar klara  

---

## Facit-riktning (titta efter du granskat själv)

Exempel på giltig feedback (dina egna ord får skilja sig):

- `FEEDBACK: items[i].done = … → map som returnerar nytt objekt för matchande id.`  
- `FEEDBACK: splice + samma array → filter på id, ny array in i setItems.`  
- `FEEDBACK: index i → använd id så delete inte flyttar “rätt rad”.`  
- `FEEDBACK: setItems(items) efter mutation → skicka resultatet av map/filter, inte originalet.`

**Målsvar (säg högt / skriv i README) — ägarskap:**  
*“Jag tar emot AI-förslag som utkast, stryker mutation och index-gissningar, och behåller bara map/filter + setItems jag kan peka på.”*

---

Nästa: [05 — Självtest](./05-sjalvtest.md).
