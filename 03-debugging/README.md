---
title: Øvelse 3 - Debugging
nav_order: 4
---

# Øvelse 3: Debugging

## Formål
At lære at bruge AI til at identificere, forklare og rette fejl i kode, med fokus på at formulere effektive prompts for debugging-assistance.

## Beskrivelse
I denne øvelse vil du lære at præsentere kode med fejl for AI'en og bede om hjælp til at identificere, forklare og rette disse fejl. Du vil øve dig i at formulere prompts, der giver dig præcis og brugbar debugging-assistance.

## Trin-for-trin guide

1. **Vælg et kodestykke med fejl:**
   Start med et overskueligt kodestykke, der indeholder en eller flere fejl. Dette kan være syntaksfejl, logiske fejl eller runtime-fejl.

2. **Formuler din prompt:**
   Beskriv problemet og hvad du har observeret. Inkluder:
   - Programmeringssproget
   - Beskrivelse af den forventede vs. faktiske opførsel
   - Eventuelle fejlmeddelelser du har modtaget
   - Hvad du allerede har prøvet (hvis relevant)

3. **Send prompten og den fejlbehæftede kode til AI'en**

4. **Gennemgå svaret:**
   - Har AI'en korrekt identificeret fejlen(e)?
   - Er forklaringen af fejlen(e) klar og forståelig?
   - Er den foreslåede løsning passende og komplet?

5. **Iterér gennem dialog:**
   Hvis svaret ikke fuldt ud løser problemet:
   - Bed om yderligere forklaringer på dele, du ikke forstår
   - Giv feedback på eventuelle aspekter af løsningen, der ikke virker
   - Stil opfølgende spørgsmål om potentielle konsekvenser af ændringerne
   - Fortsæt dialogen indtil problemet er fuldt ud løst og forstået

   Eksempel på iteration:
   "Tak for forklaringen og løsningsforslaget. Jeg har implementeret ændringen, men nu får jeg en ny fejl: 'IndexError: list index out of range'. Kan du hjælpe mig med at forstå, hvorfor dette sker, og hvordan jeg kan løse det? Hvis du har brug for mere information eller kontekst, så spørg endelig."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for debugging:

1. **Syntaksfejl:**
   "Jeg får en syntaksfejl i følgende Python-kode. Kan du hjælpe mig med at identificere og rette fejlen?

   ```python
   def calculate_average(numbers)
       total = sum(numbers)
       count = len(numbers)
       average = total / count
       return average

   result = calculate_average([1, 2, 3, 4, 5])
   print(f'Gennemsnittet er: {result}')
   ```
   Fejlmeddelelsen siger 'SyntaxError: invalid syntax', men jeg kan ikke se, hvor fejlen er. Kan du forklare, hvad der er galt, og hvordan jeg kan rette det? Hvis du ser andre potentielle problemer, må du også gerne nævne dem."

2. **Logisk fejl:**
   "Følgende JavaScript-funktion skal tælle antallet af forekomster af hvert element i et array, men den giver ikke det korrekte resultat. Kan du hjælpe mig med at finde og rette fejlen?

   ```javascript
   function countOccurrences(arr) {
       let counts = {};
       for (let i = 0; i < arr.length; i++) {
           if (counts[arr[i]]) {
               counts[arr[i]] += 1;
           } else {
               counts[arr[i]] = 1;
           }
       }
       return counts;
   }

   console.log(countOccurrences(['a', 'b', 'a', 'c', 'b', 'a']));
   // Forventet output: { a: 3, b: 2, c: 1 }
   // Faktisk output: { a: 1, b: 1, c: 1 }
   ```
   Kan du forklare, hvorfor funktionen ikke tæller korrekt, og hvordan jeg kan rette den? Hvis du har forslag til, hvordan jeg kan gøre koden mere effektiv eller læsbar, så del dem gerne."

3. **Runtime-fejl:**
   "Jeg får en runtime-fejl, når jeg kører følgende Java-kode. Kan du hjælpe mig med at identificere problemet og foreslå en løsning?

   ```java
   public class DivideNumbers {
       public static void main(String[] args) {
           int[] numbers = {10, 5, 2, 0, 8};
           for (int i = 0; i < numbers.length; i++) {
               int result = 100 / numbers[i];
               System.out.println("100 divideret med " + numbers[i] + " er " + result);
           }
       }
   }
   ```
   Jeg får en 'ArithmeticException: / by zero' fejl. Hvordan kan jeg ændre koden for at håndtere denne situation på en robust måde? Forklar venligst også, hvorfor fejlen opstår, og hvordan din foreslåede løsning forebygger den."

4. **Uventet output:**
   "Denne C#-kode skulle fjerne duplikater fra en liste af tal, men den ser ud til at fjerne alle elementer. Kan du hjælpe mig med at finde fejlen og rette den?

   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;

   class Program
   {
       static void Main()
       {
           List<int> numbers = new List<int> { 1, 2, 3, 2, 4, 3, 5 };
           List<int> uniqueNumbers = RemoveDuplicates(numbers);
           Console.WriteLine(string.Join(", ", uniqueNumbers));
       }

       static List<int> RemoveDuplicates(List<int> list)
       {
           return list.Where(x => list.IndexOf(x) == list.LastIndexOf(x)).ToList();
       }
   }
   ```
   Det forventede output er '1, 2, 3, 4, 5', men listen er tom. Hvad er galt med min RemoveDuplicates-metode, og hvordan kan jeg fikse den? Hvis du har en mere effektiv måde at fjerne duplikater på, så del den gerne."

5. **Performanceoptimering:**
   "Følgende Python-funktion til at finde primtal er korrekt, men meget langsom for store tal. Kan du hjælpe mig med at optimere den?

   ```python
   def is_prime(n):
       if n < 2:
           return False
       for i in range(2, n):
           if n % i == 0:
               return False
       return True

   def find_primes(limit):
       return [num for num in range(2, limit + 1) if is_prime(num)]

   print(find_primes(10000))  # Dette tager lang tid at køre
   ```
   Kan du forklare, hvorfor denne implementering er ineffektiv, og foreslå måder at forbedre dens ydeevne på? Giv gerne en optimeret version af koden sammen med en forklaring af de anvendte optimeringsteknikker."

## Tips
- Vær så specifik som muligt om den fejl, du oplever.
- Inkluder relevante fejlmeddelelser eller stack traces.
- Beskriv, hvad du allerede har prøvet for at løse problemet.
- Hvis problemet kun opstår under bestemte forhold, så beskriv disse.
- Vær åben for at AI'en måske finder andre problemer end det, du oprindeligt spurgte om.
- Afslut med en opfordring til AI'en om at stille opklarende spørgsmål, hvis der er behov for mere kontekst.

## Udfordring
Tag et stykke kode fra et af dine egne projekter, der indeholder en fejl, du har svært ved at løse. Præsenter det for AI'en og arbejd dig gennem debugging-processen. Prøv at formulere dine prompts så præcist som muligt, og engager dig i en dialog med AI'en for at nå frem til en løsning.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan hjalp AI'en dig med at identificere og løse fejlen?
- Var der aspekter af fejlfindingen, hvor AI'en var særligt nyttig?
- Var der situationer, hvor AI'ens forslag ikke var helt korrekte eller komplette?
- Hvordan kan du integrere AI-assisteret debugging i din normale arbejdsgang?

Husk, at AI er et kraftfuldt værktøj til debugging, men det erstatter ikke din egen kritiske tænkning og erfaring. Brug AI'en som en samarbejdspartner i fejlfindingsprocessen, men vær altid klar til at evaluere og teste de foreslåede løsninger.