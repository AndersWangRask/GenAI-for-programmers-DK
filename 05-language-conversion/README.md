---
title: Øvelse 5 - Konvertering mellem programmeringssprog
nav_order: 7
---

# Øvelse 5: Konvertering mellem programmeringssprog

## Formål
At lære at bruge AI til at konvertere kode fra ét programmeringssprog til et andet, med fokus på at formulere effektive prompts for at opnå korrekte og idiomatiske oversættelser.

## Beskrivelse
I denne øvelse vil du lære at præsentere kode i ét programmeringssprog for AI'en og bede om hjælp til at konvertere det til et andet sprog. Du vil øve dig i at formulere prompts, der resulterer i præcise oversættelser, der tager højde for sprogspecifikke konventioner og bedste praksisser.

## Trin-for-trin guide

1. **Vælg et kodestykke og målsprog:**
   Start med et overskueligt kodestykke i et programmeringssprog, og beslut hvilket sprog du vil konvertere det til.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker konverteret. Inkluder:
   - Kildesprog og målsprog
   - Eventuelle specifikke krav eller begrænsninger
   - Om du ønsker forklaringer på væsentlige ændringer
   - Hvis der er specifikke sprogfunktioner eller biblioteker, du gerne vil bruge i målsproget

3. **Send prompten og kildekoden til AI'en**

4. **Gennemgå svaret:**
   - Er koden korrekt konverteret?
   - Er koden skrevet på en måde, der er typisk og naturlig for målsproget?
   - Er eventuelle sprogspecifikke ændringer forklaret tilfredsstillende?

5. **Iterér gennem dialog:**
   Hvis konverteringen ikke er helt tilfredsstillende:
   - Bed om forklaringer på dele af konverteringen, du ikke forstår
   - Anmod om alternative implementeringer, hvis det er relevant
   - Stil spørgsmål om eventuelle forskelle i funktionalitet eller ydeevne
   - Fortsæt dialogen indtil du har en konvertering, der opfylder dine behov

   Eksempel på iteration:
   "Tak for konverteringen. Jeg kan se, at du har brugt en for-loop i Python-versionen, men kunne vi ændre det til en list comprehension for at gøre det mere pythonisk? Kan du også forklare, hvorfor du valgte at bruge 'defaultdict' i stedet for en almindelig dictionary? Hvis du har brug for mere kontekst, så spørg endelig."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for konvertering mellem programmeringssprog:

1. **Java til Python:**
   "Kan du konvertere følgende Java-klasse til Python? Sørg for at følge Python's konventioner, såsom at bruge snake_case til metodenavne og undgå getters/setters hvor det er muligt. Forklar venligst eventuelle væsentlige ændringer i designet.

   ```java
   public class Employee {
       private String name;
       private int age;
       private double salary;

       public Employee(String name, int age, double salary) {
           this.name = name;
           this.age = age;
           this.salary = salary;
       }

       public void giveRaise(double percentage) {
           this.salary += this.salary * (percentage / 100);
       }

       public String getName() {
           return name;
       }

       public int getAge() {
           return age;
       }

       public double getSalary() {
           return salary;
       }

       @Override
       public String toString() {
           return "Employee{name='" + name + "', age=" + age + ", salary=" + salary + "}";
       }
   }
   ```
   Hvis der er nogen Python-specifikke funktioner eller biblioteker, der kunne forbedre implementeringen, så nævn dem gerne."

2. **Python til JavaScript:**
   "Kan du konvertere denne Python-funktion til JavaScript? Brug gerne moderne JavaScript-funktioner (ES6+) hvor det er passende. Forklar eventuelle betydelige forskelle i implementeringen.

   ```python
   def process_data(data):
       result = []
       for item in data:
           if isinstance(item, (int, float)):
               result.append(item * 2)
           elif isinstance(item, str):
               if len(item) > 3:
                   result.append(item.upper())
       return result

   # Eksempel på brug:
   sample_data = [1, "hello", 3.14, "world", 42, "ai"]
   print(process_data(sample_data))
   ```
   Kan du også tilføje nogle simple tests til den JavaScript-version for at sikre, at den fungerer som forventet?"

