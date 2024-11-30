---
title: Praktisk projekt - Konverter Markdown til HTML
nav_order: 18
---

# Praktisk Projekt: Markdown til HTML Konverter

## Projektbeskrivelse
I dette projekt skal du udvikle et command line værktøj, der kan konvertere Markdown-filer til HTML ved hjælp af AI-assisteret programmering. Dette projekt giver dig mulighed for at øve dig i at bruge AI til at udvikle et komplet, funktionelt program fra bunden. 

Du kan læse mere om Markdown-formatet i bunden af denne fil.

## Projektkrav
- Læs en Markdown-fil fra en sti angivet som command line argument
- Konverter indholdet til HTML
- Gem den konverterede HTML i en ny fil
- Håndter grundlæggende Markdown-syntaks (overskrifter, links, lister, etc.)
- Implementer fejlhåndtering for almindelige scenarier (f.eks. fil ikke fundet)

## Valgfri udvidelser
- Understøttelse af mere avanceret Markdown-syntaks (tabeller, kodeblokke med syntaksfremhævning)
- Mulighed for at specificere output-filnavn og -sti
- Batch-konvertering af flere filer
- Inkludering af et simpelt CSS-stylesheet i output HTML

## Start-prompt og dialog med AI

For at komme i gang med projektet, kan du bruge følgende prompt som udgangspunkt for en dialog med AI'en:

```
Lav et command line værktøj, der kan konvertere Markdown-format til HTML. Det skal tage stien til en input Markdown-fil og konvertere denne til en HTML-fil. Brug det programmeringssprog, du føler dig mest komfortabel med. Hvis vi kan drage fordel af at bruge eksterne pakker eller biblioteker, så foreslå venligst, hvilke vi kan bruge. Hvis du har nogen spørgsmål om dette, så stil dem venligst nu, før du genererer nogen kode.
```

Denne prompt er designet til at give AI'en mulighed for at stille afklarende spørgsmål. Vær forberedt på at svare på spørgsmål om:

- Dit foretrukne programmeringssprog
- Specifikke Markdown-funktioner, du ønsker understøttet
- Hvordan output-filen skal navngives
- Eventuelle yderligere funktioner, du måtte ønske

Efter AI'en har stillet sine spørgsmål og du har besvaret dem, vil den sandsynligvis foreslå en overordnet struktur og måske nogle kodestumper. På dette tidspunkt kan du fortsætte dialogen ved at stille spørgsmål som:

1. "Kan du uddybe, hvordan vi kan implementere [specifik funktion]?"
2. "Hvordan kan vi håndtere fejl, hvis input-filen ikke findes eller ikke er læsbar?"
3. "Kan du give et eksempel på, hvordan vi kan teste dette program?"
4. "Hvilke yderligere funktioner ville du foreslå at tilføje for at gøre dette værktøj mere robust eller brugervenligt?"

Husk, at udvikling med AI er en iterativ proces. Vær ikke bange for at bede om forklaringer, foreslå ændringer, eller bede om alternative tilgange, hvis du ikke er tilfreds med det første forslag.

## Tips til AI-assisteret udvikling
1. Vær specifik i dine prompts, men giv plads til at AI'en kan komme med forslag og stille spørgsmål.
2. Når AI'en genererer kode, gennemgå den grundigt og stil spørgsmål om dele, du ikke forstår.
3. Bed AI'en om at forklare designbeslutninger og eventuelle trade-offs.
4. Brug AI'en til at hjælpe med at identificere potentielle problemer eller begrænsninger i koden.
5. Når du støder på fejl eller uventede resultater, beskriv problemet detaljeret for AI'en og bed om hjælp til fejlfinding.

## Udfordring
Når du har en fungerende grundlæggende konverter, prøv at bruge AI til at hjælpe dig med at implementere en eller flere af de valgfrie udvidelser. For eksempel:

"Nu hvor vi har en grundlæggende Markdown til HTML konverter, hvordan kan vi udvide den til at inkludere et simpelt CSS-stylesheet i output HTML'en? Kan du foreslå en måde at gøre dette på og give et eksempel på, hvordan koden kunne se ud?"

## Refleksion og læring
Efter at have afsluttet projektet, tag dig tid til at reflektere over processen:
- Hvordan hjalp AI'en dig med at tackle udfordringer, du stødte på?
- Var der nogen overraskende eller særligt nyttige forslag fra AI'en?
- Hvordan adskilte denne proces sig fra din normale måde at udvikle software på?
- Hvilke aspekter af AI-assisteret udvikling fandt du mest værdifulde?

## Deling af din løsning
Når du har implementeret din Markdown til HTML konverter, er du velkommen til at dele din løsning og dine erfaringer. Inkluder gerne:
- En kort beskrivelse af din implementering
- Eventuelle udfordringer du stødte på, og hvordan AI hjalp dig med at overvinde dem
- Eksempler på særligt interessante eller nyttige interaktioner med AI'en
- Refleksioner over, hvad du har lært om AI-assisteret programmering gennem dette projekt

God fornøjelse med projektet, og husk at nyde processen med at udforske mulighederne ved AI-assisteret udvikling!

## Om Markdown
Markdown er et let-at-læse og let-at-skrive tekstformat, der kan konverteres til HTML. Det blev skabt af John Gruber og Aaron Swartz i 2004 med målet om at gøre det så enkelt som muligt at formatere tekst, samtidig med at det forbliver læsbart i sin rå form. Markdown bruges bredt på platforme som GitHub, Reddit, og mange dokumentationsværktøjer.

Du kan lære mere om Markdown på [den officielle Markdown hjemmeside](https://daringfireball.net/projects/markdown/) eller i [GitHub's Markdown guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).