# PROMPT UNIC PENTRU QWEN CODE — BUSOLA 120 + DESIGN DE REFERINȚĂ

Lucrezi ca principal full-stack engineer, creative director, UX engineer, narrative systems designer și QA lead. Construiește/actualizează aplicația locală BUSOLA, **fără GitHub, fără clone/remote, fără acces la infrastructură de producție**, folosind exclusiv folderul proiectului local și cele două fișiere anexate:

1. `busola_120_povesti.json` — **sursa canonică pentru 120 de experiențe draft**.
2. Imaginea de referință `Cinci scenarii pentru decizii mai bune(1).png` — **sursa vizuală pentru interfață**. Imaginea are 1536×1024 pixeli. Utilizatorul ți-o va atașa sau copia în proiect. **Deschide și inspectează efectiv imaginea; nu presupune că o vezi doar din nume.** Dacă nu există local, raportează acest lucru și folosește instrucțiunile textuale de mai jos, fără să pretinzi pixel-perfect.

## OBIECTIV

Realizează o platformă educațională românească de dezvoltare personală bazată pe decizii, cu **4 grupe de vârstă și 120 de experiențe**. Aceasta trebuie să arate foarte aproape de imaginea de referință, dar să fie un **produs interactiv** accesibil, nu o imagine statică. Codul, datele, imaginile și funcționalitățile trebuie separate corect.

**Nu redesena din imaginație. Referința vizuală are prioritate pentru aspectul catalogului și al playerului, atâta timp cât nu compromite accesibilitatea.**

## 1. DIRECȚIA VIZUALĂ EXACTĂ DIN IMAGINE

Imaginea reprezintă un mozaic editorial cinematic, de culoare brună, cu **cinci carduri dreptunghiulare late**, dispuse pe desktop astfel:
- primul rând: **3 carduri de aceeași lățime**;
- al doilea rând: **2 carduri de aceeași lățime, mai late decât cele de pe primul rând**;
- spațieri mici, constante, în jur de 8–12px;
- colțuri rotunjite discret, ~9–12px;
- fundal exterior aproape alb-ivory.

Reproduce **gramatica vizuală**, nu textul sau conținutul eronat al imaginilor din machetă. Designul unui card:
1. **Fotografie cinematografică hero pe întregul card** (warm editorial photo, realism fotografic, lumină aurie de apus, umbre cacao), `object-fit: cover`, gradient brun-negru pe margini pentru contrast.
2. În **colțul stânga-sus**: număr mare, serif editorial, subțire, cupru/auriu pal: `01`, `02`, ... . Lângă număr: titlu mare cu serif de culoare alb cald; imediat sub titlu un subtitlu scurt uppercase, font sans, tracking ridicat, text alb-ivory.
3. Partea de jos: **bandă cu 4 thumbnail-uri egale** separate de gap mic, contur 1–2px caramel luminos, colțuri ~8px. Fiecare thumbnail este o imagine independentă, cu overlay întunecat și etichetă albă lizibilă, jos-stânga.
4. Sub fiecare thumbnail, în marginea inferioară a cardului, text scurt uppercase, tracking larg: `CONTEXT`, `ALEGERI`, `CONSECINȚE`, `REFLECȚIE`. Folosește aceste patru etape în aceeași ordine ca macheta.
5. Iluminare „golden hour”, textură și profunzime: interior domestic cu veioze, ferestre luminoase, cafea, laptop, scene de discuții, stradă la apus; nu transforma totul într-o interfață foarte galbenă ori portocalie.
6. Atmosferă **Warm Premium / editorial storytelling / cinematic decision journeys**. Aspect rafinat, nu gamification, nu carduri dashboard standard.
7. Paletă de tokens: fundal `#F8F1E7`, ivory `#FFFCF7`, cacao `#38271F`, brun profund `#21140F`, terracotta `#8F442E`, caramel `#9A6035`, auriu stins `#B38A3F`. Text pe imagine `#FFF9F0`, overlay-uri negre/brune 25–75% în funcție de contrast.
8. Tipografie: serif elegant (de exemplu Georgia ori alt serif cu diacritice complete) pentru număr și titlu; sans lizibil pentru subtitluri și micro-label-uri. Fără text rasterizat: toate titlurile și etichetele sunt elemente HTML reale.

