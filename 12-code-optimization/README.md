---
title: Øvelse 12 - Kodeoptimering
nav_order: 14
---

# Øvelse 12: Kodeoptimering

## Formål
At lære at bruge AI til at identificere, analysere og implementere optimeringsmuligheder i kode, med fokus på at formulere effektive prompts for at opnå forbedringer i ydeevne, hukommelsesforbrug og kodekvalitet.

## Beskrivelse
I denne øvelse vil du lære at bruge AI til at hjælpe dig med at optimere kode. Du vil øve dig i at formulere prompts, der resulterer i praktiske forslag til optimering, detaljerede forklaringer af optimeringsteknikker og vejledning om, hvordan man afvejer forskellige optimeringsmuligheder.

## Trin-for-trin guide

1. **Vælg et kodestykke til optimering:**
   Start med et specifikt kodestykke, som du mener kan optimeres. Det kan være en funktion, en klasse eller et helt modul.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker at optimere. Inkluder:
   - Koden der skal optimeres
   - Hvilket programmeringssprog der bruges
   - Specifikke områder du vil fokusere på (f.eks. ydeevne, hukommelsesforbrug, læsbarhed)
   - Eventuelle begrænsninger eller krav (f.eks. bagudkompatibilitet, målplatform)
   - Om du ønsker forklaringer på de foreslåede optimeringer

3. **Send prompten til AI'en**

4. **Gennemgå svaret:**
   - Er de foreslåede optimeringer relevante og effektive?
   - Er forklaringerne klare og forståelige?
   - Adresserer svaret dine specifikke behov eller begrænsninger?

5. **Iterér gennem dialog:**
   Hvis optimeringsforslagene ikke er helt tilfredsstillende:
   - Bed om yderligere forklaringer eller alternativer
   - Stil spørgsmål om potentielle trade-offs ved optimeringerne
   - Diskuter hvordan optimeringerne kan påvirke andre dele af systemet
   - Fortsæt dialogen indtil du har en god forståelse og praktisk anvendelige optimeringer

   Eksempel på iteration:
   "Tak for optimeringsforslaget. Kan du uddybe, hvordan denne ændring påvirker hukommelsesforbruget? Jeg er også interesseret i at vide, om der er nogen potentielle negative konsekvenser for læsbarheden af koden. Hvis du har alternative tilgange, der måske balancerer ydeevne og læsbarhed bedre, vil jeg gerne høre om dem."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for kodeoptimering:

1. **Optimering af tidskompleksitet:**
   "Kan du hjælpe mig med at optimere følgende Python-funktion, der finder det næststørste element i en liste? Den nuværende implementation har en tidskompleksitet på O(n log n) på grund af sorteringen. Jeg vil gerne reducere det til O(n) hvis muligt.

   ```python
   def find_second_largest(numbers):
       if len(numbers) < 2:
           return None
       sorted_numbers = sorted(set(numbers), reverse=True)
       return sorted_numbers[1]
   ```

   Giv venligst en optimeret version af funktionen sammen med en forklaring af, hvordan og hvorfor den er mere effektiv. Hvis der er nogen trade-offs ved den optimerede version, så nævn dem venligst også."

2. **Hukommelsesoptimering:**
   "Jeg har følgende Java-klasse, der bruges til at cache store mængder data. Den bruger meget hukommelse, især når antallet af elementer vokser. Kan du foreslå måder at optimere hukommelsesforbruget på uden at ofre for meget på ydelsen?

   ```java
   public class DataCache {
       private Map<String, List<Integer>> cache = new HashMap<>();

       public void addData(String key, List<Integer> data) {
           cache.put(key, new ArrayList<>(data));
       }

       public List<Integer> getData(String key) {
           return new ArrayList<>(cache.get(key));
       }

       public boolean hasData(String key) {
           return cache.containsKey(key);
       }
   }
   ```

   Jeg er særligt interesseret i:
   - Hvordan vi kan reducere hukommelsesforbruget
   - Eventuelle alternative datastrukturer, der kunne være mere effektive
   - Hvordan vi kan håndtere situationer, hvor cachen vokser for stor
   
   Forklar venligst dine forslag og giv eksempler på, hvordan de kan implementeres."

3. **Optimering af databaseforespørgsler:**
   "Jeg har følgende SQL-forespørgsel, der kører langsomt på store datasæt. Kan du hjælpe med at optimere den?

   ```sql
   SELECT o.order_id, o.order_date, c.customer_name, 
          p.product_name, oi.quantity, p.price
   FROM orders o
   JOIN customers c ON o.customer_id = c.customer_id
   JOIN order_items oi ON o.order_id = oi.order_id
   JOIN products p ON oi.product_id = p.product_id
   WHERE o.order_date BETWEEN '2023-01-01' AND '2023-12-31'
   ORDER BY o.order_date DESC;
   ```

   Databasen har millioner af ordrer og ordre-items. Giv venligst forslag til, hvordan denne forespørgsel kan optimeres, herunder:
   - Eventuelle indekser, der kunne hjælpe
   - Mulige omstruktureringer af forespørgslen
   - Tips til, hvordan man kan analysere og forbedre ydeevnen af SQL-forespørgsler generelt

   Hvis du har brug for flere oplysninger om skemastrukturen eller typiske anvendelsesmønstre, så sig endelig til."

