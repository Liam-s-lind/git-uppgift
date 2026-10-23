# Git-uppgift

## 1. Versionshantering och vanlig filsparning

Versionshantering handlar om att hålla koll på hur ett projekt förändras över tid, så att man kan gå tillbaka till en tidigare sparad version om något blir fel. När jag trycker Ctrl + S sparas filen på datorn, men det skapas ingen commit i Git. Först när jag gör en commit tas en ögonblicksbild av det jag har lagt i staging, och till den skriver jag ett meddelande som förklarar vad jag har ändrat.

### Commits som frysta ögonblicksbilder

Man kan se en commit som ett fotografi av projektet precis så som det såg ut just då, och den blir kvar i historiken. Min första commit innehåller fortfarande alla tre TODO, trots att jag senare ersatte dem med riktiga funktioner. Det visar hur Git fungerar: nya ändringar skriver inte över gamla commits, utan de bevaras som de var. Tack vare det kan jag i efterhand bläddra bakåt och se hur projektet har vuxit fram steg för steg.

## 2. git status, git add och git commit

Jag använder git status när jag vill se vad som händer i projektet just nu: vilka filer som är nya, vilka jag har ändrat och vilka som redan är redo för nästa commit. Med git add bestämmer jag vad som ska vara med, för då läggs filens nuvarande innehåll i staging. När jag sedan kör git commit sparas det som ligger där i den lokala historiken, tillsammans med ett meddelande som beskriver vad jag har gjort.

### Arbetsyta, staging och commit

Arbetsytan är där jag faktiskt jobbar med filerna, lite som ett ark på skrivbordet. Staging fungerar som ett kuvert: med git add lägger jag ner den version jag vill spara, och när jag gör en commit arkiveras kuvertets innehåll som en ögonblicksbild. Om jag ändrar filen efter att jag har lagt den i kuvertet följer ändringen inte med automatiskt, så jag måste köra git add igen för att få med den senaste versionen. Får jag meddelandet no changes added to commit betyder det att jag har ändrat saker i arbetsytan, men att jag inte har lagt några ändringar i staging, så det finns inga förberedda ändringar att committa.

## 3. Det lokala repot, GitHub och git push

På min dator ligger arbetsmappen och det lokala Git-repot, och det är där jag gör ändringar och skapar commits. GitHub har ett eget repo på nätet, och är det publikt kan andra gå in och titta på det. När jag kör `git push` skickas mina lokala commits dit, så att historiken för grenen uppdateras på GitHub.

### De två minnesytorna och Everything up-to-date

Jag tänker mig det lokala repot som en arkivlåda hemma och repot på GitHub som en glasmonter där jag ställer ut historiken. En ny commit hamnar först i lådan på min dator, och när jag kör `git push` skickas en kopia till montern medan den finns kvar lokalt. Om jag bara har ändrat och sparat en fil, utan att lägga den i staging och committa, finns det inga nya commits att skicka. Då kan push svara med `Everything up-to-date`, fast filen i arbetsytan faktiskt har ändrats.

