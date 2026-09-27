# 03 — Övningar

**Omfång det här paketet:** Markera rad som klar (toggle `done` med `.map()`) och ta bort rad (`.filter()`). Immutabel `setItems`. Peka var state uppdateras. Ingen ny CSS-layout. Ingen ny app-setup. Listan ska bara *finnas* så handlers har något att uppdatera.

AI får hjälpa dig knappa. Du måste kunna **peka och förklara** varje `setItems`-rad du behåller.

---

## Uppgift 1 — Packlista: bocka av utan att sudda originalet

**Mål:** Toggle `done` med `.map()`. Förstå problemet när du skriver på samma objekt.

**Problem först:** Startläget visar tre saker att packa. Det *finns* rader. Det finns **ingen** fungerande “klar”-handling. Det är läget du ska ta dig ur.

```jsx
const [saker, setSaker] = useState([
  { id: 1, text: "Sovsäck", done: false },
  { id: 2, text: "Vattenflaska", done: false },
  { id: 3, text: "Karta", done: false },
])
```

Visa `saker` med `.map()`. En knapp eller checkbox per rad. Tema: **vandring/packning** — inte en att-göra-app med “köpa mjölk / städa”.

**Krav:**
1. Varje rad har `{ id, text, done }`.  
2. Klick på *en* rad vänder `done` för **bara den** `id`:n via `.map()` och `setSaker`.  
3. Du skriver **inte** `sak.done = true` på originalet.  
4. I anteckningar: en mening som pekar ut `setSaker`-raden — *varför* den är bytet.

**Klart-check (peka i DIN kod):**
- [ ] Tre rader syns  
- [ ] Peka: `.map()`-uttrycket och säg *varför* du returnerar nytt objekt bara vid matchande `id`  
- [ ] Peka: `setSaker(...)` — *varför* state uppdateras just där, inte i knappen  
- [ ] Två klick på samma rad: `done` går dit och tillbaka  

**Ägarskap:**
- Utan AI: skriv handler själv.  
- Med AI: tillåtet som bollplank — spara prompten och **en mening** om vad du ändrade om AI muterade arrayen. Du ska kunna förklara varje rad.

---

## Uppgift 2 — Läslista: ta bort en titel du skippar

**Mål:** `.filter()` för delete. Koppla till samma pek-regel som toggle.

Många tänker nu: “Jag sätter texten till tom sträng så försvinner den.” Nej. Raden ska **inte finnas** i nästa array.

**Brief:** En **läslista** (böcker/artiklar du tänkt läsa). Minst tre titlar som objekt. En ta-bort-knapp per rad. Valfritt: samma toggle som i uppgift 1 så du har *båda* Exam 2-handlingarna i en app.

```jsx
const [titlar, setTitlar] = useState([
  { id: 1, text: "The Pragmatic Programmer", done: false },
  { id: 2, text: "Eloquent JavaScript", done: false },
  { id: 3, text: "CSS Secrets", done: false },
])
```

**Krav:**
1. `setTitlar(titlar.filter((t) => t.id !== id))` eller likvärdigt — ny array utan den raden.  
2. Inget `splice` på originalet.  
3. Efter delete: övriga rader kvar, samma `id`:n.  
4. I anteckningar: tre meningar — (a) skillnad map vs filter, (b) var `setTitlar` sitter, (c) varför `id` och inte index.

**Klart-check (peka i DIN kod):**
- [ ] En titel försvinner från skärmen när du tar bort  
- [ ] Peka på `filter`-villkoret och säg *varför* det är `!== id`  
- [ ] Peka på `setTitlar` / `setSaker` och förklara VARFÖR det är state-bytet  
- [ ] Anteckningarnas tre meningar är *dina* ord  

**Ägarskap:** Samma regel som uppgift 1. Om AI skrev `delete titlar[i]`: skriv om till filter du kan stå för.

---

## Uppgift 3 — Stretch (valfritt)

En app, båda handlers: packlista *eller* läslista. Peka på **två** `set…`-rader (toggle + delete) och säg högt vilken som är map och vilken som är filter.

**Klart-check:** Kan du göra det utan att titta i teoriguiden? Om ja: du har muntlig mini-träning.

---

## När du kört fast

1. Logga `id` i handler — kommer rätt id in?  
2. Kör metoden högt: id? map eller filter? setItems?  
3. Jämför med [01-teoriguide](./01-teoriguide.md) — särskilt tabellen och målsvaren.  
4. UI orörligt: du skickar troligen samma array in igen.  
5. Gå vidare till [04 — AI-träning](./04-ai-traning.md).
