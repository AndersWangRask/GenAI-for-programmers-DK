---
title: Øvelse 9 - Unit Test Generering
nav_order: 11
---

# Øvelse 9: Unit Test Generering

## Formål
At lære at bruge AI til at generere, forbedre og analysere unit tests, med fokus på at formulere effektive prompts for at opnå omfattende og robuste tests.

## Beskrivelse
I denne øvelse vil du lære at bruge AI til at hjælpe dig med at skrive unit tests for din kode. Du vil øve dig i at formulere prompts, der resulterer i effektive tests, dækker forskellige scenarier og hjælper med at identificere potentielle problemer i din kode.

## Trin-for-trin guide

1. **Vælg en kodeenhed til test:**
   Start med en funktion, metode eller klasse, som du vil skrive unit tests for.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker at teste. Inkluder:
   - Koden, der skal testes
   - Forventet funktionalitet
   - Eventuelle edge cases eller særlige scenarier
   - Det foretrukne test-framework (f.eks. JUnit, pytest)
   - Om du ønsker forklaringer på testene

3. **Send prompten til AI'en**

4. **Gennemgå svaret:**
   - Dækker testene alle væsentlige aspekter af funktionaliteten?
   - Er testene klare og let forståelige?
   - Er der taget højde for edge cases?

5. **Iterér gennem dialog:**
   Hvis testene ikke er helt tilfredsstillende:
   - Bed om yderligere tests for specifikke scenarier
   - Spørg om forbedringer af eksisterende tests
   - Diskuter potentielle svage punkter i koden, som testene har afsløret
   - Fortsæt dialogen indtil du har et sæt tests, der grundigt dækker din kode

   Eksempel på iteration:
   "Tak for disse tests. Kan vi tilføje nogle tests for grænsetilfælde, f.eks. når input er en tom liste eller indeholder negative tal? Desuden, hvordan kan vi teste for potentielle exceptions? Hvis du ser nogen måder at forbedre selve koden baseret på disse tests, så del dem gerne."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for unit test generering:

1. **Basal funktionstest:**
   "Kan du generere unit tests for følgende Python-funktion ved hjælp af pytest? Sørg for at teste både normale use cases og edge cases.

   ```python
   def calculate_discount(price, discount_percent):
       if discount_percent < 0 or discount_percent > 100:
           raise ValueError("Discount percent must be between 0 and 100")
       discount = price * (discount_percent / 100)
       return price - discount
   ```
   Inkluder venligst tests for gyldige input, grænseværdier og håndtering af exceptions."

2. **Klasse med afhængigheder:**
   "Jeg har følgende Java-klasse, der bruger en ekstern service. Kan du skrive JUnit-tests for denne klasse, inklusive hvordan man kan mocke den eksterne service?

   ```java
   public class UserManager {
       private final UserService userService;

       public UserManager(UserService userService) {
           this.userService = userService;
       }

       public User createUser(String username, String email) {
           if (userService.isUsernameTaken(username)) {
               throw new IllegalArgumentException("Username already exists");
           }
           User newUser = new User(username, email);
           return userService.saveUser(newUser);
       }

       public boolean deleteUser(String username) {
           User user = userService.findByUsername(username);
           if (user == null) {
               return false;
           }
           return userService.deleteUser(user.getId());
       }
   }
   ```
   Forklar venligst, hvordan man effektivt kan teste denne klasse uden at være afhængig af den faktiske implementation af UserService."