3. **C# til TypeScript:**
   "Kan du konvertere denne C#-klasse til TypeScript? Sørg for at udnytte TypeScripts typesystem og eventuelle relevante funktioner som interfaces eller generics. Forklar eventuelle designbeslutninger, du træffer i processen.

   ```csharp
   public class ShoppingCart
   {
       private Dictionary<string, int> items = new Dictionary<string, int>();

       public void AddItem(string item, int quantity)
       {
           if (items.ContainsKey(item))
           {
               items[item] += quantity;
           }
           else
           {
               items[item] = quantity;
           }
       }

       public void RemoveItem(string item, int quantity)
       {
           if (items.ContainsKey(item))
           {
               items[item] -= quantity;
               if (items[item] <= 0)
               {
                   items.Remove(item);
               }
           }
       }

       public int GetItemQuantity(string item)
       {
           return items.ContainsKey(item) ? items[item] : 0;
       }

       public List<string> GetItems()
       {
           return new List<string>(items.Keys);
       }

       public int GetTotalQuantity()
       {
           return items.Values.Sum();
       }
   }
   ```
   Hvis der er nogen TypeScript-specifikke mønstre eller best practices, der kunne forbedre denne implementation, så inkluder dem gerne."

4. **JavaScript til Rust:**
   "Kan du konvertere denne JavaScript-funktion til Rust? Sørg for at udnytte Rusts typesystem og ejerskabsmodel. Forklar venligst de vigtigste forskelle i implementeringen og eventuelle udfordringer ved konverteringen.

   ```javascript
   function findLongestWord(sentence) {
       const words = sentence.split(' ');
       let longestWord = '';
       
       for (let word of words) {
           if (word.length > longestWord.length) {
               longestWord = word;
           }
       }
       
       return longestWord;
   }

   // Eksempel på brug:
   console.log(findLongestWord('The quick brown fox jumps over the lazy dog'));
   ```
   Kan du også tilføje nogle simple tests til Rust-versionen for at demonstrere, hvordan man typisk tester i Rust?"

5. **SQL til MongoDB Query:**
   "Kan du konvertere denne SQL-forespørgsel til en tilsvarende MongoDB-forespørgsel? Forklar eventuelle forskelle i tilgangen og hvordan MongoDB håndterer joinoperationer anderledes.

   ```sql
   SELECT 
       customers.name, 
       orders.order_date, 
       products.product_name, 
       order_items.quantity
   FROM 
       customers
   INNER JOIN 
       orders ON customers.id = orders.customer_id
   INNER JOIN 
       order_items ON orders.id = order_items.order_id
   INNER JOIN 
       products ON order_items.product_id = products.id
   WHERE 
       orders.order_date > '2023-01-01'
   ORDER BY 
       orders.order_date DESC
   LIMIT 10;
   ```
   Kan du også give et eksempel på, hvordan man ville strukturere disse data i MongoDB for at optimere for denne type forespørgsel?"

## Tips
- Vær specifik om både kildesprog og målsprog.
- Angiv eventuelle versionskrav (f.eks. Python 3.8+, ES6+ JavaScript).
- Bed om forklaringer på væsentlige ændringer i implementeringen.
- Spørg om idiomatiske løsninger i målsproget.
- Overvej at bede om eksempler på brug eller simple tests i målsproget.
- Vær opmærksom på sprogspecifikke funktioner eller biblioteker, der kan forbedre implementeringen.
- Afslut med en opfordring til AI'en om at stille opklarende spørgsmål, hvis der er behov for mere kontekst.

## Udfordring
Vælg en funktion eller klasse fra et af dine projekter, og prøv at konvertere den til et programmeringssprog, du er mindre fortrolig med. Brug AI'en til at hjælpe med konverteringen og til at forklare de vigtigste forskelle mellem sprogene.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvilke udfordringer stødte du på ved konvertering mellem forskellige programmeringssprog?
- Hvordan hjalp AI'en dig med at forstå de sprogspecifikke forskelle og konventioner?
- Var der nogen overraskende forskelle eller ligheder mellem sprogene, som du lærte om?
- Hvordan kan du bruge denne teknik til at lære nye programmeringssprog eller forbedre din forståelse af forskellige sprogtilgange?

Husk, at selvom AI kan være en stor hjælp ved konvertering mellem programmeringssprog, er det stadig vigtigt at have en grundlæggende forståelse af begge sprog for at kunne evaluere og finjustere resultaterne effektivt.