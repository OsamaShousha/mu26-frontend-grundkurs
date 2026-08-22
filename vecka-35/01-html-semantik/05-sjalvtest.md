# 05 — Självtest

Svara **först** utan att titta på facit. Skriv i Docs/anteckningar — privat, för dig. Sikta på målsvar du kan *säga högt*.

Sedan: öppna facit och rätta dig.

---

## Frågor

1. Vad är skillnaden mellan HTML och CSS på en mening?HTML which made the website structue but CSS which design it.
   
2. Vad är skillnaden mellan `head` och `header`? (Tänk butiken: följesedel vs namnskylt.) head is html tag which contain hiden information about website(links, meta, title)
 but header it contain the top visibile part of the website(logo, menu, main heading)

4. Vad betyder **semantisk HTML**? (Sikta mot Exam README-nivå — målsvaret.) it  means that when we write html we need to use tag which describe the meaning of the content, not only using div.
   
5. Varför är det sämre att bygga hela sidan med bara `div`?  because it can be harder to understand it from other person or the person who wrote the code. it can also make it lees clear to SEO to find the website.
6. Du har en bit text som är sidans viktigaste rubrik. Vilken tagg — och varför inte `p`?  because we need to use <h1> tag to provide the important of the text so it can be easy to find the page.
 <p> just paragraph.
6. Beskriv metoden i tre steg när du är osäker på tagg.  
  + What this part about? is a meny,section, heading or article.
  + Which is the most descriping tag i can use for this part.
  + May be i use <div> if i need it for only a box for styling-layout </div>
7. Vad ska en <img> alltid ha förutom `src` — och varför? alt because if the image did not load down so the user can read the discription of the image, also it make the website more accessible for peoble with problem with reading or listing the browser will read the describtion for them.  
14. Peka i *din* kod (café, podd eller bokklubb): nämn tre taggar och **varför** du valde dem (inte “för att det såg bra ut”).
<nav> to have linksin <ul>which have </ul> or meny to help users to move or go other parts of my the website</nav>
<section> to give a clear structure for the website</section>
<footer> because it contain the ending information of the page such as contact information.

---

## Facit

<details>
<summary>Visa facit (målsvar-nivå)</summary>

1. **HTML** = struktur/betydelse; **CSS** = utseende (kommer mer senare i kursen).  
2. **`head`** = metadata *om* dokumentet (title, charset) — följesedeln. **`header`** = synligt sidhuvud i `body` — namnskylten. De är INTE samma sak.  
3. Semantisk HTML = välja taggar efter innehållets *betydelse* (t.ex. `header` för sidhuvud) så strukturen blir tydlig för människor och verktyg — inte bara `div` överallt.  
4. `div` saknar betydelse; koden blir svårare att läsa, underhålla och förstå för verktyg/andra — och du kan inte motivera den i Exam.  
5. **`h1`** — det är huvudrubrik. `p` är brödtext, inte sidans huvudämne.  
6. (1) Vad *är* innehållet? (2) Matcha tagg med samma betydelse. (3) Inte gissa “låda”/`div` — fråga hellre.  
7. **`alt`** — textalternativ om bilden inte syns / för skärmläsare. Utan `alt` saknas betydelsen för den som inte ser bilden.  
8. Subjektivt — rimligt om du kopplar tagg → betydelse (metodstegen). Fel om svaret bara är “AI skrev det” eller “det såg bra ut”.

</details>

---

## Klart för veckan?

Om dina svar ligger nära facit, övningarna är gjorda, och du kan peka i egen kod:

- [ ] Målsvar semantik — egna ord, högt  
- [ ] Målsvar metod — egna ord, högt  
- [ ] Tre taggar i din kod med *varför*

Då har du landat HTML-målet. Nästa paket: Git — se [02-git-github](../02-git-github/).
