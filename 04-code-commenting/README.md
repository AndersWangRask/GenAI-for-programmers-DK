---
title: Øvelse 4 - Kommentering af kode
nav_order: 5
---

# Øvelse 4: Kommentering af kode

## Formål
At lære at bruge AI til at tilføje passende og informative kommentarer til kode, med fokus på at formulere effektive prompts for at opnå klare, koncise og nyttige kommentarer.

## Beskrivelse
I denne øvelse vil du lære at præsentere ukommenteret kode for AI'en og bede om hjælp til at tilføje passende kommentarer. Du vil øve dig i at formulere prompts, der resulterer i klare, informative og relevante kommentarer, som forbedrer kodens læsbarhed og vedligeholdelse.

## Trin-for-trin guide

1. **Vælg et kodestykke uden kommentarer:**
   Start med et overskueligt kodestykke, der mangler kommentarer. Dette kan være en funktion, en klasse eller et lille script.

2. **Formuler din prompt:**
   Beskriv, hvad du ønsker i forhold til kommentering. Inkluder:
   - Programmeringssproget
   - Hvilken type kommentarer du ønsker (f.eks. funktionsbeskrivelser, inline kommentarer, dokumentationsstrenge)
   - Eventuelle specifikke aspekter af koden, du gerne vil have forklaret
   - Din foretrukne kommenteringsstil eller standarder

3. **Send prompten og den ukommenterede kode til AI'en**

4. **Gennemgå svaret:**
   - Er kommentarerne klare og informative?
   - Forklarer de de rigtige aspekter af koden?
   - Er de i overensstemmelse med god kommenteringspraksis?

5. **Iterér gennem dialog:**
   Hvis kommentarerne ikke er helt tilfredsstillende:
   - Bed om uddybning eller omformulering af specifikke kommentarer
   - Anmod om kommentarer til dele af koden, der ikke blev dækket
   - Foreslå justeringer baseret på din foretrukne stil eller standarder
   - Fortsæt dialogen indtil kommentarerne opfylder dine behov

   Eksempel på iteration:
   "Tak for kommentarerne. De er generelt gode, men kan du tilføje flere inline kommentarer til for-loopen? Jeg vil gerne have en kort forklaring på hvert trin i loopen. Desuden foretrækker vi at bruge // for inline kommentarer i stedet for #. Kan du opdatere kommentarerne med disse ændringer?"

## Eksempel-prompts

Her er nogle eksempler på gode prompts for kommentering af kode:

1. **Funktionskommentering:**
   "Kan du tilføje passende kommentarer til følgende Python-funktion? Inkluder venligst en funktionsbeskrivelse, parameterforklaringer og en beskrivelse af returværdien. Brug Python's docstring-format.

   ```python
   def process_data(raw_data, threshold):
       result = []
       for item in raw_data:
           if isinstance(item, (int, float)):
               if item > threshold:
                   result.append(item * 2)
           elif isinstance(item, str):
               if len(item) > threshold:
                   result.append(item.upper())
       return result
   ```
   Hvis du har brug for mere information om funktionens formål, så spørg endelig."

