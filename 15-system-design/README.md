---
title: Øvelse 15 - Systemdesign
nav_order: 16
---

# Øvelse 15: Systemdesign

## Formål
At lære at bruge AI til at assistere i designprocessen for komplekse softwaresystemer, med fokus på at formulere effektive prompts for at opnå omfattende, skalerbare og robuste systemarkitekturer.

## Beskrivelse
I denne øvelse vil du lære at bruge AI til at hjælpe dig med at designe og planlægge implementeringen af større softwaresystemer. Du vil øve dig i at formulere prompts, der resulterer i detaljerede systemdesigns, arkitekturforslag, og vejledning om bedste praksis for at opbygge skalerbare og vedligeholdbare systemer.

## Trin-for-trin guide

1. **Vælg et systemdesign-scenarie:**
   Start med et komplekst scenarie, der kræver design af et omfattende softwaresystem.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker at designe. Inkluder:
   - En detaljeret beskrivelse af systemets formål og krav
   - Forventede skaleringsbehov og ydeevnekrav
   - Eventuelle specifikke teknologier eller begrænsninger
   - Områder du er særligt interesseret i (f.eks. datamodellering, API-design, skalerbarhed)

3. **Send prompten til AI'en**

4. **Gennemgå svaret:**
   - Er det foreslåede design omfattende og dækker alle aspekter af systemet?
   - Adresserer designet de specificerede krav og begrænsninger?
   - Er forklaringerne af arkitekturvalg klare og velbegrundede?

5. **Iterér gennem dialog:**
   Hvis designforslaget ikke er helt tilfredsstillende:
   - Bed om uddybning af specifikke dele af arkitekturen
   - Stil spørgsmål om, hvordan designet håndterer specifikke udfordringer eller scenarier
   - Anmod om alternative tilgange eller trade-offs
   - Fortsæt dialogen indtil du har et grundigt og praktisk anvendeligt systemdesign

   Eksempel på iteration:
   "Tak for systemdesignet. Kan du uddybe, hvordan den foreslåede mikroservice-arkitektur vil håndtere datakonsistens på tværs af tjenester? Jeg er også interesseret i at vide, hvordan dette design skalerer under høj belastning, og hvilke overvejelser vi bør gøre os omkring fejltolerance og disaster recovery. Hvis du har konkrete forslag til implementeringsteknologier eller værktøjer, der understøtter dette design, vil jeg gerne høre om dem."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for systemdesign:

1. **E-commerce platform:**
   "Jeg skal designe en skalerbar e-commerce platform, der kan håndtere følgende krav:
   - Understøtte millioner af produkter og brugere
   - Håndtere spidsbelastninger under salgskampagner
   - Implementere et realtids inventarsystem
   - Sikre hurtig søgning og filtrering af produkter
   - Integrere med forskellige betalingsgateways
   - Implementere personaliserede produktanbefalinger

   Kan du foreslå en overordnet systemarkitektur for denne platform? Inkluder venligst:
   - En høj-niveau arkitekturoversigt
   - Forslag til nøglekomponenter og deres interaktioner
   - Strategier for at sikre skalerbarhed og ydeevne
   - Overvejelser omkring datamodellering og databasevalg
   - Sikkerhedsovervejelser for bruger- og betalingsdata

   Forklar venligst dine valg og eventuelle trade-offs i dit foreslåede design."

2. **Streaming-tjeneste:**
   "Jeg er ved at designe en videostreamingplatform i stil med Netflix. Systemet skal kunne:
   - Streame video til millioner af samtidige brugere
   - Håndtere globalt distribueret indhold
   - Implementere effektiv caching og CDN-integration
   - Understøtte personaliserede anbefalinger
   - Håndtere forskellige enheder og netværkskvaliteter
   - Implementere robust DRM (Digital Rights Management)

   Kan du foreslå en arkitektur for dette system? Jeg er særligt interesseret i:
   - Overordnet systemarkitektur
   - Strategier for effektiv indholdslevering
   - Skalerbarhedsovervejelser for backend-systemer
   - Datamodellering for brugerdata, indhold og anbefalinger
   - Sikkerhedsaspekter, især omkring DRM

   Giv venligst en detaljeret beskrivelse af arkitekturen og forklar, hvordan den adresserer hver af de ovennævnte krav."

3. **IoT-platform:**
   "Jeg skal designe en IoT-platform til smart home-enheder med følgende krav:
   - Understøtte millioner af tilsluttede enheder
   - Håndtere realtidsdata fra sensorer
   - Implementere robust enhedsautentificering og -autorisation
   - Muliggøre fjernkontrol af enheder
   - Udføre dataanalyse og maskinlæring på indsamlede data
   - Sikre lav latens for kritiske kommandoer

   Kan du foreslå en systemarkitektur for denne IoT-platform? Inkluder venligst:
   - Overordnet arkitekturdiagram
   - Valg af protokoller for enhedskommunikation
   - Strategier for dataindsamling og -behandling
   - Sikkerhedsovervejelser for enhedsautentificering og datakryptering
   - Skaleringsstrategier for at håndtere voksende antal enheder
   - Forslag til implementering af dataanalyse og maskinlæring

   Forklar rationalet bag dine arkitekturvalg og eventuelle udfordringer, der skal overvejes."

