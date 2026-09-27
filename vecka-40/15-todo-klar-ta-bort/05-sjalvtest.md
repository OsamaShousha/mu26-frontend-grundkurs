# 05 — Självtest

Svara **först** utan att titta på facit. Skriv i Docs/anteckningar — privat, för dig. Sikta på målsvar du kan *säga högt*.

Sedan: öppna facit och rätta dig.

---

## Frågor

1. Varför räcker inte en sträng per rad när du ska kunna markera klar?  
2. Vad gör `.map()` när du togglar `done`?  
3. Vad gör `.filter()` när du tar bort en rad?  
4. Du skriver `item.done = true` och sen `setItems(items)`. Vad är problemet?  
5. Var uppdateras state — i knappen, i `.map()`, eller någon annanstans? Peka med ord.  
6. Varför `id` och inte `items[2]` när du tar bort?  
7. Beskriv metoden när du tvekar: ska jag ändra objektet på plats?  
8. Peka i *din* kod: nämn toggle-raden och delete-raden och **varför** — inte “AI sa åt mig”.

---

## Facit

<details>
<summary>Visa facit (målsvar-nivå)</summary>

1. Sträng bär bara text. Klar-status behöver ett fält, t.ex. `done`, plus `id` för att träffa rätt rad.  
2. `.map()` bygger en **ny** array. Matchande `id` får ett **nytt** objekt med bytt `done`; övriga lämnas.  
3. `.filter()` bygger en **ny, kortare** array utan den `id`:n.  
4. Du muterar originalet och skickar ofta **samma** array — React kan missa bytet. Ny array + nytt objekt.  
5. I **`setItems` / `setTodos`**. Knappen anropar. Map/filter *skapar* nästa lista.  
6. Index flyttar sig när listan kortas. `id` följer raden.  
7. (1) `id` från klicket. (2) Toggle → map, delete → filter. (3) Resultatet in i `setItems`.  
8. Subjektivt — rimligt om du kopplar handler → ny array → set. Fel om svaret bara är “AI skrev det”.

</details>

---

## Klart för paketet?

Om dina svar ligger nära facit, övningarna är gjorda, och du kan peka i egen kod:

- [ ] Målsvar toggle — egna ord, högt  
- [ ] Målsvar ta bort — egna ord, högt  
- [ ] Målsvar var state uppdateras — egna ord, högt  
- [ ] Map-rad och filter-rad pekade i din kod  

Då har du landat klar/ta bort. Nästa paket: [16-css-react](../16-css-react/).
