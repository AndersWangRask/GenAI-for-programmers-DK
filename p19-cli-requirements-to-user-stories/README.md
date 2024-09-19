---
title: Praktisk projekt - Markdown kravdokument til User Stories
nav_order: 21
---

# Praktisk Projekt: AI-Drevet Kravanalyse og User Story Generator

## Disclaimer
Dette er et eksempelprojekt designet til at demonstrere potentialet i AI-assisteret programmering. Det er ikke tiltænkt som et produktionsklart system, men som en læringsoplevelse, der viser, hvordan AI kan anvendes i softwareudviklingsprocesser. Projektet er bevidst ambitiøst og komplekst for at illustrere, hvor hurtigt man kan opbygge et skelet til avancerede systemer ved hjælp af AI.

## Projektbeskrivelse
I dette avancerede projekt skal du udvikle et command line værktøj, der bruger AI til at analysere et kravdokument i Markdown-format, generere user stories baseret på analysen, og derefter oprette disse stories i et projektstyringsværktøj. Dette projekt demonstrerer kraften i AI-assisteret programmering ved at tackle en kompleks, multi-facetteret opgave.

## Projektkrav
### Basis implementering:
- Læs et Markdown-dokument med kravspecifikationer fra en given filsti
- Send hele dokumentets indhold til en AI-tjeneste for analyse
- Modtag og parse AI-genererede user stories
- Outputte de genererede user stories til konsollen eller en fil

### AI-integration:
- Brug OpenAI API (eller lignende) til at analysere hele kravdokumentet
- Instruer AI'en i at generere strukturerede user stories med klare separatorer (f.eks. "---" mellem hver story)
- Parse AI'ens respons for at udtrække individuelle user stories

### Projektstyringsintegration:
- Integrer med GitHub API eller Azure DevOps API
- Opret de genererede user stories som issues eller work items i det valgte projektstyringsværktøj

### Avancerede features (valgfrie):
- Implementer prioritering af user stories baseret på AI-analyse
- Tilføj estimering af kompleksitet eller arbejdsmængde for hver user story
- Generer acceptance kriterier for hver user story

## Valgfri udvidelser
- Tilføj support for at analysere multiple kravdokumenter på én gang
- Implementer en funktion til at generere et mock kravdokument ved hjælp af AI
- Tilføj mulighed for at opdatere eksisterende user stories baseret på ændringer i kravdokumentet
- Implementer en simpel GUI for værktøjet

## Start-prompt og dialog med AI

Brug følgende prompt som udgangspunkt for en dialog med AI'en:

```
Udvikl et command line værktøj, der kan analysere et Markdown-dokument med softwarekrav, bruge AI til at generere user stories baseret på disse krav, og derefter oprette disse stories i et projektstyringsværktøj (f.eks. GitHub eller Azure DevOps). Programmet skal sende hele kravdokumentet til AI'en for analyse og bede om strukturerede user stories som output. Brug det programmeringssprog, du foretrækker. Du skal integrere med en AI API (som OpenAI) og et projektstyringsværktøjs API. Hvis du har nogen spørgsmål om projektets krav eller specifikationer, så stil dem venligst nu, før du begynder at generere kode.
```

Vær forberedt på, at AI'en kan stille opklarende spørgsmål om:

- Dit foretrukne programmeringssprog
- Hvilket AI API og projektstyringsværktøj du vil bruge
- Specifikke ønsker til formatet af de genererede user stories
- Hvordan du ønsker at håndtere API-begrænsninger og fejl

Efter AI'en har stillet sine spørgsmål og du har besvaret dem, vil den sandsynligvis foreslå en overordnet struktur og nogle kodestumper. Du kan fortsætte dialogen ved at stille spørgsmål som:

1. "Hvordan kan vi strukturere vores anmodning til AI'en for at få klart adskilte user stories tilbage?"
2. "Kan du give et eksempel på, hvordan vi kan parse AI'ens respons for at udtrække individuelle user stories?"
3. "Hvordan håndterer vi autentificering og sikker opbevaring af API-nøgler for både AI API'en og projektstyringsværktøjet?"
4. "Kan du foreslå en strategi for at håndtere fejl og begrænsninger i API-kald, især hvis kravdokumentet er meget stort?"

## Tips til AI-assisteret udvikling
1. Bed AI'en om at forklare komplekse koncepter eller API-integrationer trin for trin.
2. Når du arbejder med AI-analyse af tekst, eksperimenter med forskellige promptformater for at se, hvilke der giver de bedste resultater.
3. Brug AI'en til at hjælpe med at generere testkravdokumenter og mockdata.
4. Bed om hjælp til at strukturere din kode på en måde, der gør den let at udvide med nye features senere.

## Implementeringsguide
For at håndtere projektets kompleksitet, overvej at implementere det i faser:

1. Fase 1: Dokument Indlæsning og AI-Analyse
   - Implementer indlæsning af Markdown-dokumentet
   - Sæt OpenAI API integration op
   - Send hele dokumentets indhold til AI for analyse
   - Modtag og gem AI-genererede user stories

2. Fase 2: Parsing af AI-Output
   - Implementer parsing af AI'ens respons
   - Udtræk individuelle user stories baseret på definerede separatorer
   - Strukturer user stories i et anvendeligt format

3. Fase 3: Projektstyringsintegration
   - Implementer integration med valgt projektstyringsværktøj (GitHub/Azure DevOps)
   - Opret genererede user stories som issues/work items

4. Fase 4: Avancerede Features
   - Tilføj prioritering og estimering af user stories
   - Generer acceptance kriterier
   - Implementer eventuelle valgfrie udvidelser

## Udfordring
Når du har en fungerende version af værktøjet, prøv at bruge det på et rigtigt eller AI-genereret softwareprojekt. Analyser resultaterne og overvej:

"Hvordan kan vi forbedre vores prompt til AI'en for at generere endnu mere præcise og brugbare user stories? Kan vi tilføje funktionalitet til at lære fra feedback og iterativt forbedre output over tid?"

## Refleksion og læring
Efter at have afsluttet projektet, overvej følgende:
- Hvordan ændrede dette projekt din opfattelse af, hvad der er muligt med AI-assisteret programmering?
- Hvilke udfordringer stødte du på ved at integrere forskellige API'er og systemer, og hvordan hjalp AI dig med at overkomme dem?
- Hvordan påvirkede brugen af AI din tilgang til problemløsning i et komplekst projekt som dette?
- Hvilke nye færdigheder eller indsigter har du opnået om AI, API-integration og softwareudviklingsprocesser?

## Deling af din løsning
Når du har implementeret din AI-drevne kravanalysator og user story generator, er du meget velkommen til at dele din løsning og erfaringer. Inkluder gerne:
- En detaljeret beskrivelse af din implementering, herunder valg af teknologier og API'er
- Eksempler på input kravdokumenter og de resulterende user stories
- Udfordringer du stødte på, særligt med AI-integration og API-håndtering, og hvordan du løste dem
- Eksempler på særligt interessante eller overraskende resultater fra AI-analysen
- Dine tanker om potentialet for denne type værktøj i softwareudviklingsprocesser

God fornøjelse med projektet! Dette er en enestående mulighed for at udforske grænsefladen mellem traditionel softwareudvikling, AI-assisteret programmering og moderne projektstyringsværktøjer. Nyd processen og vær ikke bange for at eksperimentere og lære undervejs!