### Responsive
- 1440px+: grilă 3 sus / 2 jos pentru secțiunea cu cinci experiențe promovate, conform imaginii.
- 900–1439px: grilă fluidă cu 2 coloane, fără a forța o machetă ruptă; dacă este necesar, ultimul card poate ocupa două coloane.
- sub ~900px: o singură coloană, carduri cinematografice cu raport adaptat, bandă de thumbnail-uri utilizabilă; la mobil thumbnail-urile pot fi 2×2, fără text minuscul.
- Toate imaginile au fallback CSS/editorial dacă fișierele lipsesc.
- Contraste WCAG 2.2 AA, butoane cu focus vizibil, suport tastatură și `prefers-reduced-motion`.
- Întreaga suprafață/CTA a cardului și fiecare thumbnail au semantică de navigare funcțională, fără linkuri imbricate și fără controale inactive.

### Fotografiile
Imaginea atașată este o **referință de compoziție**, nu o bibliotecă din care să decupezi fotografii pentru scene. Nu utiliza screenshotul întreg drept UI, nu îl pune ca background fals și nu reutiliza fragmente cu text rasterizat. Pentru fiecare experiență pregătește un manifest de imagini proprii cu cinci sloturi: `context`, `branch-1`, `branch-2`, `branch-3`, `reflection`. Dacă generatorul de imagini este disponibil, imaginile trebuie să urmărească contextul poveștii și să păstreze același protagonist în toate scenele experienței. Dacă generatorul lipsește, livrează un sistem elegant de placeholder-uri + prompturi specifice, fără a pretinde că toate cele 600 de fotografii există.

**Important:** screenshotul conține inconsecvențe narative intenționate sau rezultate din machetare (de exemplu oferte turistice lângă un titlu despre alt produs). Folosește **numai JSON-ul** drept adevăr narativ; nu transfera în povestiri destinațiile, mesajele bancare, textele din screenshot sau pașii care nu se potrivesc poveștii.

## 2. ÎMPĂRȚIRE PE 4 ETAPE ALE VIEȚII

- `25-34` — **CONSTRUCȚIE · Carieră și disciplină**. Organizarea vieții, timpul, banii, relațiile, identitatea profesională.
- `35-44` — **RESPONSABILITATE · Echilibru și claritate**. Obligații, stres, familie și muncă fără a presupune că toți au copii.
- `45-59` — **MATURITATE · Experiență și adaptare**. Reevaluarea convingerilor, adaptarea obiceiurilor, colaborarea între generații.
- `60+` — **ÎNȚELEPCIUNE · Sens și continuitate**. Curiozitate, autonomie, relații și activitate potrivită fiecărei persoane, fără infantilizare.

Homepage-ul are un selector clar, premium, de vârstă/etapă. Vârsta este **preferință de explorare**, nu profil psihologic sau restricție rigidă. Permite schimbarea categoriei.

## 3. IMPORTĂ INTEGRAL 120 DE POVEȘTI DIN JSON

**Nu genera alte povești ca înlocuitor pentru datele atașate.** Importă cele 120 de intrări din `busola_120_povesti.json`, în română, păstrând exact ID, categoria, titlul, contextul, cele trei alegeri, cele trei consecințe, întrebarea de reflecție și acțiunea practică. Conținutul este **draft editorial**; nu schimba automat `editorialStatus` în approved.

Structură: 4 categorii × 6 capitole × 5 povești = 120. Cele șase capitole sunt:
1. Gândire critică și discernământ
2. Decizii și priorități
3. Emoții și autoreglare
4. Relații și comunicare
5. Disciplină și adaptare
6. Valori, sens și acțiune

În JSON, fiecare `choices[]` are `id`, `text`, `consequenceId`, `consequence`. Implementarea trebuie să asocieze consecința **exclusiv prin ID**, fără a ghici după ordine ori text. Jurnalul reflecțiilor este privat dacă este activat.

