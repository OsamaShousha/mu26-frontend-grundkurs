# 03 — Övningar

**Omfång det här paketet:** Importera CSS-fil, `className`, enkel layout (lista / input / knappar), visuell skillnad klar vs oklar, felsök på grundnivå. Ingen ny Grid-kurs. Inga designfiler. Inga nya state-API:er — listan med `done` ska redan fungera.

AI får föreslå färger. Du måste kunna **peka och förklara** `import` och klar-klassen.

---

## Uppgift 1 — Veckomeny: burkarna ska gå att hitta

**Mål:** Städad, begriplig layout. CSS i egen fil som importeras.

**Problem först:** Du har en lista (t.ex. **veckomeny**: måndagssoppa, tisdagspasta …) med input + knapp för att lägga till och rader som kan markeras. Utan CSS sitter fält, knapp och lista i en klump. Det är läget du ska ta dig ur.

Tema: veckomeny eller **verktyg att lämna tillbaka** — inte samma packlista/läslista som i förra paketet, och inte en kopia av någon eventsida.

**Krav:**
1. En CSS-fil, t.ex. `App.css`, med `import "./App.css"` i komponenten som ritar UI.  
2. Layout som går att *använda*: var skriver jag, var är listan, var är knapparna. Luft, maxbredd eller enkel rad för fält+knapp är ok. **Inget nytt rutnät som kursmoment.**  
3. JSX använder `className`, inte `class`.  
4. I anteckningar: en mening som pekar ut `import`-raden — *varför* den behövs.

**Klart-check (peka i DIN kod):**
- [ ] Input, lista och knappar är lätta att skilja åt på skärmen  
- [ ] Peka på `import` och säg *varför* filen annars inte gäller  
- [ ] Peka på minst två `className` och säg *vad* de stylar  
- [ ] Ingen `class=` i JSX  

**Ägarskap:**
- Utan AI: skriv CSS själv.  
- Med AI: tillåtet som bollplank — stryk layoutsystem du inte kan förklara. En mening om vad du tog bort.

---

## Uppgift 2 — Avklarad rad ska se avklarad ut

**Mål:** Tydlig skillnad klar vs oklar. Träna debug-kedjan.

**Brief:** Samma app. När `done` är true ska raden **synas annorlunda** — t.ex. genomstruken (`text-decoration: line-through`) och nedtonad. Inte dold.

**Krav:**
1. Extra klass när `done` är true (t.ex. `ratt--klar`).  
2. Skillnaden syns utan att man måste gissa.  
3. **Felsök med flit:** ta bort `import` tillfälligt, notera vad som händer, lägg tillbaka. Öppna Inspect: peka på klassen på det klara elementet.  
4. I anteckningar: tre meningar — (a) hur CSS kopplas in, (b) hur klar-klassen sätts, (c) vad Inspect visade.

**Klart-check (peka i DIN kod):**
- [ ] En klar och en oklar rad syns *olika*  
- [ ] Peka på villkoret i `className` och säg *varför* extra klassen sitter där  
- [ ] Peka i DevTools: klassen finns på elementet  
- [ ] Du kan räkna upp debug-kedjan (spara → import → className → Inspect)  

**Ägarskap:** Om AI gömde klara rader med `display: none`: skriv om så de syns men är överstrukna. Exam kräver tydlig skillnad, inte att de försvinner.

---

## Uppgift 3 — Stretch (valfritt)

En tredje klass för knappar (t.ex. ta-bort vs “klar”). Fortfarande samma CSS-fil. Ingen ny teknik.

**Klart-check:** Peka på tre klasser i filen och säg vilken burk/etikett var och en tillhör (lista, klar-rad, knapp).

---

## När du kört fast

1. Debug-kedjan högt: sparad? import? className? Inspect?  
2. Jämför med [01-teoriguide](./01-teoriguide.md) — särskilt tabellen.  
3. Klassen i CSS men inte på elementet → villkoret i JSX. Klassen på elementet men ingen effekt → stavfel eller överskrivning.  
4. Gå vidare till [04 — AI-träning](./04-ai-traning.md).
