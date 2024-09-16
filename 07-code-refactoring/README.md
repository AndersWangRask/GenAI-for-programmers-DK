---
title: Øvelse 7 - Refaktorering
nav_order: 8
---

# Øvelse 7: Refaktorering

## Formål
At lære at bruge AI til at refaktorere og forbedre eksisterende kode, med fokus på at formulere effektive prompts for at opnå mere læsbar, vedligeholdbar og effektiv kode.

## Beskrivelse
I denne øvelse vil du lære at præsentere eksisterende kode for AI'en og bede om hjælp til at refaktorere og forbedre den. Du vil øve dig i at formulere prompts, der resulterer i meningsfulde forbedringer af kodens struktur, læsbarhed og ydeevne.

## Trin-for-trin guide

1. **Vælg et kodestykke til refaktorering:**
   Start med et overskueligt kodestykke, der kunne have gavn af forbedring. Det kan være kode med dårlig læsbarhed, gentagne elementer, eller ineffektive algoritmer.

2. **Formuler din prompt:**
   Beskriv, hvad du ønsker at forbedre. Inkluder:
   - Programmeringssproget
   - Specifikke områder du gerne vil have fokus på (f.eks. læsbarhed, ydeevne, modularitet)
   - Eventuelle begrænsninger eller krav (f.eks. baglæns kompatibilitet)
   - Om du ønsker forklaringer på de foreslåede ændringer

3. **Send prompten og den originale kode til AI'en**

4. **Gennemgå svaret:**
   - Er de foreslåede ændringer meningsfulde og forbedrer de koden?
   - Er forklaringerne på ændringerne klare og forståelige?
   - Er der aspekter af koden, som ikke blev adresseret?

5. **Iterér gennem dialog:**
   Hvis refaktoreringen ikke er helt tilfredsstillende:
   - Bed om yderligere forklaringer på specifikke ændringer
   - Foreslå alternative områder, der kunne forbedres
   - Stil spørgsmål om potentielle konsekvenser af ændringerne
   - Fortsæt dialogen indtil du har en refaktorering, der opfylder dine behov

   Eksempel på iteration:
   "Tak for refaktoreringen. Jeg kan se, at du har forbedret læsbarheden betydeligt. Kunne vi også se på at optimere ydeevnen af for-loopen i funktionen? Og hvad med fejlhåndtering - er der måder, vi kan gøre den mere robust? Hvis du har brug for mere kontekst om kodens anvendelse, så spørg endelig."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for refaktorering:

1. **Forbedring af læsbarhed:**
   "Kan du refaktorere følgende Python-funktion for at forbedre dens læsbarhed? Fokuser på at gøre koden mere selvforklarende, opdel lange linjer, og brug mere beskrivende variabelnavne. Behold funktionaliteten uændret.

   ```python
   def f(x,y,z):
       r=[]
       for i in range(len(x)):
           if x[i]>y and x[i]<z:
               r.append(x[i])
       return r
   ```
   Forklar venligst dine ændringer og hvorfor de forbedrer læsbarheden."

2. **Optimering af ydeevne:**
   "Denne JavaScript-funktion bruges til at finde de mest frekvente elementer i et array. Kan du refaktorere den for at forbedre dens ydeevne, især for store input? Behold funktionaliteten, men gør den hurtigere hvis muligt.

   ```javascript
   function findMostFrequent(arr) {
       let frequencyMap = {};
       let maxFrequency = 0;
       let mostFrequent = [];

       for (let i = 0; i < arr.length; i++) {
           if (frequencyMap[arr[i]]) {
               frequencyMap[arr[i]]++;
           } else {
               frequencyMap[arr[i]] = 1;
           }
           
           if (frequencyMap[arr[i]] > maxFrequency) {
               maxFrequency = frequencyMap[arr[i]];
               mostFrequent = [arr[i]];
           } else if (frequencyMap[arr[i]] === maxFrequency) {
               mostFrequent.push(arr[i]);
           }
       }

       return mostFrequent;
   }
   ```
   Forklar venligst dine optimeringer og hvordan de forbedrer ydeevnen."

