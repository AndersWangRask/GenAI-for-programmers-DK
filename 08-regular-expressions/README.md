---
title: Øvelse 8 - Regular Expressions (Regex)
nav_order: 9
---

# Øvelse 8: Regular Expressions (Regex)

## Formål
At lære at bruge AI til at forstå, skrive og debugge regular expressions (regex), med fokus på at formulere effektive prompts for at opnå præcise og effektive regex-mønstre.

## Beskrivelse
I denne øvelse vil du lære at bruge AI til at hjælpe dig med at arbejde med regular expressions. Du vil øve dig i at formulere prompts, der resulterer i klare forklaringer af regex-mønstre, hjælp til at skrive nye regex'er, og assistance med at debugge og optimere eksisterende regex'er.

## Trin-for-trin guide

1. **Vælg en regex-opgave:**
   Start med en specifik opgave, der involverer regex. Det kan være at matche et bestemt mønster, validere input, eller udtrække information fra en tekst.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker at opnå med regex'en. Inkluder:
   - Det specifikke mønster eller den type data, du vil matche
   - Eventuelle edge cases eller specielle krav
   - Om du ønsker forklaringer på regex'ens forskellige dele
   - Hvilket programmeringssprog eller regex-motor du bruger (hvis relevant)

3. **Send prompten til AI'en**

4. **Gennemgå svaret:**
   - Er den foreslåede regex korrekt og effektiv?
   - Er forklaringen klar og forståelig?
   - Dækker løsningen alle de specificerede krav og edge cases?

5. **Iterér gennem dialog:**
   Hvis regex'en eller forklaringen ikke er helt tilfredsstillende:
   - Bed om uddybning af specifikke dele af regex'en
   - Præsenter eksempler på input, der ikke matches korrekt
   - Spørg om potentielle optimeringsmuligheder
   - Fortsæt dialogen indtil du har en regex, der opfylder dine behov

   Eksempel på iteration:
   "Tak for regex'en. Den fungerer godt for de fleste tilfælde, men den matcher ikke korrekt, når der er mellemrum i e-mailadressen før @-tegnet. Kan du justere den til at håndtere dette? Og kan du forklare, hvordan vi kan gøre den mere permissiv over for sjældne, men gyldige e-mailformater? Hvis du har brug for flere eksempler på edge cases, så sig til."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for arbejde med regular expressions:

1. **Forståelse af eksisterende regex:**
   "Kan du forklare, hvad følgende regex gør, og give eksempler på strenge, den vil matche og ikke matche? Forklar venligst hver del af udtrykket.

   ```
   ^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$
   ```
   Hvis der er nogen potentielle problemer eller begrænsninger ved denne regex, så nævn dem venligst."

2. **Skrivning af ny regex for e-mailvalidering:**
   "Kan du hjælpe mig med at skrive en regex til at validere e-mailadresser? Den skal opfylde følgende krav:
   - Tillad bogstaver, tal, punktummer, bindestreger og underscores i den lokale del (før @)
   - Kræv et @-symbol
   - Tillad bogstaver, tal og bindestreger i domænedelen (efter @)
   - Kræv mindst ét punktum i domænedelen
   - Tillad ikke to punktummer lige efter hinanden
   - Tillad ikke specialtegn som begyndelse eller slutning af hver del
   
   Giv venligst også nogle eksempler på gyldige og ugyldige e-mailadresser baseret på denne regex. Hvis du ser nogen potentielle problemer eller begrænsninger, så nævn dem gerne."

3. **Optimering af eksisterende regex:**
   "Jeg bruger følgende regex til at matche datoer i formatet DD-MM-YYYY, men den er ret langsom på store datasæt. Kan du hjælpe med at optimere den uden at ændre dens funktionalitet?

   ```
   ^(0[1-9]|[12][0-9]|3[01])-(0[1-9]|1[012])-(19|20)\d\d$
   ```
   Forklar venligst dine optimeringsforslag og hvordan de forbedrer ydeevnen. Hvis der er trade-offs mellem læsbarhed og ydeevne, så nævn dem gerne."

4. **Regex for kompleks tekstudtrækning:**
   "Jeg har brug for hjælp til at skrive en regex, der kan udtrække information fra en log-fil. Hver loglinje har følgende format:

   ```
   [TIMESTAMP] USER:username ACTION:action STATUS:status MESSAGE:arbitrary message text
   ```

   Timestamp er i formatet YYYY-MM-DD HH:MM:SS.
   Username, action, og status er enkeltord uden mellemrum.
   Message kan indeholde hvilken som helst tekst, inklusive mellemrum og specialtegn.

   Kan du lave en regex, der udtrækker hver del som en separat capture group? Giv også gerne et eksempel på, hvordan man kan bruge denne regex i Python til at parse en loglinje."

5. **Debuggning af regex:**
   "Jeg prøver at bruge følgende regex til at matche HTML-tags, men den fungerer ikke som forventet:

   ```
   <(.*?)>.*?</\1>
   ```

   Den skulle matche par af åbnings- og lukketags med deres indhold, men den matcher ikke korrekt når der er nestede tags. Kan du hjælpe med at identificere problemet og foreslå en løsning? Forklar venligst, hvorfor den oprindelige regex ikke virker for nestede tags, og hvordan din løsning adresserer dette problem."

## Tips
- Vær så specifik som muligt om dit regex-behov, inkluder eksempler på, hvad der skal matches og hvad der ikke skal.
- Hvis du arbejder med et specifikt programmeringssprog eller regex-motor, så nævn det, da syntaksen kan variere.
- Bed om forklaringer på komplekse dele af regex'en for at forbedre din forståelse.
- Overvej at bede om alternative tilgange, hvis det er relevant.
- Spørg om potentielle ydeevnemæssige implikationer for komplekse regex'er.
- Afslut med en opfordring til AI'en om at stille opklarende spørgsmål, hvis der er behov for mere kontekst om anvendelsen eller begrænsningerne.

## Udfordring
Vælg en af følgende regex-udfordringer, eller brug en fra dit eget arbejde:

1. Skriv en regex til at validere komplekse passwords (mindst 8 tegn, mindst ét stort bogstav, ét lille bogstav, ét tal og ét specialtegn).
2. Lav en regex til at udtrække alle URL'er fra en given tekst.
3. Skriv en regex til at validere og parse et komplekst datoformat (f.eks. "25th December 2023", "Dec 25, 2023", "2023-12-25").
4. Lav en regex til at matche og udtrække indholdet af særlige kommentarer i kildekode (f.eks. TODO, FIXME, eller NOTE kommentarer).
5. Skriv en regex til at validere og parse ISBN-numre (både 10- og 13-cifrede).

Brug AI'en til at hjælpe dig med at udvikle, teste og optimere din regex. Husk at bede om forklaringer og overvej edge cases.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan forbedrede AI'ens forklaringer din forståelse af regular expressions?
- Hvilke aspekter af regex-udvikling fandt du mest udfordrende, og hvordan hjalp AI'en med disse?
- Var der nogen overraskende eller kreative løsninger, som AI'en foreslog?
- Hvordan kan du integrere AI-assisteret regex-udvikling i dine fremtidige projekter?

Husk, at selvom AI kan være en stor hjælp til at udvikle og forstå regex'er, er det stadig vigtigt at udvikle en grundlæggende forståelse af regex-syntaks og -koncepter. AI'en bør bruges som et supplement til din egen viden, ikke som en erstatning for den.