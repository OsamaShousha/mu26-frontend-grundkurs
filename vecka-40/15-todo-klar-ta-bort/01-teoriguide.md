# 01 — Teoriguide: Markera klar & ta bort

> **Så använder du denna guide:** Här slipar du **målsvar** du ska kunna säga högt / skriva i README. Tar du paketet från noll — läs klart, gör sen [03 — Övningar](./03-ovningar.md) och [04 — AI-träning](./04-ai-traning.md). Se också [mappens README](./README.md).

Vi börjar med **vad som går sönder** när du “ändrar listan på plats” — sedan bygger vi upp hur du byter ut state med en *ny* array. Det är inte magi. Det är en metod.

Ingen ny layout här. Ingen ny bygg-setup. Du har redan en lista i state och kan visa den med `.map()`.

---

## Problemet först — “jag ändrade ju raden”

Många tänker nu: “Jag sätter `done = true` på objektet. Klart.” Andas.

**Dåligt läge:** Du har tre rader i en array. Du bockar av rad 2 genom att skriva på *samma* objekt och *samma* array. Skärmen rör sig inte — eller värre: den rör sig ibland, ibland inte. Du tar bort med `splice` och undrar varför React inte reagerar.

Det är två olika jobb:

1. **Ändra en rad** (klar ↔ oklar) utan att förstöra de andra.  
2. **Ta bort en rad** utan att lämna ett hål du måste “städa”.

Båda löses med **ny array in i `setItems`**. Inte med att sudda på originalet.

---

## Utskriften — du skriver inte på enda exemplaret

**Metafor:** Tänk en **utskriven packlista**. Originalet ligger i skrivaren. Bockar du av “sovsäck” med penna på enda pappret har du *muterat* listan — och du har ingen ren kopia kvar. I React gör du tvärtom: du **skriver ut en ny lista**. På den nya utskriften är just den raden bockad. Den gamla utskriften slängs.

Ta bort “tält” = ny utskrift **utan** den raden. Inte ett kryss ovanpå ordet.

**Vad det är:** Immutabel uppdatering = du skapar en *ny* array (och vid toggle: ett *nytt* objekt för den raden).  
**Varför det finns:** React jämför “fick jag en ny lista?”. Skriver du på samma array kan den missa att något hänt.  
**Om det saknas / vad det INTE är:** Det är INTE att `.map()` “ritar klart-bockar”. Map *bygger nästa lista*. Det är INTE CSS. Det är INTE att du måste lära ett nytt ramverk.

**Målsvar (säg högt / skriv i README):** *“Jag byter inte ut en rad inuti den gamla arrayen. Jag ger React en ny array där just den raden (eller avsaknaden av den) är förändringen.”*

---

## Objekt, inte bara sträng — raden har mer än text

En sträng `"Sovsäck"` kan inte bära både namn och status. När raden ska kunna vara klar *och* ha text behöver du ett objekt.

```js
{ id: 1, text: "Sovsäck", done: false }
```

**Vad det är:** `id` = vilken rad, `text` = vad som står, `done` = klar eller inte.  
**Varför det finns:** Toggle ska träffa *en* rad. Utan `id` gissar du på index — och index flyttar sig när du tar bort.  
**Om det saknas / vad det INTE är:** Sträng räcker INTE när en rad både har text och status. `id` är INTE samma sak som platsen i listan (index 0, 1, 2).

**Målsvar (säg högt / skriv i README) — objekt:**  
*“Sträng räcker inte när en rad både har text och status. Objekt `{ id, text, done }` låter oss uppdatera en egenskap utan att tappa resten.”*

---

## Toggle — `.map()` bygger ny lista

**Problem först:** Det här *muterar* och litar på samma array:

```js
function markeraKlar(id) {
  const träff = items.find((item) => item.id === id)
  träff.done = !träff.done
  setItems(items)
}
```

Du skrev på originalet. `setItems(items)` skickar *samma* array tillbaka.

**Bättre:** ny array, nytt objekt för matchande `id`:

```js
function toggleKlar(id) {
  setItems(
    items.map((item) =>
      item.id === id ? { ...item, done: !item.done } : item
    )
  )
}
```

