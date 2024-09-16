---
title: Øvelse 10 - API-dokumentation
nav_order: 12
---

# Øvelse 10: API-dokumentation

## Formål
At lære at bruge AI til at generere, forbedre og analysere API-dokumentation, med fokus på at formulere effektive prompts for at opnå klar, præcis og brugervenlig dokumentation.

## Beskrivelse
I denne øvelse vil du lære at bruge AI til at hjælpe dig med at skrive og forbedre API-dokumentation. Du vil øve dig i at formulere prompts, der resulterer i detaljeret, forståelig og praktisk anvendelig dokumentation for forskellige typer af API'er.

## Trin-for-trin guide

1. **Vælg et API eller en del af et API til dokumentation:**
   Start med et specifikt API endpoint, en klasse eller et modul, som du vil dokumentere.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker dokumenteret. Inkluder:
   - API'ens formål og overordnede funktionalitet
   - Specifikke endpoints, metoder eller funktioner
   - Forventet input og output format
   - Eventuelle autentificeringskrav
   - Ønsket dokumentationsformat (f.eks. OpenAPI/Swagger, README, inline kommentarer)

3. **Send prompten til AI'en**

4. **Gennemgå svaret:**
   - Er dokumentationen klar og let at forstå?
   - Dækker den alle væsentlige aspekter af API'en?
   - Er der eksempler på brug af API'en?
   - Er eventuelle fejlkoder og deres betydning beskrevet?

5. **Iterér gennem dialog:**
   Hvis dokumentationen ikke er helt tilfredsstillende:
   - Bed om uddybning af specifikke dele
   - Anmod om flere eller bedre eksempler
   - Spørg om hvordan man kan håndtere specifikke use cases
   - Fortsæt dialogen indtil du har en dokumentation, der opfylder dine behov

   Eksempel på iteration:
   "Tak for denne dokumentation. Kan vi tilføje et afsnit om rate limiting og hvordan man håndterer det? Desuden vil jeg gerne have nogle eksempler på, hvordan man kan bruge dette API med curl kommandoer. Hvis der er nogen best practices for fejlhåndtering, vil jeg også gerne have dem inkluderet."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for API-dokumentation:

1. **RESTful API Endpoint:**
   "Kan du generere OpenAPI (tidligere kendt som Swagger) dokumentation for følgende REST API endpoint? Det er en del af en e-commerce platform:

   - Endpoint: /api/products
   - Method: GET
   - Description: Henter en liste af produkter
   - Query Parameters: 
     - page (optional): Side nummer for pagination
     - limit (optional): Antal produkter per side
     - category (optional): Filtrer produkter efter kategori
   - Response: JSON array af produktobjekter
   - Authentication: Kræver API nøgle i header

   Inkluder venligst eksempler på request og response, mulige fejlkoder, og en kort beskrivelse af hvordan man autentificerer sig mod API'en."

2. **Python bibliotek:**
   "Jeg har skrevet følgende Python funktion som en del af et databehandlingsbibliotek. Kan du hjælpe mig med at skrive en god docstring for den, der følger Google's Python Style Guide?

   ```python
   def process_time_series(data, window_size, aggregation_func):
       result = []
       for i in range(len(data) - window_size + 1):
           window = data[i:i+window_size]
           result.append(aggregation_func(window))
       return result
   ```
   
   Forklar venligst funktionens formål, parametre, returværdi, og giv et eksempel på hvordan den kan bruges."

3. **GraphQL Schema:**
   "Jeg har følgende GraphQL schema for en blog applikation. Kan du generere dokumentation for det i Markdown format? Inkluder beskrivelser af typer, queries og mutations.

   ```graphql
   type Post {
     id: ID!
     title: String!
     content: String!
     author: User!
     comments: [Comment!]!
     createdAt: DateTime!
   }

   type User {
     id: ID!
     name: String!
     email: String!
     posts: [Post!]!
   }

   type Comment {
     id: ID!
     content: String!
     author: User!
     post: Post!
     createdAt: DateTime!
   }

   type Query {
     getPost(id: ID!): Post
     getPosts(limit: Int, offset: Int): [Post!]!
     getUser(id: ID!): User
   }

   type Mutation {
     createPost(title: String!, content: String!): Post!
     updatePost(id: ID!, title: String, content: String): Post!
     deletePost(id: ID!): Boolean!
     createComment(postId: ID!, content: String!): Comment!
   }
   ```
   
   Giv venligst også et par eksempler på, hvordan man kan udføre queries og mutations mod dette schema."

