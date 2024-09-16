# Øvelse 11: Design Patterns

## Formål
At lære at bruge AI til at forstå, implementere og anvende design patterns i softwareudvikling, med fokus på at formulere effektive prompts for at opnå praktisk og kontekstspecifik vejledning.

## Beskrivelse
I denne øvelse vil du lære at bruge AI til at hjælpe dig med at arbejde med design patterns. Du vil øve dig i at formulere prompts, der resulterer i klare forklaringer, praktiske implementeringseksempler og vejledning om, hvornår og hvordan man bedst anvender forskellige design patterns.

## Trin-for-trin guide

1. **Vælg et design pattern eller et designproblem:**
   Start med et specifikt design pattern, du vil lære mere om, eller et designproblem, du søger en løsning på.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker at lære eller opnå. Inkluder:
   - Navnet på design pattern (hvis kendt) eller en beskrivelse af problemet
   - Det programmeringssprog, du arbejder i
   - Eventuel kontekst eller specifikke krav til din situation
   - Om du ønsker en forklaring, implementeringseksempel eller anvendelsesscenarie

3. **Send prompten til AI'en**

4. **Gennemgå svaret:**
   - Er forklaringen klar og forståelig?
   - Er implementeringseksemplet relevant og korrekt?
   - Adresserer svaret dine specifikke behov eller kontekst?

5. **Iterér gennem dialog:**
   Hvis svaret ikke er helt tilfredsstillende:
   - Bed om yderligere forklaringer eller eksempler
   - Stil spørgsmål om specifikke aspekter af pattern'et
   - Diskuter alternative patterns eller tilgange
   - Fortsæt dialogen indtil du har en god forståelse og praktisk anvendelig viden

   Eksempel på iteration:
   "Tak for forklaringen af Observer pattern. Kan du give et konkret eksempel på, hvordan dette kunne implementeres i et real-time dashboard system? Specifikt er jeg interesseret i, hvordan man kan håndtere mange samtidige observers effektivt. Hvis du har nogle forslag til, hvordan man kunne kombinere dette med andre patterns for at forbedre skalerbarheden, vil jeg også gerne høre om det."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for arbejde med design patterns:

1. **Forstå et specifikt pattern:**
   "Kan du forklare Singleton pattern og give et eksempel på dets implementering i Python? Inkluder venligst information om:
   - Hvad problemet er, som dette pattern løser
   - Fordele og ulemper ved at bruge Singleton
   - Et kodeeksempel på en thread-safe implementation
   - Typiske use cases for Singleton
   - Eventuelle alternative patterns eller tilgange, der kunne bruges i stedet

   Hvis du har nogle tips til, hvordan man kan undgå almindelige faldgruber ved brug af Singleton, vil jeg også gerne høre dem."

2. **Vælge det rette pattern:**
   "Jeg arbejder på et system, der skal håndtere forskellige typer af dokumenter (f.eks. PDF, Word, Excel) og udføre forskellige operationer på dem (f.eks. åbne, redigere, gemme). Hvilke design patterns ville du anbefale til denne situation, og hvorfor? 

   Jeg er særligt interesseret i at opnå:
   - Nem tilføjelse af nye dokumenttyper
   - Mulighed for at tilføje nye operationer uden at ændre eksisterende kode
   - God separation of concerns

   Kan du give et overordnet design for dette system i C#, der demonstrerer brugen af de anbefalede patterns?"

3. **Implementere et komplekst pattern:**
   "Kan du guide mig gennem implementeringen af Model-View-ViewModel (MVVM) pattern i en TypeScript/React applikation? Jeg vil gerne have:
   - En overordnet forklaring af MVVM og dets fordele i en React-kontekst
   - Et kodeeksempel, der viser strukturen af Model, View og ViewModel
   - Forklaring på, hvordan data binding og commands kan implementeres
   - Tips til at holde ViewModels testbare
   - Eventuelle React-specifikke overvejelser eller best practices

   Hvis du kan inkludere et simpelt eksempel på en komponent, der bruger denne struktur, ville det være meget hjælpsomt."