**Nu inventa** perspective biblice ca aprobate. Câmpul `perspective.status=pending_human_review` nu reprezintă conținut verificat. Playerul poate afișa o secțiune „Perspective în curs de pregătire” sau poate omite pasul până la review, fără a induce că există citate și surse aprobate.

## 4. CATALOG ȘI PLAYER CINEMATIC

Pagina catalog:
- secțiune HERO cu 5 povești promovate, în **grila 3+2 din fotografia atașată**; pentru fiecare categorie alege primele 5 sau un set configurabil din propriul catalog;
- apoi afișează lista integrală a celor 30 de povești din categoria aleasă, în 6 capitole;
- număr cu două cifre, titlu mare, subtitlu derivat din obiectiv/tema capitolului, 4 thumbnail-uri cu etapele, elemente clicabile reale, status draft vizibil doar în mediul de preview;
- nu folosi imagini cu text ca înlocuitor pentru UI.

Playerul pentru o poveste:
`Context → Cele 3 alegeri → Consecința corespunzătoare → Reflecție → Perspectivă (numai dacă e aprobată) → Acțiune → Finalizare`.

- Aspect de roman interactiv cinematic, cu imagine mare și text separat pe un panel ivory/cacao.
- La decizie, nu afișa anticipat consecințele și nu indica „alegerea corectă”.
- După alegere, afișează exact consecința ramurii selectate.
- Reflecția este opțională, utilizatorul poate sări.
- Reluare cu altă alegere, progres local de demo, istoric segregat pe experiență.
- Fără diagnostice, scoruri morale sau presiune de a dezvălui date personale.
- Toate cele 120 pot fi parcurse în mediul local privat de test cu date sintetice; nu înseamnă publicare autorizată.

## 5. ARHITECTURĂ ȘI CALITATE

Folosește Next.js/React/TypeScript/Tailwind sau stackul local compatibil deja inițializat. Pentru demonstrația inițială, datele pot fi încărcate din JSON local și progresul demo poate rămâne local, fără a pretinde autentificare sau plăți reale. Dacă există deja baze de date și autentificare locală, păstrează securitatea și nu elimina verificările.

Implementează:
- componente reutilizabile `AgeStageSelector`, `StoryMosaic`, `StoryCard`, `SceneStrip`, `ExperiencePlayer`, `DecisionChoice`, `ReflectionStep`, `SceneImage`;
- tokenuri de design, stiluri CSS responsabile și layout cu CSS Grid;
- `alt` descriptiv, placeholder-uri, skeleton și stări de eroare;
- test de integritate pentru **exact 120 experiențe**, **30/grup**, **5/capitol**, **3 opțiuni distincte/poveste**, fără coliziuni de ID, fără consecințe lipsă;
- teste pentru ramificare, navigare, responsive, keyboard și lipsa imaginilor;
- `npm run lint`, `npm run typecheck`, `npm run build`, testele existente și cele noi;
- screenshoturi reale desktop (1536×1024) și mobil pentru comparare cu referința, dacă mediul suportă browser automat;
- raport de diferențe vizuale reale observate. Nu pretinde identitate pixel-perfect dacă fotografiile originale nu sunt disponibile.

## 6. LIVRABILE ȘI LIMITE

Livrează cod funcțional, nu doar un plan. Rulează aplicația **local**, verifică efectiv URL-ul/portul și precizează dacă acesta poate fi accesat din browserul utilizatorului sau numai din workspace. Furnizează instrucțiuni locale de pornire și raport de verificări.

**Interzis:** GitHub, clone, push, remote Git, servere de producție, deployment public, chei live, plăți reale, expunerea jurnalelor, importul datelor personale sau publicarea necontrolată a drafturilor. Nu rescrie poveștile din JSON fără aprobarea editorială.

**Criteriu final:** un utilizator selectează una dintre cele patru etape, vede catalogul cu **aspect foarte apropiat imaginii de referință**, intră în oricare dintre cele 30 de povești specifice categoriei, face una din trei alegeri, primește consecința potrivită, reflectează opțional și finalizează într-un player consistent. Demonstrează acest parcurs în testele locale.

**Începe implementarea în folderul local. Nu te opri la analiză sau mockup.**