3. **Asynkron kode:**
   "Kan du hjælpe mig med at skrive unit tests for denne asynkrone JavaScript-funktion ved hjælp af Jest? Funktionen henter data fra en API og behandler det.

   ```javascript
   async function fetchAndProcessUserData(userId) {
       try {
           const response = await fetch(`https://api.example.com/users/${userId}`);
           if (!response.ok) {
               throw new Error('Failed to fetch user data');
           }
           const userData = await response.json();
           return {
               name: userData.name,
               email: userData.email,
               age: calculateAge(userData.birthDate)
           };
       } catch (error) {
           console.error('Error fetching user data:', error);
           return null;
       }
   }

   function calculateAge(birthDate) {
       const today = new Date();
       const birth = new Date(birthDate);
       let age = today.getFullYear() - birth.getFullYear();
       const monthDiff = today.getMonth() - birth.getMonth();
       if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birth.getDate())) {
           age--;
       }
       return age;
   }
   ```
   Inkluder tests for succesfulde API-kald, fejlhåndtering og edge cases i aldersberegningen."

4. **Test-Driven Development (TDD) approach:**
   "Jeg vil implementere en simpel Stack-datastruktur i C#. Kan du hjælpe mig med at skrive unit tests først, følgende TDD-princippet? Stacken skal understøtte følgende operationer:
   - Push: Tilføj et element øverst på stakken
   - Pop: Fjern og returner det øverste element
   - Peek: Se det øverste element uden at fjerne det
   - IsEmpty: Tjek om stakken er tom
   
   Brug NUnit som test-framework. Skriv tests for hver operation, inklusive edge cases og potentielle exceptions."

5. **Parametriserede tests:**
   "Jeg har denne TypeScript-funktion til validering af passwords. Kan du skrive parametriserede tests for den ved hjælp af Jest? Vi skal teste forskellige kombinationer af password-længder og tilstedeværelse/fravær af forskellige tegntyper.

   ```typescript
   function isPasswordValid(password: string): boolean {
       if (password.length < 8) return false;
       if (!/[A-Z]/.test(password)) return false;
       if (!/[a-z]/.test(password)) return false;
       if (!/[0-9]/.test(password)) return false;
       if (!/[!@#$%^&*]/.test(password)) return false;
       return true;
   }
   ```
   Inkluder en række test cases, der dækker både gyldige og ugyldige passwords. Forklar venligst, hvordan parametriserede tests kan gøre vores testsuite mere vedligeholdbar og omfattende."

## Tips
- Vær specifik om hvilken kode der skal testes og hvilke aspekter du vil fokusere på.
- Inkluder informationer om det ønskede test-framework og eventuelle særlige krav.
- Bed om tests, der dækker både normale use cases og edge cases.
- Overvej at bede om forklaringer på testenes struktur og formål.
- Spørg om best practices for testning inden for det specifikke sprog eller framework.
- Hvis relevant, bed om vejledning i at mocke eksterne afhængigheder.
- Afslut med en opfordring til AI'en om at foreslå forbedringer af selve koden baseret på test-perspektivet.

## Udfordring
Vælg en af følgende udfordringer eller brug en fra dit eget projekt:

1. Skriv tests for en funktion, der manipulerer strenge (f.eks. en funktion, der vender ord i en sætning).
2. Generer tests for en klasse, der implementerer en simpel datastruktur (f.eks. en linked list eller en binær søgetræ).
3. Lav tests for en funktion, der arbejder med datoer og tider, inklusive håndtering af forskellige tidszoner.
4. Skriv tests for en funktion, der udfører komplekse matematiske beregninger.
5. Generer tests for en service-klasse, der interagerer med en database eller ekstern API.

Brug AI'en til at hjælpe dig med at skrive omfattende tests, og sørg for at dække både normale scenarier og edge cases.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan hjalp AI'en dig med at identificere test-scenarier, du måske ikke selv havde tænkt på?
- Hvilke aspekter af unit test-generering fandt du mest udfordrende, og hvordan assisterede AI'en med disse?
- Hvordan kan AI-assisteret test-generering påvirke din tilgang til Test-Driven Development (TDD)?
- Hvilke potentielle faldgruber ser du ved at stole for meget på AI til at generere tests?

Husk, at mens AI kan være et kraftfuldt værktøj til at generere og forbedre unit tests, er det stadig vigtigt at have en dyb forståelse af din kode og dens forventede adfærd. AI-genererede tests bør altid gennemgås og justeres efter behov for at sikre, at de virkelig tester det, du har brug for.