3. **Forbedring af modularitet:**
   "Denne Java-klasse håndterer både fil-I/O og databehandling. Kan du refaktorere den for at forbedre dens modularitet? Opdel funktionaliteten i separate klasser eller metoder hvor det giver mening, og følg princippet om enkelt ansvar (Single Responsibility Principle).

   ```java
   public class DataProcessor {
       public void processFile(String filename) {
           try {
               BufferedReader reader = new BufferedReader(new FileReader(filename));
               String line;
               List<Integer> numbers = new ArrayList<>();
               while ((line = reader.readLine()) != null) {
                   numbers.add(Integer.parseInt(line.trim()));
               }
               reader.close();

               int sum = 0;
               for (int num : numbers) {
                   sum += num;
               }
               double average = (double) sum / numbers.size();

               BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"));
               writer.write("Sum: " + sum + "\n");
               writer.write("Average: " + average + "\n");
               writer.close();

               System.out.println("Processing complete. Results written to output.txt");
           } catch (IOException | NumberFormatException e) {
               e.printStackTrace();
           }
       }
   }
   ```
   Forklar venligst dine ændringer og hvordan de forbedrer klassens modularitet og vedligeholdbarhed."

4. **Anvendelse af designmønstre:**
   "Denne C# kode implementerer en simpel logger. Kan du refaktorere den til at bruge Singleton-designmønstret? Sørg for, at loggeren er trådsikker og kun instantieres én gang.

   ```csharp
   public class Logger
   {
       public void Log(string message)
       {
           string logEntry = $"{DateTime.Now}: {message}";
           Console.WriteLine(logEntry);
           File.AppendAllText("log.txt", logEntry + Environment.NewLine);
       }
   }

   // Usage
   Logger logger = new Logger();
   logger.Log("Application started");
   ```
   Forklar venligst fordelene ved at bruge Singleton-mønstret i dette tilfælde, og eventuelle overvejelser omkring implementeringen."

5. **Refaktorering til SOLID-principper:**
   "Denne TypeScript-kode bryder med flere SOLID-principper. Kan du refaktorere den for at følge disse principper bedre, særligt Single Responsibility og Open/Closed principperne?

   ```typescript
   class Order {
       constructor(public orderId: string, public customerName: string, public total: number) {}

       processOrder() {
           // Validate order
           if (this.total <= 0) {
               throw new Error("Invalid order total");
           }

           // Save to database
           console.log(`Saving order ${this.orderId} to database`);

           // Send confirmation email
           console.log(`Sending confirmation email to ${this.customerName}`);

           // Update inventory
           console.log("Updating inventory");
       }
   }

   // Usage
   const order = new Order("12345", "John Doe", 99.99);
   order.processOrder();
   ```
   Forklar venligst dine ændringer og hvordan de forbedrer kodens overholdelse af SOLID-principperne."

## Tips
- Vær specifik om hvilke aspekter af koden du ønsker at forbedre (f.eks. læsbarhed, ydeevne, modularitet).
- Hvis der er specifikke designmønstre eller principper du vil følge, nævn dem eksplicit.
- Bed om forklaringer på de foreslåede ændringer for at forstå rationalet bag refaktoreringen.
- Overvej at bede om flere alternative tilgange til refaktorering, hvis det er relevant.
- Spørg om potentielle trade-offs ved de foreslåede ændringer.
- Afslut med en opfordring til AI'en om at stille opklarende spørgsmål, hvis der er behov for mere kontekst om kodens anvendelse eller begrænsninger.

## Udfordring
Vælg et stykke kode fra et af dine egne projekter, som du mener kunne forbedres. Det kunne være en funktion, der er blevet for kompleks over tid, eller en klasse, der håndterer for mange ansvarsområder. Præsenter koden for AI'en og bed om hjælp til at refaktorere den.

Overvej at fokusere på et eller flere af følgende aspekter:
1. Forbedring af kodens læsbarhed og vedligeholdbarhed
2. Optimering af ydeevne
3. Anvendelse af relevante designmønstre
4. Forbedring af modularitet og separation of concerns
5. Implementering af SOLID-principper

Husk at bede AI'en om at forklare dens refaktoreringsbeslutninger, og vær ikke bange for at stille opfølgende spørgsmål eller bede om alternative tilgange.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvilke forbedringer i din kode var mest værdifulde eller overraskende?
- Hvordan hjalp AI'ens forklaringer dig med at forstå principperne bag god kodestruktur og design?
- Var der nogen foreslåede ændringer, du var uenig i eller som ikke passede til din specifikke kontekst?
- Hvordan kan du integrere denne type AI-assisteret refaktorering i din normale udviklingsproces?

Husk, at refaktorering er en løbende proces i softwareudvikling. AI kan være et kraftfuldt værktøj til at identificere forbedringsmuligheder og foreslå ændringer, men det er stadig vigtigt at bruge din egen dømmekraft og forståelse af projektets kontekst, når du beslutter, hvilke ændringer der skal implementeres.