# Øvelse 13: Sikkerhedsanalyse

## Formål
At lære at bruge AI til at identificere, analysere og afhjælpe sikkerhedsproblemer i kode, med fokus på at formulere effektive prompts for at opnå grundige sikkerhedsgennemgange og praktiske løsningsforslag.

## Beskrivelse
I denne øvelse vil du lære at bruge AI til at hjælpe dig med at udføre sikkerhedsanalyser af din kode. Du vil øve dig i at formulere prompts, der resulterer i detaljerede sikkerhedsgennemgange, identifikation af potentielle sårbarheder og forslag til, hvordan man kan forbedre kodens sikkerhed.

## Trin-for-trin guide

1. **Vælg et kodestykke til sikkerhedsanalyse:**
   Start med et specifikt kodestykke, som du ønsker at analysere for sikkerhedsproblemer. Det kan være en funktion, en klasse eller et helt modul.

2. **Formuler din prompt:**
   Beskriv præcist, hvad du ønsker at analysere. Inkluder:
   - Koden der skal analyseres
   - Hvilket programmeringssprog der bruges
   - Kontekst om, hvor og hvordan koden bruges
   - Specifikke sikkerhedsaspekter du er bekymret for (f.eks. injektionsangreb, autentificering, datahåndtering)
   - Om du ønsker forklaringer på de identificerede problemer og løsningsforslag

3. **Send prompten til AI'en**

4. **Gennemgå svaret:**
   - Er de identificerede sikkerhedsproblemer relevante og realistiske?
   - Er forklaringerne klare og forståelige?
   - Er de foreslåede løsninger praktiske og effektive?

5. **Iterér gennem dialog:**
   Hvis analysen ikke er helt tilfredsstillende:
   - Bed om yderligere detaljer om specifikke sårbarheder
   - Stil spørgsmål om potentielle angrebsscenarier
   - Diskuter, hvordan foreslåede sikkerhedsforanstaltninger kan påvirke ydeevne eller brugervenlighed
   - Fortsæt dialogen indtil du har en grundig forståelse af sikkerhedsproblemerne og mulige løsninger

   Eksempel på iteration:
   "Tak for sikkerhedsanalysen. Kan du uddybe, hvordan den identificerede XSS-sårbarhed konkret kunne udnyttes? Jeg er også interesseret i at vide, om der er nogen potentielle negative konsekvenser ved at implementere den foreslåede løsning, f.eks. i forhold til ydeevne eller kompatibilitet. Hvis du har alternative sikkerhedsforanstaltninger, der kunne overvejes, vil jeg gerne høre om dem."

## Eksempel-prompts

Her er nogle eksempler på gode prompts for sikkerhedsanalyse:

1. **Analyse af brugerinput-håndtering:**
   "Kan du udføre en sikkerhedsanalyse af følgende PHP-funktion, der håndterer brugerinput til en søgefunktion på en webside? Jeg er særligt bekymret for SQL-injektion og XSS-angreb.

   ```php
   function search_users($query) {
       $db = new mysqli("localhost", "username", "password", "database");
       $sql = "SELECT * FROM users WHERE name LIKE '%" . $query . "%'";
       $result = $db->query($sql);
       
       echo "<h2>Søgeresultater for: " . $query . "</h2>";
       while ($row = $result->fetch_assoc()) {
           echo "<p>" . $row['name'] . " - " . $row['email'] . "</p>";
       }
       $db->close();
   }

   if (isset($_GET['q'])) {
       search_users($_GET['q']);
   }
   ```

   Identificer venligst alle potentielle sikkerhedsproblemer, forklar hvordan de kunne udnyttes, og foreslå sikre alternativer til den nuværende implementering."

2. **Analyse af autentificeringsmekanisme:**
   "Jeg har følgende Python-funktion, der håndterer brugerlogin i en webapplikation. Kan du gennemgå den for potentielle sikkerhedssårbarheder og foreslå forbedringer?

   ```python
   import hashlib

   def user_login(username, password):
       db = connect_to_database()
       cursor = db.cursor()
       
       hashed_password = hashlib.md5(password.encode()).hexdigest()
       
       query = f"SELECT * FROM users WHERE username = '{username}' AND password = '{hashed_password}'"
       cursor.execute(query)
       user = cursor.fetchone()
       
       if user:
           session['user_id'] = user['id']
           return True
       else:
           return False
   ```

   Jeg er særligt interesseret i:
   - Sikkerheden af password-håndteringen
   - Potentielle injektionsrisici
   - Bedste praksis for sessionstyring
   
   Giv venligst konkrete forslag til, hvordan denne funktion kan gøres mere sikker."

3. **Analyse af fil-upload funktion:**
   "Kan du udføre en sikkerhedsanalyse af denne JavaScript/Node.js kode, der håndterer fil-uploads i en webapplikation? Jeg er bekymret for, om den er sårbar over for ondsindet fil-upload.

   ```javascript
   const express = require('express');
   const multer = require('multer');
   const path = require('path');

   const app = express();
   const upload = multer({ dest: 'uploads/' });

   app.post('/upload', upload.single('file'), (req, res) => {
       if (!req.file) {
           return res.status(400).send('No file uploaded.');
       }

       const file = req.file;
       const filePath = path.join(__dirname, 'uploads', file.originalname);

       fs.renameSync(file.path, filePath);

       res.send('File uploaded successfully.');
   });

   app.listen(3000, () => console.log('Server running on port 3000'));
   ```

   Identificer venligst potentielle sikkerhedsrisici, forklar hvordan de kunne udnyttes, og foreslå måder at forbedre sikkerheden uden at kompromittere funktionaliteten."