4. **C# class library:**
   "Jeg har følgende C# klasse, der er en del af et større bibliotek til filhåndtering. Kan du generere XML dokumentationskommentarer for klassen og dens metoder? Følg Microsoft's guidelines for XML dokumentation.

   ```csharp
   using System;
   using System.IO;

   namespace FileProcessingLibrary
   {
       public class FileProcessor
       {
           public string ProcessFile(string filePath, Func<string, string> lineProcessor)
           {
               if (!File.Exists(filePath))
                   throw new FileNotFoundException("The specified file was not found.", filePath);

               string processedContent = "";
               using (StreamReader reader = new StreamReader(filePath))
               {
                   string line;
                   while ((line = reader.ReadLine()) != null)
                   {
                       processedContent += lineProcessor(line) + Environment.NewLine;
                   }
               }
               return processedContent.TrimEnd();
           }

           public void SaveProcessedFile(string content, string outputPath)
           {
               File.WriteAllText(outputPath, content);
           }
       }
   }
   ```
   
   Inkluder venligst beskrivelser af klassen, metoderne, parametrene, returværdier, og eventuelle exceptions der kan kastes. Giv også et simpelt eksempel på, hvordan man kan bruge denne klasse."

5. **CLI Tool:**
   "Jeg har udviklet et command-line interface (CLI) værktøj til at konvertere billeder mellem forskellige formater. Kan du hjælpe mig med at skrive en README.md fil, der dokumenterer, hvordan man installerer og bruger dette værktøj? Værktøjet har følgende kommandoer og flag:

   - Kommando: convert
     - Flag:
       - -i eller --input: Input filsti (påkrævet)
       - -o eller --output: Output filsti (påkrævet)
       - -f eller --format: Output format (valgfrit, standard er PNG)
       - -q eller --quality: Output kvalitet for JPEG (valgfrit, 0-100, standard er 85)
   - Kommando: resize
     - Flag:
       - -i eller --input: Input filsti (påkrævet)
       - -o eller --output: Output filsti (påkrævet)
       - -w eller --width: Ny bredde (påkrævet)
       - -h eller --height: Ny højde (påkrævet)
   
   Værktøjet er skrevet i Python og kan installeres via pip. Inkluder venligst sektioner for installation, brug, eksempler, og almindelige fejl/troubleshooting."

## Tips
- Vær specifik om hvilken type API eller kode du dokumenterer (f.eks. RESTful API, bibliotek, klasse).
- Angiv det ønskede dokumentationsformat (f.eks. OpenAPI, README, inline kommentarer).
- Bed om eksempler på brug af API'en eller koden.
- Overvej at bede om beskrivelser af fejlscenarier og hvordan man håndterer dem.
- Spørg om best practices for at bruge API'en eller koden.
- Hvis relevant, bed om information om versionshistorik eller fremtidige ændringer.
- Afslut med en opfordring til AI'en om at foreslå forbedringer eller tilføjelser til dokumentationen.

## Udfordring
Vælg en af følgende udfordringer eller brug en fra dit eget projekt:

1. Skriv dokumentation for et REST API endpoint, der håndterer brugerregistrering og login.
2. Generer inline dokumentation for en kompleks funktion eller klasse i dit foretrukne programmeringssprog.
3. Lav en README.md fil for et open source projekt, du arbejder på eller er interesseret i.
4. Skriv dokumentation for et GraphQL schema, der repræsenterer et socialt medie med brugere, opslag og kommentarer.
5. Generer hjælpetekster for et CLI-værktøj, du har udviklet eller bruger ofte.

Brug AI'en til at hjælpe dig med at skrive omfattende og brugervenlig dokumentation. Husk at overveje forskellige typer af brugere (f.eks. nybegyndere vs. erfarne udviklere) i din dokumentation.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan hjalp AI'en dig med at strukturere og formulere din API-dokumentation?
- Var der aspekter af dokumentationen, som AI'en foreslog, som du ikke selv havde tænkt på?
- Hvordan kan AI-assisteret dokumentationsgenerering påvirke din tilgang til at designe og implementere API'er?
- Hvilke potentielle faldgruber ser du ved at stole for meget på AI til at generere dokumentation?

Husk, at mens AI kan være et kraftfuldt værktøj til at generere og forbedre API-dokumentation, er det stadig vigtigt at have en dyb forståelse af din API og dens brug. AI-genereret dokumentation bør altid gennemgås og tilpasses for at sikre, at den præcist repræsenterer din API's funktionalitet og bedst muligt hjælper dine brugere.