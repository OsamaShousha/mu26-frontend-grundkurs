# 05 — Självtest

Svara **först** utan att titta på facit. Skriv i Docs/anteckningar — privat, för dig. Sikta på målsvar du kan *säga högt*.

Sedan: öppna facit och rätta dig.

---

## Frågor

1. Hur kopplar du en CSS-fil till en React-komponent?  
2. Varför `className` och inte `class` i JSX?  
3. State säger `done: true` men raden ser likadan ut. Vilket lager saknas?  
4. Ge ett konkret exempel på visuell skillnad klar vs oklar.  
5. Beskriv debug-kedjan när stil “inte tar”.  
6. Varför är `display: none` på klara rader svagt mot Exam 2?  
7. Måste du använda Grid för “enkel layout”?  
8. Peka i *din* kod: `import`-raden och klar-klassen — **varför** just de.

---

## Facit

<details>
<summary>Visa facit (målsvar-nivå)</summary>

1. `import "./App.css"` (eller motsvarande sökväg) i komponenten som ritar UI.  
2. `class` är reserverat i JavaScript. JSX använder `className`.  
3. Etiketten — CSS-klass som faktiskt appliceras när `done` är true.  
4. T.ex. `text-decoration: line-through` + lägre `opacity` på extra klassen.  
5. Spara → import → `className` (inte `class`) → Inspect: finns klassen? Överskrivs den?  
6. Exam kräver att det *syns* vilka som är klara — inte att de försvinner.  
7. Nej. Lista, fält och knappar som går att förstå räcker. Inget nytt layoutsystem.  
8. Subjektivt — rimligt om du kopplar import → regler och klass → klar-rad. Fel om “AI stylade den”.

</details>

---

## Klart för paketet?

Om dina svar ligger nära facit, övningarna är gjorda, och du kan peka i egen kod:

- [ ] Målsvar CSS i React — egna ord, högt  
- [ ] Målsvar klar vs oklar — egna ord, högt  
- [ ] Målsvar debug — egna ord, högt  
- [ ] Import + klar-klass pekade  

Då har du landat CSS i React. Nästa paket: [17-exam-2-start](../17-exam-2-start/).