2. **Klassekommentering:**
   "Kan du tilføje kommentarer til denne Java-klasse? Inkluder klassebeskrivelse, metodebeskrivelser og eventuelle relevante inline kommentarer. Følg JavaDoc-standarden for metode- og klassedokumentation.

   ```java
   public class BankAccount {
       private String accountNumber;
       private double balance;
       private static final double MINIMUM_BALANCE = 100.0;
       
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
           if (amount > 0 && balance - amount >= MINIMUM_BALANCE) {
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
   Hvis du ser nogen steder, hvor yderligere forklaring ville være særligt nyttig, så fremhæv det gerne."

3. **Algoritmeforklaring:**
   "Kan du tilføje kommentarer til denne JavaScript-implementation af quicksort-algoritmen? Forklar gerne de forskellige trin i algoritmen og hvorfor de er nødvendige. Brug // for inline kommentarer og /** */ for funktionsbeskrivelser.

   ```javascript
   function quickSort(arr) {
       if (arr.length <= 1) {
           return arr;
       }

       const pivot = arr[Math.floor(arr.length / 2)];
       const left = [];
       const right = [];
       const equal = [];

       for (let element of arr) {
           if (element < pivot) {
               left.push(element);
           } else if (element > pivot) {
               right.push(element);
           } else {
               equal.push(element);
           }
       }

       return [...quickSort(left), ...equal, ...quickSort(right)];
   }
   ```
   Hvis du mener, at visse dele af algoritmen kræver mere detaljeret forklaring, så gør det endelig."

4. **Scriptkommentering:**
   "Kan du tilføje kommentarer til dette Python-script, der analyserer en logfil? Inkluder en overordnet beskrivelse af scriptet, forklaringer på de vigtigste trin og eventuelle antagelser eller begrænsninger. Brug # for enkelte linjer og trippel-anførselstegn for længere blokke af kommentarer.

   ```python
   import re
   from collections import Counter

   def parse_log(file_path):
       pattern = r'\[(\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2})\] \[(\w+)\] (.+)'
       entries = []
       
       with open(file_path, 'r') as file:
           for line in file:
               match = re.match(pattern, line)
               if match:
                   timestamp, level, message = match.groups()
                   entries.append((timestamp, level, message))
       
       return entries

   def analyze_log(entries):
       error_count = Counter(entry[1] for entry in entries)
       most_common_error = max(error_count, key=error_count.get)
       
       return {
           'total_entries': len(entries),
           'error_distribution': dict(error_count),
           'most_common_error': most_common_error
       }

   if __name__ == '__main__':
       log_file = 'application.log'
       log_entries = parse_log(log_file)
       analysis_result = analyze_log(log_entries)
       
       print(f"Total log entries: {analysis_result['total_entries']}")
       print(f"Error distribution: {analysis_result['error_distribution']}")
       print(f"Most common error: {analysis_result['most_common_error']}")
   ```
   Hvis du har forslag til, hvordan kommentarerne kan gøre scriptet lettere at vedligeholde eller udvide, så del dem gerne."

5. **Kommentering af kompleks logik:**
   "Kan du tilføje detaljerede kommentarer til denne C# metode, der implementerer en cache med en Least Recently Used (LRU) udskiftningspolitik? Forklar gerne den underliggende logik og datastrukturer. Brug // for korte kommentarer og /// for dokumentationskommentarer.

   ```csharp
   public class LRUCache<TKey, TValue>
   {
       private readonly int _capacity;
       private readonly Dictionary<TKey, LinkedListNode<CacheItem>> _cacheMap;
       private readonly LinkedList<CacheItem> _lruList;

       public LRUCache(int capacity)
       {
           _capacity = capacity;
           _cacheMap = new Dictionary<TKey, LinkedListNode<CacheItem>>(capacity);
           _lruList = new LinkedList<CacheItem>();
       }

       public TValue Get(TKey key)
       {
           if (_cacheMap.TryGetValue(key, out LinkedListNode<CacheItem> node))
           {
               TValue value = node.Value.Value;
               _lruList.Remove(node);
               _lruList.AddFirst(node);
               return value;
           }
           return default;
       }

       public void Put(TKey key, TValue value)
       {
           if (_cacheMap.TryGetValue(key, out LinkedListNode<CacheItem> existingNode))
           {
               _lruList.Remove(existingNode);
           }
           else if (_cacheMap.Count >= _capacity)
           {
               LinkedListNode<CacheItem> lastNode = _lruList.Last;
               _cacheMap.Remove(lastNode.Value.Key);
               _lruList.RemoveLast();
           }

           CacheItem cacheItem = new CacheItem(key, value);
           LinkedListNode<CacheItem> node = new LinkedListNode<CacheItem>(cacheItem);
           _lruList.AddFirst(node);
           _cacheMap[key] = node;
       }

       private class CacheItem
       {
           public CacheItem(TKey k, TValue v)
           {
               Key = k;
               Value = v;
           }

           public TKey Key { get; }
           public TValue Value { get; }
       }
   }
   ```
   Hvis du mener, at visse dele af implementeringen kræver mere detaljeret forklaring eller hvis du ser potentielle forbedringer, så nævn det gerne."

## Tips
- Vær specifik om hvilken type kommentarer du ønsker (f.eks. funktionsbeskrivelser, inline kommentarer, dokumentationsstrenge).
- Angiv eventuelle specifikke kommenteringsstandarder eller -formater du følger.
- Bed om forklaringer på komplekse dele af koden.
- Opfordr AI'en til at påpege steder, hvor yderligere kommentarer kunne være nyttige.
- Husk at kommentarer bør forklare 'hvorfor' snarere end 'hvad' koden gør, når det er relevant.
- Afslut med en opfordring til AI'en om at stille opklarende spørgsmål, hvis der er behov for mere kontekst.

## Udfordring
Vælg et stykke kode fra et af dine egne projekter, som mangler kommentarer eller har utilstrækkelige kommentarer. Præsenter det for AI'en og bed om hjælp til at tilføje passende kommentarer. Prøv at være specifik om dine krav og den kommenteringsstil, du foretrækker.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan forbedrede AI'ens kommentarer læsbarheden og forståelsen af koden?
- Var der nogen overraskende indsigter eller forklaringer i kommentarerne?
- Hvordan kan du integrere AI-assisteret kommentering i din normale kodningsproces?
- Hvilke fordele og potentielle faldgruber ser du ved at bruge AI til kodekommentering?

Husk, at gode kommentarer er en vigtig del af vedligeholdbar kode. AI kan være et nyttigt værktøj til at forbedre dine kommentarer, men det er stadig vigtigt at gennemgå og tilpasse kommentarerne til dit specifikke projekt og team.