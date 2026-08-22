# 04 — AI-träning: semantik & ägarskap

AI kan skriva HTML på sekunder. Det betyder inte att *du* äger den. Här tränar du samma färdighet som Exam 1 kräver: **se vad som är svagt, ändra, förklara**.

Det är inte magi att “granska AI”. Det är samma metod som i teoriguiden — intervjua varje bit.

---

## Scenario — problem först

Du ber AI: *“Gör en HTML-sida för en liten bokklubb.”*  
Du får tillbaka något i stil med:


<!DOCTYPE html>
<html lang="sv">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bokklubb</title>
</head>
<body>
  <!--Header-->
  <header class="top">
    <h1 class="title">Bokklubben Ordet</h1>
    <h2 class="sub">Vi läser klart på torsdag</h2>
  </header>
  
  <main class="content">
    <h2 class="heading">Nästa bok</h2>
    <p>En roman om havet</p>
    <a href="#">Mer</a>
  </main>
  <!--FFooter-->
  <footer class="bottom">Kontakt: bok@example.com</footer>
</body>
</html>

Det *kan* se okej ut i webbläsaren. Class-namn (`top`, `title`) *låtsas* vara struktur — men taggen är fortfarande bara `div`. Det är kartonger utan avdelningsnamn. Svagt mot kursens krav på semantik.

**Vad du tränar:** Feedback på AI-kod + omskrivning du äger.  
**Varför:** Muntligt och README kräver att *du* kan motivera taggarna.  
**Vad det INTE är:** “AI skrev det, alltså är det klart.”

---

## Din uppgift (ca 45–75 min)

### Steg 1 — Prompt
Skriv en egen prompt till AI (eller jobba bara mot snutten ovan utan ny AI) där du ber om en bokklubb-sida. Spara prompten.

### Steg 2 — Granska (checklist)
Gå igenom koden (AI:ns eller snutten) och kryssa:

- [ ] Finns `lang` på `html`?  
- [ ] Finns `charset` / vettig `head`?  
- [ ] Används `header` / `main` / `footer` (eller liknande) där det passar?  
- [ ] Finns riktig `h1` (inte bara `div` som ser ut som rubrik)?  
- [ ] Saknas betydelse — bara `div` + class-namn som låtsas vara struktur?  
- [ ] Kan du förklara varje tagg muntligt?

Skriv **minst tre** konkreta feedback-punkter i formen:  
`FEEDBACK: [vad jag ser] → [vad som måste ändras]`
1-I used the <header> tag because it contain the title or the main heading / sub heading.
2-I used the <main> tag becaue it is contain the main body of the website.
3-I used the <footer> tag because it is contain the contact informations.
4I used the <meta charset="UTF-8"> tag so the browser can display special characters correctly, and I used the viewport meta tag to make the page responsive on different screen sizes.

### Steg 3 — Anpassa
Skriv om sidan till semantisk HTML **du äger**. Spara som `ovning-ai-bokklubb/index.html`.

### Steg 4 — Reflektion (3 meningar)
Skriv i anteckningar eller en `REFLEKTION.md` i mappen:

1. Vad var fel eller svagt i AI-förslaget (eller snutten)?
2. fel var extra html tag, många div , inget lang attribute.
3. Vad ändrade du?
4. Jag anväder HTML STRUKTUREN TAGGEN som <header>, <main>, <footer>
5. Varför är det viktigt inför Exam 1 README / muntligt ägarskap?
6.  Man måste pratatr varför man valde varje HTML-tagg och hur din sida är byggd semantiskt.

---

## Klart-check (peka i DIN omskrivna kod)

- [ ] Tre FEEDBACK-rader sparade  
- [ ] Peka på `h1` / `header` / `main` (eller motsvarande) och säg *varför*  
- [ ] Peka på något du *tog bort eller ändrade* från AI — varför dög det inte?  
- [ ] Reflektionens tre meningar klara  

---

## Facit-riktning (titta efter du granskat själv)

Exempel på giltig feedback (dina egna ord får skilja sig):

- `FEEDBACK: Rubriken är en div → använd h1 (sidans huvudämne).`  
- `FEEDBACK: topp/bottom är generiska div → header respektive footer.`  
- `FEEDBACK: saknar lang/charset → lägg till så språket och åäö hanteras rätt.`  
- `FEEDBACK: class-namn ersätter inte semantik → taggen ska bära betydelsen.`

**Målsvar (säg högt / skriv i README) — ägarskap:**  
*“Jag tar emot AI-förslag som utkast, granskar tagg för tagg, och behåller bara det jag kan förklara.”*

---

Nästa: [05 — Självtest](./05-sjalvtest.md).