4. **Refaktorering med patterns:**
   "Jeg har følgende Java-kode, der håndterer forskellige typer af betalingsmetoder i et e-commerce system. Koden bruger mange if-else statements og er svær at vedligeholde. Kan du hjælpe mig med at refaktorere den ved hjælp af passende design patterns?

   ```java
   public class PaymentProcessor {
       public void processPayment(String paymentMethod, double amount) {
           if (paymentMethod.equals("CreditCard")) {
               // Kreditkort logik
           } else if (paymentMethod.equals("PayPal")) {
               // PayPal logik
           } else if (paymentMethod.equals("BankTransfer")) {
               // Bankoverførsel logik
           } else {
               throw new IllegalArgumentException("Ukendt betalingsmetode");
           }
       }
   }
   ```

   Jeg vil gerne have en løsning, der gør det nemt at tilføje nye betalingsmetoder i fremtiden uden at ændre eksisterende kode. Forklar venligst dit valg af pattern(s) og giv et eksempel på den refaktorerede kode."

5. **Kombinere multiple patterns:**
   "Jeg udvikler et stort enterprise-system og overvejer at kombinere flere design patterns for at opnå en fleksibel og skalerbar arkitektur. Kan du forklare, hvordan man effektivt kan kombinere følgende patterns, og give et overordnet struktureksempel?

   - Repository Pattern (for data access)
   - Factory Pattern (for objekt creation)
   - Observer Pattern (for event handling)
   - Dependency Injection (for loose coupling)

   Jeg er særligt interesseret i:
   - Hvordan disse patterns komplementerer hinanden
   - Potentielle udfordringer ved at kombinere dem
   - Et overordnet kodeeksempel i C# der viser, hvordan de kan integreres
   - Best practices for at holde koden testbar og vedligeholdbar

   Hvis du har forslag til andre patterns, der kunne være nyttige i denne kontekst, hører jeg også gerne om dem."

## Tips
- Vær specifik om hvilket design pattern eller problem du arbejder med.
- Angiv det programmeringssprog, du bruger, da implementeringer kan variere.
- Bed om konkrete kodeeksempler, når det er relevant.
- Spørg om fordele, ulemper og typiske use cases for patterns.
- Overvej at bede om sammenligninger med lignende eller alternative patterns.
- Hvis du arbejder med et specifikt projekt, giv kontekst om dets krav og begrænsninger.
- Afslut med en opfordring til AI'en om at dele eventuelle ekstra indsigter eller best practices.

## Udfordring
Vælg en af følgende udfordringer eller brug en fra dit eget projekt:

1. Implementer en logger ved hjælp af Singleton pattern og overvej, hvordan du kan gøre den thread-safe.
2. Design en simpel game engine ved hjælp af Component pattern, der tillader nem tilføjelse af nye spilelementer.
3. Refaktorer en eksisterende kodebase til at bruge Strategy pattern for at håndtere forskellige algoritmer.
4. Implementer en simpel dokumenteditor, der bruger Command pattern til at håndtere undo/redo funktionalitet.
5. Design et notifikationssystem ved hjælp af Observer pattern, der kan skalere til mange subscribers.

Brug AI'en til at guide dig gennem processen, få forklaringer på designbeslutninger, og diskuter fordele og ulemper ved forskellige tilgange.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan forbedrede AI'ens forklaringer og eksempler din forståelse af design patterns?
- Var der nogen overraskende eller kreative anvendelser af patterns, som AI'en foreslog?
- Hvordan kan du integrere denne tilgang til at lære og anvende design patterns i dine fremtidige projekter?
- Hvilke fordele og potentielle faldgruber ser du ved at bruge AI til at guide designbeslutninger?

Husk, at mens AI kan være en uvurderlig ressource for at lære om og implementere design patterns, er det vigtigt at udvikle en dyb forståelse af principperne bag patterns og hvornår de bør anvendes. Brug AI'en som et værktøj til at supplere din læring og beslutningstagning, men stol også på din egen dømmekraft og erfaring i softwaredesign.