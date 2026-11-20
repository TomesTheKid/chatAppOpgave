# ChatApp

På 3. semester af datamatikeruddannelsen har vi i en gruppe lavet en chat-webapp, hvor brugere kan
logge ind, oprette chats og skrive beskeder til hinanden. Fokus i projektet har været at lave en
backend med Node.js og Express, med login, sessions, en REST API og en database i skyen.

## Funktioner
- Login og logout med sessions
- Brugere har forskellige niveauer:
    - Niveau 1: Kan se og skrive beskeder
    - Niveau 2: Kan oprette chats og redigere sine egne
    - Niveau 3: Kan redigere alle chats og tilføje brugere
- Oprettelse, redigering og sletning af chats
- Man kan se, hvilke brugere der er online
- Oversigt over brugere og hvilke beskeder de har skrevet

## Hvordan det virker
Serveren er lavet med Express og bruger Pug til at lave siderne. Chats og beskeder bliver gemt i
Firebase Firestore, hvor hver chat har sine beskeder liggende under sig.

Beskederne bliver krypteret med RSA, før de bliver gemt, så de ikke kan læses direkte i databasen.
Passwords bliver hashet, så de ikke ligger i klartekst, og nøgler og secrets ligger i en `.env`-fil
i stedet for i koden.

Adgang til de forskellige endpoints bliver styret med middleware, der tjekker om man er logget ind,
og om man har det rigtige niveau.

## Teknologier
- JavaScript (Node.js)
- Express
- Pug
- Firebase Firestore
- express-session

## Min rolle
Min primære rolle var at lave delen, hvor man kan se og skrive beskeder, se brugere, se hvem der
er online, og oprette og slette brugere. Det betød, at jeg lavede routes og endpoints til beskeder
og brugere i Express. Ud over det hjalp jeg også med Firebase Firestore og hashingen af passwords.

## Sådan køres projektet
1. Kør `npm install`
2. Lav en `.env`-fil ud fra `.env.example` og udfyld den med en session-secret og jeres Firebase-oplysninger
3. Kør `node app.js`
4. Åbn http://localhost:8080

Første gang serveren starter, laver den selv et nyt nøglepar til krypteringen.

## Screenshots
<img width="425" height="376" alt="image" src="https://github.com/user-attachments/assets/3d9049bf-d2db-4fa6-b644-cc36105ba86d" />
<img width="600" height="374" alt="image" src="https://github.com/user-attachments/assets/b450a811-adab-447c-9a43-a0370cc1ff40" />
<img width="950" height="337" alt="image" src="https://github.com/user-attachments/assets/d2a1e2e0-dd5d-4188-8180-212dcfc583f0" />
<img width="282" height="280" alt="image" src="https://github.com/user-attachments/assets/982beb0b-9318-40df-8a1f-0325a1f294df" />