4. **Socialt netværk:**
   "Jeg planlægger at udvikle et nyt socialt netværk med fokus på privatliv og brugerkontrol. Platformen skal kunne:
   - Håndtere millioner af aktive brugere
   - Implementere komplekse privatlivsindstillinger for deling af indhold
   - Understøtte realtids-chat og notifikationer
   - Implementere et nyhedsfeed med personaliseret indhold
   - Håndtere upload og deling af forskellige medietyper (billeder, videoer, etc.)
   - Sikre robust moderering af indhold

   Kan du foreslå en systemarkitektur for denne platform? Jeg er særligt interesseret i:
   - Overordnet systemdesign
   - Datamodellering for brugerrelationer og indholdssynlighed
   - Strategier for effektiv implementering af nyhedsfeed
   - Arkitektur for realtids-funktionalitet
   - Skalerbarhedsovervejelser for brugergeneret indhold
   - Sikkerhedsaspekter, især omkring databeskyttelse og privatliv

   Giv venligst en detaljeret beskrivelse af den foreslåede arkitektur og forklar, hvordan den adresserer hver af de ovennævnte krav."

5. **Distribueret database:**
   "Jeg skal designe en højt skalerbar, distribueret database, der kan håndtere følgende krav:
   - Understøtte globalt distribuerede læse- og skriveoperation
   - Implementere stærk konsistens for kritiske data
   - Tilbyde justerbar konsistens for ikke-kritiske data
   - Håndtere automatisk sharding og rebalancering af data
   - Implementere robuste fejltolerancemekanismer
   - Understøtte komplekse forespørgsler og transaktioner

   Kan du foreslå en arkitektur for dette databasesystem? Inkluder venligst:
   - Overordnet systemdesign
   - Strategier for data partitionering og replikering
   - Mekanismer for at sikre datakonsistens
   - Fejltolerancestrategier
   - Skaleringsmekanismer for at håndtere voksende datamængder og forespørgselsbelastning
   - Overvejelser omkring ydeevne og latens

   Forklar venligst dine arkitekturvalg og hvordan de adresserer de specificerede krav. Hvis du har forslag til specifikke teknologier eller algoritmer, der kunne være nyttige i implementeringen, så del dem gerne."

## Tips
- Vær så detaljeret som muligt i din beskrivelse af systemkravene og forventede use cases.
- Inkluder information om forventet skala (f.eks. antal brugere, datamængde) og ydeevnekrav.
- Bed om forklaringer på arkitekturvalg og trade-offs.
- Spørg om, hvordan det foreslåede design håndterer specifikke udfordringer (f.eks. skalerbarhed, fejltolerance).
- Overvej at bede om alternative tilgange eller sammenligninger mellem forskellige arkitekturer.
- Hvis relevant, bed om vejledning i valg af specifikke teknologier eller implementeringsstrategier.
- Afslut med en opfordring til AI'en om at dele eventuelle yderligere overvejelser eller best practices for den type system, du designer.

## Udfordring
Vælg en af følgende udfordringer eller brug en fra dit eget projekt:

1. Design et globalt distribueret fildelingssystem med fokus på høj tilgængelighed og lave latenstider.
2. Arkitektur en realtids-samarbejdsplatform (som Google Docs) med understøttelse af samtidig redigering og versionsstyring.
3. Design et skalerbart mikroservice-baseret backend-system for en mobil-app med millioner af brugere.
4. Skitser arkitekturen for et cloud-baseret continuous integration/continuous deployment (CI/CD) system.
5. Design en højt skalerbar og fejltolerant betalingsplatform, der kan håndtere globale transaktioner.

Brug AI'en til at guide dig gennem designprocessen, få forklaringer på arkitekturvalg, og diskuter fordele og ulemper ved forskellige tilgange.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan hjalp AI'en dig med at overveje aspekter af systemdesignet, du måske ikke selv havde tænkt på?
- Hvilke dele af systemdesignprocessen fandt du mest udfordrende, og hvordan assisterede AI'en med disse?
- Hvordan kan du integrere AI-assisteret systemdesign i dine fremtidige projekter?
- Hvilke begrænsninger eller potentielle risici ser du ved at stole på AI til systemdesign?

Husk, at mens AI kan give værdifuld indsigt og forslag til systemdesign, er det vigtigt at kombinere dette med din egen erfaring og domæneviden. AI bør ses som et værktøj til at supplere og udvide din egen designproces, ikke som en erstatning for grundig analyse og overvejelse.