---
title: Praktisk projekt - UML til Mermaid til SQL skema til C# Entity Framework klasser
nav_order: 22
---

# Praktisk Projekt: Multimodal UML-Analyse og Implementering

## Projektbeskrivelse
I dette avancerede projekt vil du udforske AI'ens multimodale kapaciteter ved at arbejde med et UML-diagram gennem forskellige repræsentationer og implementeringer. Du vil bruge AI til at analysere et visuelt UML-diagram, konvertere det til forskellige formater, og generere både databaseskemaer og programmeringskode baseret på diagrammet.

## Formål
- Demonstrere AI'ens evne til at forstå og arbejde med visuelle diagrammer
- Øve dig i at formulere effektive prompts for forskellige typer opgaver
- Få praktisk erfaring med at bruge AI til forskellige aspekter af softwaredesign og -udvikling
- Udforske sammenhængen mellem UML, databasedesign og objektorienteret programmering

## Materialer
- Adgang til en AI, der kan analysere billeder (f.eks. ChatGPT-4 med billedanalyse)
- Et UML-klassediagram (du kan finde et online eller bruge et fra et tidligere projekt)

*Du kan f.eks. bruge dette UML-diagram:*
![Eksempel UML Diagram](https://miro.medium.com/v2/resize:fit:2532/1*Srh6QviwDT6LFFdSnyzelA.png)

## Projektkrav

1. Billedanalyse og forklaring:
   - Upload et UML-klassediagram til AI'en
   - Få AI'en til at forklare diagrammet i detaljer

2. Mermaid-konvertering:
   - Bed AI'en om at genskabe UML-diagrammet ved hjælp af Mermaid-syntaks

3. SQL-skriptgenerering:
   - Få AI'en til at generere et T-SQL-script (eller et script til et andet databasesystem efter eget valg) for at oprette et databaseskema baseret på UML-diagrammet

4. Kodegenerering:
   - Bed AI'en om at generere klasser i dit foretrukne programmeringssprog, der svarer til UML-diagrammet
   - Hvis du bruger C#, bed om klasser forberedt til brug med Entity Framework. For andre sprog, bed om tilsvarende ORM-forberedelse

## Trin-for-trin guide

1. UML-diagramanalyse:
   - Upload dit valgte UML-klassediagram til AI'en
   - Prompt: "Kan du forklare dette UML-klassediagram i detaljer? Beskriv hver klasse, deres attributter, metoder og relationerne mellem klasserne."

2. Mermaid-konvertering:
   - Prompt: "Kan du genskabe dette UML-diagram ved hjælp af Mermaid-syntaks? Sørg for at inkludere alle klasser, attributter, metoder og relationer fra det originale diagram."

3. SQL-skriptgenerering:
   - Prompt: "Baseret på dette UML-diagram, kan du generere et T-SQL-script til at oprette et tilsvarende databaseskema i Microsoft SQL Server? Inkluder passende datatyper, primærnøgler, fremmednøgler og eventuelle nødvendige indeks."

4. Kodegenerering:
   - Prompt: "Kan du generere C#-klasser baseret på dette UML-diagram? Klasserne skal være forberedt til brug med Entity Framework, inklusive nødvendige attributter og navigationsproperties. Sørg for at følge C# konventioner og best practices."

## Tips til effektiv promptning

- Vær specifik om, hvilke detaljer du ønsker inkluderet i hver output
- Hvis AI'en udelader noget, bed om uddybning eller tilføjelser
- Ved komplekse diagrammer, overvej at dele opgaven op i mindre dele
- Bed om forklaringer på designbeslutninger, især for SQL-skemaet og kodegenerering

## Udfordringer og udvidelser

- Bed AI'en om at foreslå forbedringer eller alternative designs til UML-diagrammet
- Få AI'en til at generere unit tests for de genererede klasser
- Bed om implementering af et simpelt API baseret på de genererede klasser
- Eksperimenter med forskellige UML-diagrammer og sammenlign AI'ens output

## Refleksionsspørgsmål

Efter at have gennemført projektet, overvej følgende:

1. Hvor præcist forstod AI'en det visuelle UML-diagram?
2. Hvilke fordele og begrænsninger oplevede du ved at bruge AI til denne type opgave?
3. Hvordan håndterede AI'en overgangen mellem forskellige repræsentationer (visuelt diagram, Mermaid, SQL, kode)?
4. Hvilke dele af processen fandt du mest værdifulde eller overraskende?
5. Hvordan kunne denne tilgang integreres i en reel softwareudviklingsproces?

## Deling af din løsning

Når du har gennemført projektet, er du velkommen til at dele din erfaring og resultater. Inkluder gerne:

- Det originale UML-diagram
- AI'ens forklaring af diagrammet
- Den genererede Mermaid-kode og et billede af det resulterende diagram
- Det genererede SQL-script
- Eksempler på de genererede klasser
- Dine refleksioner over processen og resultaterne

Din deling kan hjælpe andre med at lære af din erfaring og give indsigt i styrker og begrænsninger ved at bruge AI til softwaredesign og -udvikling.

God fornøjelse med projektet! Dette er en spændende mulighed for at udforske, hvordan AI kan assistere i forskellige faser af softwareudvikling, fra design til implementation. Nyd processen og vær åben for de indsigter og muligheder, der kan opstå undervejs.