| Del | Vad det är (+ bild) | Varför | Om saknas / INTE |
|-----|---------------------|--------|------------------|
| `.map()` | Gå igenom varje rad, lämna tillbaka en *ny* lista | En utskrift till | INTE “mutera den du hittar” |
| `item.id === id` | Rätt lapp i högen | Annars bockar du fel rad | INTE samma sak som index |
| `{ ...item, done: !item.done }` | Ny kopia av *den* raden, bara `done` bytt | Övriga fält ska följa med | INTE `item.done = true` på originalet |
| `setItems(...)` | Här byts state | Utan den här raden händer inget i UI | INTE “klicket räcker” |

**Målsvar (säg högt / skriv i README) — toggle:**  
*“Vi skapar en ny array där just den raden fått nytt `done`-värde — t.ex. med `.map()` som returnerar ett nytt objekt för matchande id, övriga oförändrade.”*

---

## Ta bort — `.filter()` lämnar resten

**Problem först:** `items.splice(i, 1)` + `setItems(items)` — du klipper i originalet.

**Bättre:** ny lista utan den `id`:n.

```js
function taBort(id) {
  setItems(items.filter((item) => item.id !== id))
}
```

**Vad det är:** `.filter()` behåller raderna som *klarar* testet. `!== id` = “alla utom den jag klickade”.  
**Varför det finns:** Ta bort = inte “sudda texten”, utan *ingen rad med det id:t längre*.  
**Om det saknas / vad det INTE är:** Filter *visar* inte “dolda” rader. Den bygger en kortare array. Det är INTE samma jobb som toggle (där raden ska *finnas kvar* med nytt `done`).

**Målsvar (säg högt / skriv i README) — ta bort:**  
*“`setItems(items.filter((item) => item.id !== id))` — en ny array utan den raden.”*

---

## Peka: var uppdateras state?

Många tänker: “State sitter i knappen.” Nej. Knappen *anropar*. Byten sitter i `setItems(...)`.

**Vad det är:** En handler (`toggleKlar`, `taBort`) som anropas med `id`, och som **enda** den gör mot listan är att anropa `setItems` med ny array.  
**Varför det finns:** Examinationen (muntligt) vill att du pekar: *här* byts datan.  
**Om det saknas:** Du kan klicka, men du kan inte förklara kedjan. Då äger du inte koden.

**Målsvar (säg högt / skriv i README) — var state uppdateras:**  
*“Uppdateringen sitter i `setItems` / `setTodos`. Klicket skickar `id` till en funktion som lägger in en ny array — med `.map()` för toggle och `.filter()` för delete.”*

---

## Metod — när du tvekar “ska jag ändra objektet?”

Det är inte magi. Tre steg:

1. **Har raden ett `id`?** Skicka `id` från knappen/checkboxen — inte “rad nummer tre”.  
2. **Toggle?** `.map()` → nytt objekt för matchande id. **Delete?** `.filter()` → utan den id:n.  
3. **`setItems` med resultatet.** Peka på den raden. Det är bytet.

**Vad metoden är:** Ett sätt att uppdatera lista utan att skriva på originalet.  
**Varför den finns:** Exam 2 kräver klar + ta bort, och muntligt att du kan peka.  
**Om den saknas:** Mutation, fel rad, eller UI som inte följer med.

**Målsvar (säg högt / skriv i README) — metod:**  
*“Id från klicket. Toggle med map (nytt objekt). Delete med filter (ny kortare lista). Alltid in i setItems.”*

---

## Vanliga missar

| Miss | Rättare tanke |
|------|----------------|
| `item.done = true` sen `setItems(items)` | Nytt objekt + ny array. Samma array räcker ofta inte |
| Ta bort med `map` och `null` | Filter. Raden ska inte finnas |
| Toggle med `filter` | Filter tar bort. Toggle ska *behållas* med nytt `done` |
| Hitta raden med index `items[2]` | `id` överlever när listan kortas |
| “Map ritar knappen” | Map bygger nästa *data*. JSX ritar sen utifrån state |
| Ny CSS / ny layout “så det syns” | Synlig klar-stil är nästa paket. Här: datan ska stämma |
| Ny Vite-app “för att göra rätt” | Samma app. Bara två handlers till |

---

## Checkpoint (privat)

Skriv i Docs/anteckningar — för dig:

1. Varför objekt `{ id, text, done }` och inte bara en sträng?  
2. Vad gör `.map()` vid toggle — i en mening?  
3. Vad gör `.filter()` vid delete — i en mening?  
4. Peka (i tanken) på *vilken rad* som är `setItems` — varför just den?

När du kan säga svaren högt utan att titta: gå vidare.

---

## Nästa steg

Gå till [02 — Visuellt](./02-visuell.md), sedan övningarna.
