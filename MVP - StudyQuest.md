# MVP Beskrivelse - StudyQuest

## Overordnet Koncept

### Problemstilling

Universitetsstuderende står over for flere udfordringer i deres læseproces: I traditionel eksamenoplæsning skal de studerende gennemgå lange, kedelige PDF-dokumenter og tekstbøger, der ofte virker uoverskuelige og demotiverende. Studerende kæmper med at:

* Navigere gennem hundreders af siders pensum uden klar struktur
* Fastholde fokus gennem passive læsesessioner
* Vurdere deres egen forståelse og fremskridt
* Identificere hvad der er vigtigst at fokusere på
* Forberede sig effektivt til mundtlige eksamener

I dag forsøger studerende at tackle disse udfordringer ved at bruge en fragmenteret kombination af værktøjer: ChatGPT, Gemini og Claude til tekstanalyse og summarization, Notebook LM til lydoverblik, Quizlet til flashcards, og forskellige skoleintra til kursusoverblik. De primære anvendelser fokuserer på at gøre tunge akademiske tekster lettere tilgængelige gennem summarization og uddybning af komplekse teorier. Selvom dette repræsenterer et skridt væk fra ren passiv læsning, forbliver det fundamentalt reaktivt snarere end proaktivt. Denne lappeløsning skaber ikke sammenhængende struktur i læseplanen, fastholder ikke fokus systematisk, tester ikke aktivt forståelsen, og identificerer ikke strategisk de mest kritiske områder at prioritere.

Mange studerende betaler allerede for premium versioner af disse chatbots, men oplever frustrationer med at prompte sig til effektiv læring. Med så almengyldige værktøjer kræver det betydelig tid og ekspertise at formulere de rigtige spørgsmål og få optimale resultater til læring, og selv da mangler den systematiske struktur og progression som effektiv eksamensforberedelse kræver. Derudover skaber det fragmenterede værktøjslandskab ineffektivitet og kompleksitet, da studerende skal navigere mellem flere platforme og manuelt integrere resultater fra forskellige AI-værktøjer.

## Løsningsapproach

Platformen udfordrer den traditionelle læseproces ved at ændre kedelige akademiske materialer til en dynamisk, interaktiv læringsoplevelse. Gennem avanceret AI-teknologi omdannes passiv læsning til aktiv læring ved at:

**Strukturere og organisere:** AI'en analyserer og opdeler komplekse materialer i logiske, håndterbare enheder, der følger en pædagogisk progression og videnskabeligt begrundede e-læring principper.

**Aktivere læringen:** Integrerede quizzer og interaktive elementer sikrer, at brugeren konstant engageres, testes og hjælpes i deres forståelse.

**Personalisere oplevelsen:** Systemet tilpasser sig det enkelte kursus ved at generere specifikke læringsmål, tests og simplificerede indhold baseret på det uploadede materiale.

**Simulere eksamenssituation:** Mundtlige "fake eksamener" forbereder studerende på den reelle eksamenssituation med AI-drevet feedback.

## Værdiproposition

Platformen leverer en komplet transformation af studieprocessen fra uoverskuelig til struktureret læsning, fra passivitet til aktivitet, og fra usikkerhed til selvsikkerhed. Studerende får:

* **Klarhed:** Præcis overblik over hvad der skal læses og i hvilken rækkefølge
* **Engagement:** Interaktive elementer der holder fokus og motivation høj
* **Forståelse:** Umiddelbar feedback og mulighed for at identificere videnshuller
* **Forberedelse:** Realistisk eksamenssimulation der bygger selvtillid
* **Progression:** Konstant overblik over fremskridt og resterende arbejde

## Teknologisk Innovation

Platformen kombinerer moderne AI-teknologi med pædagogiske principper for at skabe en løsning, der kan håndtere materiale på tværs af mange universitetsfag og -niveauer. AI'en fungerer som en personlig tutor, der forstår indholdet, identificerer kernebegreber, og skaber relevante tests tilpasset det specifikke materiale. Den systematiske promptning med forskellige modeller, sammenkoblet med en gennemarbejdet datastruktur sikrer en tilstrækkelig kvalitet i det genererede undervisningsmateriale. Kvaliteten at dette generede materiale vil på baggrund af dette overgå resultater, brugeren ville kunne opnå fra en traditionel chatbot.

## Målgruppe

**Primær målgruppe:** Universitetsstuderende på tværs af de fleste fagområder  
**Platform:** Desktop web-applikation

## Kerneværdi