4. **Parallellisering og concurrency:**
   "Jeg har en C# applikation, der behandler en stor mængde filer sekventielt. Kan du hjælpe mig med at omskrive den til at udnytte parallel processering for at forbedre ydeevnen? Her er den nuværende kode:

   ```csharp
   public class FileProcessor
   {
       public void ProcessFiles(string[] filePaths)
       {
           foreach (var filePath in filePaths)
           {
               string content = File.ReadAllText(filePath);
               string processedContent = ProcessContent(content);
               File.WriteAllText(filePath + ".processed", processedContent);
           }
       }

       private string ProcessContent(string content)
       {
           // Simulerer en tidskrævende operation
           Thread.Sleep(100);
           return content.ToUpper();
       }
   }
   ```

   Jeg vil gerne vide:
   - Hvordan vi kan parallellisere filbehandlingen
   - Hvordan vi kan håndtere potentielle concurrency-problemer
   - Bedste praksis for at balancere parallelitet og ressourceforbrug
   
   Giv venligst en optimeret version af koden og forklar de vigtigste ændringer og deres fordele."

5. **Algoritmisk optimering:**
   "Jeg har implementeret følgende algoritme i JavaScript til at finde alle primtal op til et givet tal ved hjælp af Sieve of Eratosthenes. Selvom den fungerer, er den langsom for store input. Kan du hjælpe med at optimere den?

   ```javascript
   function findPrimes(n) {
       let primes = new Array(n + 1).fill(true);
       primes[0] = primes[1] = false;

       for (let i = 2; i <= n; i++) {
           if (primes[i]) {
               for (let j = i * i; j <= n; j += i) {
                   primes[j] = false;
               }
           }
       }

       return primes.reduce((acc, isPrime, num) => {
           if (isPrime) acc.push(num);
           return acc;
       }, []);
   }
   ```

   Jeg er interesseret i:
   - Hvordan vi kan forbedre tidskompleksiteten
   - Eventuelle optimeringsmuligheder specifikke for JavaScript
   - Måder at reducere hukommelsesforbruget, især for meget store værdier af n
   
   Giv venligst en optimeret version af algoritmen sammen med en forklaring af de foretagne ændringer og deres indvirkning på ydeevnen."

## Tips
- Vær specifik om hvilke aspekter af koden du ønsker at optimere (f.eks. hastighed, hukommelsesforbrug, skalerbarhed).
- Inkluder information om den kontekst, koden kører i (f.eks. hardware-begrænsninger, forventet input-størrelse).
- Bed om forklaringer på de foreslåede optimeringer, så du forstår rationalet bag ændringerne.
- Spørg om potentielle trade-offs ved optimeringerne.
- Overvej at bede om alternative optimeringstilgange, hvis det er relevant.
- Hvis du arbejder med et specifikt programmeringssprog eller framework, så nævn det, da optimeringsmuligheder kan variere.
- Afslut med en opfordring til AI'en om at dele eventuelle generelle tips eller best practices for kodeoptimering.

## Udfordring
Vælg en af følgende udfordringer eller brug en fra dit eget projekt:

1. Optimer en rekursiv funktion til at bruge tail recursion eller omskriv den til en iterativ løsning.
2. Forbedre ydeevnen af en funktion, der arbejder med store datasæt, ved at implementere caching eller memoization.
3. Optimer en CPU-intensiv operation ved at udnytte parallelle beregninger eller multitrådning.
4. Reducer hukommelsesforbruget i en datastruktur, der håndterer store mængder data.
5. Forbedre ydeevnen af en databasedrevet applikation ved at optimere forespørgsler og indekser.

Brug AI'en til at guide dig gennem optimeringsprocessen, få forklaringer på de foreslåede ændringer, og diskuter fordele og ulemper ved forskellige optimeringstilgange.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan hjalp AI'en dig med at identificere optimeringsmuligheder, du måske ikke selv havde overvejet?
- Hvilke aspekter af kodeoptimering fandt du mest udfordrende, og hvordan assisterede AI'en med disse?
- Hvordan balancerede du mellem forskellige optimeringsmål (f.eks. hastighed vs. læsbarhed)?
- Hvilke nye optimeringsteknikker eller -strategier lærte du gennem denne proces?

Husk, at mens AI kan være et kraftfuldt værktøj til at identificere og implementere optimeringsmuligheder, er det vigtigt at have en grundlæggende forståelse af ydeevne og optimeringsteknikker. Brug AI'en som et supplement til din egen viden og erfaring, og vær altid kritisk over for de foreslåede ændringer.