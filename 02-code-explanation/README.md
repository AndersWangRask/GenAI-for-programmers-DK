---
title: Øvelse 2 - Kodeforklaring
nav_order: 4
---

# Øvelse 2: Kodeforklaring

## Formål
At lære at bruge AI til at forklare og analysere eksisterende kode, med fokus på at formulere effektive prompts for at opnå klare og detaljerede forklaringer.

## Beskrivelse
I denne øvelse vil du lære at bede AI'en om at forklare forskellige kodestykker. Du vil øve dig i at formulere prompts, der resulterer i grundige og forståelige forklaringer af kodens funktion, struktur og eventuelle særlige aspekter.

## Trin-for-trin guide

1. **Vælg et kodestykke:**
   Start med et overskueligt kodestykke, som du gerne vil have forklaret. Det kan være en funktion, en klasse, eller et lille script.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker forklaret. Inkluder:
   - Programmeringssproget
   - Hvilket aspekt af koden du især er interesseret i (f.eks. overordnet funktion, specifikke linjer, optimeringsmuligheder)
   - Eventuelle specifikke spørgsmål du har om koden

3. **Send prompten og koden til AI'en**

4. **Gennemgå svaret:**
   - Er forklaringen klar og forståelig?
   - Dækker den alle de aspekter, du var interesseret i?
   - Er der noget, der mangler eller kunne uddybes?

5. **Iterér gennem dialog:**
   Hvis forklaringen ikke er fuldt tilfredsstillende:
   - Bed om uddybning af specifikke dele af forklaringen
   - Stil opfølgende spørgsmål om aspekter, der ikke blev dækket
   - Anmod om eksempler eller analogier, hvis noget er svært at forstå
   - Fortsæt dialogen indtil du har en klar forståelse af koden

   Eksempel på iteration:
   "Tak for forklaringen. Kan du uddybe, hvordan linjen 'x = [i for i in range(10) if i % 2 == 0]' fungerer? Særligt er jeg interesseret i at forstå list comprehension delen. Hvis du har brug for at give flere eksempler for at forklare det, så gør endelig det."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for kodeforklaring:

1. **Funktionsanalyse:**
   "Kan du forklare, hvad følgende Python-funktion gør? Forklar venligst trin for trin, hvordan den virker, og hvad dens formål er. Hvis du ser nogen potentielle problemer eller forbedringer, må du gerne nævne dem.

   ```python
   def process_data(data):
       result = []
       for item in data:
           if isinstance(item, (int, float)):
               result.append(item * 2)
           elif isinstance(item, str):
               result.append(item.upper())
       return result
   ```
   Hvis du har brug for yderligere kontekst eller information, så spørg endelig."

2. **Algoritmeforståelse:**
   "Kan du forklare, hvordan følgende JavaScript-funktion implementerer binær søgning? Forklar gerne algoritmen trin for trin og hvorfor den er effektiv.

   ```javascript
   function binarySearch(arr, target) {
       let left = 0;
       let right = arr.length - 1;
       while (left <= right) {
           const mid = Math.floor((left + right) / 2);
           if (arr[mid] === target) return mid;
           if (arr[mid] < target) left = mid + 1;
           else right = mid - 1;
       }
       return -1;
   }
   ```
   Hvis der er nogen specifikke aspekter af koden, du mener er særligt vigtige at forstå, så fremhæv dem gerne."

3. **Klassebeskrivelse:**
   "Kan du give en detaljeret forklaring af denne Java-klasse? Jeg er særligt interesseret i at forstå, hvordan konstruktøren fungerer, og hvordan metoderne interagerer med hinanden.

   ```java
   public class BankAccount {
       private String accountNumber;
       private double balance;
       
       public BankAccount(String accountNumber, double initialBalance) {
           this.accountNumber = accountNumber;
           this.balance = initialBalance;
       }
       
       public void deposit(double amount) {
           if (amount > 0) {
               balance += amount;
           }
       }
       
       public boolean withdraw(double amount) {
           if (amount > 0 && balance >= amount) {
               balance -= amount;
               return true;
           }
           return false;
       }
       
       public double getBalance() {
           return balance;
       }
   }
   ```
   Hvis du ser nogen måder at forbedre denne klasse på, eller hvis der er nogen potentielle fejl eller edge cases, der bør håndteres, så nævn det gerne."

4. **Regex forklaring:**
   "Kan du forklare, hvad følgende regular expression i Python gør? Giv gerne eksempler på, hvilke strenge den vil matche og hvilke den ikke vil matche.

   ```python
   pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
   ```
   Hvis du har brug for at bryde forklaringen ned i mindre dele, så gør endelig det."

5. **Kodeoptimering:**
   "Kan du analysere følgende C# kode og forklare, hvordan den fungerer? Derefter vil jeg gerne have dig til at påpege eventuelle ineffektiviteter og foreslå, hvordan koden kan optimeres.

   ```csharp
   public static List<int> FindDuplicates(List<int> numbers)
   {
       List<int> duplicates = new List<int>();
       for (int i = 0; i < numbers.Count; i++)
       {
           for (int j = i + 1; j < numbers.Count; j++)
           {
               if (numbers[i] == numbers[j] && !duplicates.Contains(numbers[i]))
               {
                   duplicates.Add(numbers[i]);
               }
           }
       }
       return duplicates;
   }
   ```
   Hvis du har forslag til, hvordan man kan forbedre både læsbarheden og ydeevnen af denne kode, så del dem gerne."

## Tips
- Vær specifik om, hvilke aspekter af koden du ønsker forklaret.
- Hvis koden er lang eller kompleks, overvej at bede om en overordnet forklaring først, og derefter dykke ned i specifikke dele.
- Spørg om potentielle problemer eller optimeringsmuligheder.
- Bed om eksempler eller analogier, hvis noget er svært at forstå.
- Afslut med en opfordring til AI'en om at stille opklarende spørgsmål, hvis der er behov for mere kontekst.

## Udfordring
Vælg et kodestykke fra et projekt, du arbejder på, eller find et interessant kodestykke online. Bed AI'en om at forklare det, og prøv derefter at stille opfølgende spørgsmål for at få en dybere forståelse.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvilke aspekter af kodeforklaringerne var mest nyttige for dig?
- Var der nogen misforståelser eller uklarheder i AI'ens forklaringer?
- Hvordan kan du bruge denne teknik i dit daglige arbejde som programmør?

Husk, at evnen til at få klare forklaringer på kode er et værdifuldt værktøj i din værktøjskasse som programmør. Det kan hjælpe dig med at forstå kompleks kode, debugge problemer, og endda lære nye programmeringsteknikker.