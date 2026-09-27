# 01 — Teoriguide: CSS i React

> **Så använder du denna guide:** Här slipar du **målsvar** du ska kunna säga högt / skriva i README. Tar du paketet från noll — läs klart, gör sen [03 — Övningar](./03-ovningar.md) och [04 — AI-träning](./04-ai-traning.md). Se också [mappens README](./README.md).

Vi börjar med **vad som går sönder** när datan är rätt men ögat inte ser det — sedan kopplar vi in CSS-filen och sätter en tydlig klar-stil. Det är inte magi. Det är samma CSS du redan kan, plus två kopplingsregler.

Ingen ny Grid-kurs. Inga designverktyg. Inga nya React-API:er. Du har redan en lista med `done`.

---

## Problemet först — “den ÄR ju klar”

Många tänker nu: “`done` är `true`. Då måste det synas.” Andas.

**Dåligt läge:** Checkboxen slår om. State stämmer. På skärmen ser alla rader likadana ut. En kompis (eller du om tre veckor) kan inte avgöra vad som är avklarat. Eller: du klistrar `style={{}}` överallt och vet inte var utseendet bor.

Det är två olika lager:

1. **Data** — `done: true` i objektet.  
2. **Etikett** — CSS som gör skillnaden synlig.

Exam 2 kräver båda. Det här paketet är lagret du *ser*.

---

## Etikett på burken — och streck i anteckningsboken

**Metafor:** En burk i skafferiet *är* basilika även utan lapp — men du öppnar fel burk om etiketten saknas. **`done` är innehållet.** **CSS-klassen är etiketten** du klistrar på så du slipper gissa.

När något är avklarat i en pappersanteckning **stryker du över raden**. Samma signal på skärmen: genomstruken text, gärna lite nedtonad. Inte en ny “designlinje”. En läsbar skillnad.

**Vad det är:** En CSS-fil kopplad till komponenten + en extra klass när `done` är true.  
**Varför det finns:** Användaren (och du när du testar) ska *se* klar vs oklar.  
**Om det saknas / vad det INTE är:** Utan etikett kan datan vara rätt och UI:t ljuga. Det är INTE ett nytt layoutsystem. Det är INTE att `done` “blir rött av sig själv”.

**Målsvar (säg högt / skriv i README):** *“State vet om raden är klar. CSS visar det — t.ex. med en extra klass och genomstruken text.”*

---

## Koppla in filen — `import`, inte gissning

I HTML länkar du ofta `<link rel="stylesheet">`. I en React-komponent **importerar** du filen.

```js
import "./App.css"
```

I JSX: **`className`**, inte `class`. `class` är reserverat i JavaScript.

```jsx
<li className={sak.done ? "rad rad--klar" : "rad"}>
  {sak.text}
</li>
```

```css
.rad--klar {
  text-decoration: line-through;
  opacity: 0.6;
}
```

| Del | Vad det är (+ bild) | Varför | Om saknas / INTE |
|-----|---------------------|--------|------------------|
| `import "./App.css"` | Sladden mellan burken och etikettarken | Annars laddas inte reglerna | INTE samma sak som `link` i `index.html` här |
| `className` | JSX-namnet för CSS-klass | `class` krockar i JS | INTE `class=` i JSX |
| Extra klass vid `done` | Etiketten “avklarad” | En basklass räcker inte för två lägen | INTE att gömma raden med `display: none` |
| `line-through` | Strecket i anteckningsboken | Ögat ser skillnad | INTE krav på nytt Grid |

**Målsvar (säg högt / skriv i README) — CSS i React:**  
*“Vi importerar en CSS-fil i komponenten (`import './App.css'`). I JSX använder vi `className`, inte `class`.”*

**Målsvar (säg högt / skriv i README) — visuell feedback:**  
*“Klar rad får en annan klass (t.ex. `rad--klar`) så användaren ser skillnad — t.ex. line-through och nedtonad färg.”*

---

## Enkel layout — lista, fält, knappar

Exam 2: “grundläggande och städad layout … lätt att förstå hur den används.”

Det räcker med det du redan kan: avstånd, maxbredd, tydlig lista, input och knappar som inte sitter i en klump. En rad med fält + knapp får gärna använda `display: flex` *om du redan kan det* — det är inte en ny kurs i layoutsystem.

**Vad det är:** Sidan ska gå att *använda*: var skriver jag, var ligger listan, vad gör knapparna.  
**Varför det finns:** En osynlig input eller tre knappar utan luft är svåra att betjäna — och svåra att redovisa.  
**Om det saknas / vad det INTE är:** Det är INTE att bygga ett rutnät från grunden. Det är INTE att jaga pixelperfekt “design”.

**Målsvar (säg högt / skriv i README) — layout:**  
*“Lista, textfält och knappar är lätta att hitta. CSS ligger i en importerad fil. Inget nytt layoutsystem krävs.”*

---

## Metod — när stilen “inte tar”

Många tänker: “React hatar CSS.” Nej. Tre stopp:

1. **Sparad fil? Importerad?** Ingen `import` → ingen etikettark.  
2. **Rätt `className` i JSX?** Stavfel, eller `class=` som JSX struntar i. Villkor: sätts klassen när `done` är true?  
3. **Inspect i DevTools:** Finns klassen på elementet? Överskrivs den av en mer specifik regel?

**Vad metoden är:** En felsökningskedja på grundnivå.  
**Varför den finns:** Du ska kunna *debugga* enkel CSS/JS — inte gissa i 20 minuter.  
**Om den saknas:** Du byter slumpmässiga värden tills “det ser bättre ut”.

**Målsvar (säg högt / skriv i README) — debug:**  
*“Om stil saknas: spara → kolla import → kolla className → Inspect: finns klassen på elementet? Överskrivs den?”*

---

## Vanliga missar

| Miss | Rättare tanke |
|------|----------------|
| `class="rad"` i JSX | `className="rad"` |
| CSS-fil skapad men aldrig importerad | `import "./App.css"` i komponenten som ritar listan |
| Alla rader ser likadana ut | Extra klass när `done` är true — t.ex. genomstruken |
| `display: none` på klara rader | De ska *synas*, men annorlunda — Exam kräver tydlig skillnad |
| Nytt Grid “för att det ska se proffsigt ut” | Enkel layout räcker. Inget nytt system i det här paketet |
| Allt i `style={{ margin: 40 }}` | En CSS-fil du kan peka på och förklara |
| “Inspect är för proffs” | Inspect är steg 3 i metoden — grundnivå |

---

## Checkpoint (privat)

Skriv i Docs/anteckningar — för dig:

1. Hur kopplas CSS-filen in i React?  
2. Varför `className` och inte `class`?  
3. Hur ser en klar rad annorlunda ut — peka på klassen?  
4. Tre steg när stil saknas.

När du kan säga svaren högt utan att titta: gå vidare.

---

## Nästa steg

Gå till [02 — Visuellt](./02-visuell.md), sedan övningarna.