4. **Analyse af kryptografisk implementering:**
   "Jeg har implementeret følgende Java-klasse til at håndtere kryptering og dekryptering af følsomme data. Kan du gennemgå den for potentielle sikkerhedsproblemer og foreslå forbedringer?

   ```java
   import javax.crypto.Cipher;
   import javax.crypto.spec.SecretKeySpec;
   import java.util.Base64;

   public class Encryptor {
       private static final String KEY = "MySecretKey12345";
       private static final String ALGORITHM = "AES";

       public static String encrypt(String value) throws Exception {
           SecretKeySpec key = new SecretKeySpec(KEY.getBytes(), ALGORITHM);
           Cipher cipher = Cipher.getInstance(ALGORITHM);
           cipher.init(Cipher.ENCRYPT_MODE, key);
           byte[] encryptedBytes = cipher.doFinal(value.getBytes());
           return Base64.getEncoder().encodeToString(encryptedBytes);
       }

       public static String decrypt(String encrypted) throws Exception {
           SecretKeySpec key = new SecretKeySpec(KEY.getBytes(), ALGORITHM);
           Cipher cipher = Cipher.getInstance(ALGORITHM);
           cipher.init(Cipher.DECRYPT_MODE, key);
           byte[] decryptedBytes = cipher.doFinal(Base64.getDecoder().decode(encrypted));
           return new String(decryptedBytes);
       }
   }
   ```

   Jeg er særligt interesseret i:
   - Sikkerheden af nøglehåndteringen
   - Valg af krypteringsalgoritme og mode
   - Eventuelle problemer med implementation af kryptering/dekryptering
   
   Giv venligst detaljerede forslag til, hvordan denne implementering kan forbedres for at opnå bedre sikkerhed."

5. **Analyse af API endpoint:**
   "Kan du udføre en sikkerhedsanalyse af følgende C# kode, der implementerer et API endpoint til at opdatere brugeroplysninger? Jeg er bekymret for, om der er nogen potentielle sikkerhedshuller.

   ```csharp
   [HttpPut]
   [Route("api/users/{id}")]
   public IActionResult UpdateUser(int id, [FromBody] UserUpdateModel model)
   {
       if (!ModelState.IsValid)
       {
           return BadRequest(ModelState);
       }

       var user = _context.Users.Find(id);
       if (user == null)
       {
           return NotFound();
       }

       user.Name = model.Name;
       user.Email = model.Email;
       if (!string.IsNullOrEmpty(model.Password))
       {
           user.PasswordHash = ComputeHash(model.Password);
       }

       _context.SaveChanges();

       return Ok(new { message = "User updated successfully" });
   }

   private string ComputeHash(string input)
   {
       using (SHA256 sha256 = SHA256.Create())
       {
           byte[] bytes = Encoding.UTF8.GetBytes(input);
           byte[] hash = sha256.ComputeHash(bytes);
           return Convert.ToBase64String(hash);
       }
   }
   ```

   Identificer venligst eventuelle sikkerhedsproblemer, herunder men ikke begrænset til:
   - Autorisationsproblemer
   - Inputvalidering
   - Sikker håndtering af passwords
   - Potentielle CSRF-sårbarheder
   
   Giv konkrete forslag til, hvordan denne endpoint kan gøres mere sikker, og forklar rationalet bag hver anbefaling."

## Tips
- Vær specifik om konteksten, hvori koden kører (f.eks. webapplikation, mobilapp, intern service).
- Inkluder information om eventuelle eksisterende sikkerhedsforanstaltninger eller -politikker.
- Bed om forklaringer på identificerede sårbarheder, så du forstår risikoen.
- Spørg om bedste praksis for at afhjælpe specifikke typer af sikkerhedsproblemer.
- Overvej at bede om en prioriteret liste over sikkerhedsproblemer baseret på alvorlighed.
- Hvis relevant, bed om vejledning i, hvordan man kan teste for de identificerede sårbarheder.
- Afslut med en opfordring til AI'en om at dele eventuelle generelle sikkerhedstips eller -overvejelser for den type kode, du analyserer.

## Udfordring
Vælg en af følgende udfordringer eller brug en fra dit eget projekt:

1. Analysér en funktion, der håndterer brugerautentificering og sessionstyring.
2. Gennemgå kode, der håndterer filupload og -behandling for potentielle sikkerhedsrisici.
3. Undersøg en API-endpoint for sårbarheder relateret til autorisering og inputvalidering.
4. Analysér en implementering af kryptering eller hashing for potentielle svagheder.
5. Gennemgå en database-interaktionslag for SQL-injektionsrisici og sikker datahåndtering.

Brug AI'en til at hjælpe dig med at identificere sikkerhedsproblemer, forstå de potentielle risici, og udvikle sikre løsninger.

## Refleksion
Efter at have gennemført øvelsen, tænk over:
- Hvordan hjalp AI'en dig med at identificere sikkerhedsproblemer, du måske ikke selv havde overvejet?
- Hvilke aspekter af sikkerhedsanalyse fandt du mest udfordrende, og hvordan assisterede AI'en med disse?
- Hvordan kan du integrere AI-assisteret sikkerhedsanalyse i din normale udviklingsproces?
- Hvilke begrænsninger eller potentielle risici ser du ved at stole på AI til sikkerhedsanalyse?

Husk, at mens AI kan være et værdifuldt værktøj i sikkerhedsanalyse, er det vigtigt at kombinere det med menneskelig ekspertise og grundig testing. Sikkerhed er en kontinuerlig proces, og AI bør ses som et supplement til, ikke en erstatning for, traditionelle sikkerhedspraksisser.