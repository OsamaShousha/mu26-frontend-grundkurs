# 05 — Självtest

Svara **först** utan att titta på facit. Skriv i Docs/anteckningar — privat, för dig. Sikta på målsvar du kan *säga högt*.

Sedan: öppna facit och rätta dig.

---

## Frågor

1. Vad är skillnaden mellan Git och GitHub på en mening?
Git is a lokal version control tool for my code, GitHub is online website where i can share my code with others.
   
2. Vad är en **commit**?
 A Commit is a saved version of my code  with message  which decribes when, what changes changed.
 
3. Vad gör `git add` som `git commit` *inte* gör?
   git add is choosing which changed files will be include in the next commit.
   git commit saves those changes into Git history.

4. Du har committat men github.com är tomt. Vilket steg saknas — och varför räcker inte VS Code-Spara?
  git push is the stage which is missed, and it is not enough with VS storing because vs just storing in my PC and  we need to work together in big companies,
 so we need a place where we can see any changes happen and how did it and when.

5. Beskriv metoden när du tvekar: ska jag spara i Git nu?
   First i check for changes using git status then i have to use git commit to save code im     my git history then i use git add to add code to include the code in the next commit.
   
6. Varför ska commits visa **vem** som jobbat? (Exam 1)
Commit should show who worked so my teaacher, my base and my team  can see each person's contribution and ask the right person to explaini the changes.
  
7. Ni sitter två vid samma dator. Hur gör ni så båda syns?
We should switch Git user before each person's commit, or use separate accounts/computers. Writing both names only in the commit message is not enough for GitHub history.

8. Peka i *ditt* repo: nämn tre steg du körde (add/commit/push eller status) och **varför** — inte “AI sa åt mig”.
  git status to see if there any changes and in which file.
  after finsh working with code i use git add to chose the file for the next commit.
 then git commit -m "Add Masseage". to save changes in Git history.
 at last using git push to upload the code to GitHub.
---

## Facit

<details>
<summary>Visa facit (målsvar-nivå)</summary>

1. **Git** = historik/checkpoints på din dator. **GitHub** = kopian på nätet där andra och examinationen kan se den.  
2. En commit = sparad ögonblicksbild + meddelande — en punkt i historiken.  
3. **`add`** = välj vilka filer som ska med i *nästa* ögonblicksbild. **`commit`** = spara den bilden. Add laddar inte upp.  
4. **`git push`**. Spara i editorn = fil på disk, ingen GitHub-kopia.  
5. (1) Liten, begriplig ändring? (2) `git add` de filerna. (3) `git commit -m "…"` sedan `git push`.  
6. Exam 1: gemensamt repo där det ska synas att **alla** kodat — inte bara att zip:en “finns”.  
7. Skriv bådas namn i commit-meddelandet (den inloggade Git-användaren är annars ensam författare).  
8. Subjektivt — rimligt om du kopplar kommando → effekt. Fel om svaret bara är “AI skrev det” eller “jag klickade runt”.

</details>

---

## Klart för paketet?

Om dina svar ligger nära facit, övningarna är gjorda, och du kan peka i eget repo:

- [ ] Målsvar commit — egna ord, högt  
- [ ] Målsvar synlig medverkan — egna ord, högt  
- [ ] Målsvar metod — egna ord, högt  
- [ ] Add / commit / push pekade i ditt flöde  

Då har du landat Git-målet. Nästa paket: [03-css-box-model](../03-css-box-model/).