Løser tre hovedproblemer for studerende:

* **Uoverskuelighed:** Strukturerer stort pensum i håndterbare dele
* **Kedsomhed:** Gør passiv læsning interaktiv med integrerede tests
* **Mangel på fokus:** Opdeler tekster og emner i chunks og retter fokus mod vigtige elementer og væk fra støjende elementer
* **Mangel på progression:** Viser klart fremskridt og manglende områder

---

## MVP Funktionalitet

### 1. Kursusoprettelse og Strukturering

#### Kursus-niveau:
* Brugeren opretter et kursus med:
  - Kursusnavn (f.eks. "Psykologi Grundkursus")
  - Skolenavn (f.eks. "Københavns Universitet")
  - Dato/semester (f.eks. "Forår 2025")
  - Studieretning
* Upload af overordnede dokumenter:
  - Officielle læringsmål
  - Kursusbeskrivelse
  - Andre overordnede dokumenter

#### Forelæsnings-niveau:
* Brugeren opretter forelæsninger en efter en
* For hver forelæsning kan uploades:
  - PDF-filer (inkl. scannede)
  - Billeder
  - Slides
  - Webartikler (via link - automatisk scraping)

### 2. AI-Genereret kursus content

#### Automatisk strukturering:

**På Kursusniveau har vi følgende datapunkter:**
* Navn
* Uddannelsessted
* Dato/semester
* Officielle læringsmål
* Officiel kursusbeskrivelse
* AI_Kursus (i JSON-format)
  - Indeholder alle ovenstående, men sat i JSON format for nem brug
  - AI_Kursusbeskrivelse (summarized)

**På forelæsning niveau har vi følgende datapunkter:**
* AI opdeler hver tekst i relevante chunks (ca. 5-15 linjer)
* Genererer specifikke læringsmål for hver forelæsning baseret på:
  - Uploadede materialer
  - Overordnede kursuslæringsmål
* Præsenterer forelæsninger kronologisk (men tillader fri navigation)

### 3. Interaktiv Læseoplevelse

#### Forberedelse før læsning:
* Kort summary af hele teksten præsenteres først
* Liste af kernebegreber og definitioner
* Klæder brugeren på til det kommende indhold

#### Chunk-baseret læsning:
* Brugeren præsenteres for en tekstchunk ad gangen
* Automatisk highlighting af vigtige sætninger og kernebegreber
* Knap til at få forsimplet version af chunk ved forståelsesvanskeligheder
* Læser og går videre til næste chunk
* Multiple choice spørgsmål hver 3-6 chunks (afhængig af indhold)

#### Quiz-funktionalitet:
* Spørgsmål fokuserer kun på det lige læste materiale
* Ved forkert svar:
  - Ingen umiddelbart korrekt svar
  - Henvisning til specifikt sted i teksten
  - Mulighed for at prøve igen efter genbesøg

### 4. Mundtlige "Fake Eksamener"

#### Timing og placering:
* Afholdes hver 1-4 forelæsninger (afhængig af indhold)
* Præsenterer åbne spørgsmål på skærmen

#### Funktionalitet:
* Ubegrænset svartid per spørgsmål
* Mulighed for at slette og genoptage optagelser
* AI-evaluering af indtalt svar
* Generering af relevante opfølgende spørgsmål

#### Feedback og anbefalinger:
* Evaluering af samlet præstation
* Specifikke anbefalinger til genbesøg:
  - Konkrete forelæsninger
  - Specifikke tekstafsnit
  - Målrettede revisionsområder

### 5. Progression og Tracking

#### Progressionsvisning:
* Procent gennemført på kursusniveau
* Procent gennemført på forelæsningsniveau
* Automatisk gem af fremskridt

#### Navigation:
* Kronologisk præsentation af forelæsninger
* Fri navigation tilladt
* Visuel indikation af gennemførte og manglende områder

---

## Tekniske Krav (MVP)

### Filhåndtering
* PDF-filer (digitale og scannede)
* Billeder (slides, diagrammer etc.)
* Webartikler via URL (automatisk scraping)
* Håndskrevne/scannede dokumenter

### AI-Funktionalitet
* Tekstanalyse og chunk-opdeling
* Automatisk highlighting af vigtige sætninger og begreber
* Generering af tekst-summaries og kernebegreber
* Forsimpling af komplekse tekstafsnit
* Multiple choice spørgsmålsgenerering
* Læringsmålsformulering
* Stemmeanalyse og evaluering
* Opfølgende spørgsmålsgenerering