# Instruktioner

(uppdaterad 27.1.)

## Viktig information om ändringar i instruktionerna

- Till skillnad från förra året används och publiceras i år endast **ett repository**. Förra året fanns separata repositories för backend och frontend. Detta fungerade inte problemfritt för alla, därför används i år endast ett repository.
- Det är tävlandens ansvar att konfigurera sitt projekt så att separata repositories för backend och frontend **inte behövs**.
  - Om du till exempel vill slå ihop de befintliga Laravel- och React-Vite-mallarna måste detta göras manuellt, till exempel genom att bygga (build) dist-katalogen i React-projektet och kopiera den till Laravel-projektet.

> _Jag ber om ursäkt för att det tog så lång tid att ta fram uppdaterade instruktioner. Problem i deploy-pipen och repository mapping gjorde att jag inte kunde uppdatera instruktionerna tidigare, eftersom inte heller min egen miljö fungerade.
> – Laura / semifinalansvarig_

## Inloggningsuppgifter och adresser

- Alla nödvändiga användarnamn, lösenord, accesskoder och URL-adresser finns i dokumentet **Competitor Credentials** som skickats till de tävlande. Samma information finns också i Dashboarden.

- Samma inloggningsuppgifter används **före tävlingen och under tävlingen**.

## Dashboard (Competitor Dashboard)

- Du når alla tjänster som behövs under tävlingen via
  [Competitor Dashboard](https://mc.nstrim.io/cd)

- Den **6-siffriga accesskoden** som krävs för inloggning finns i dokumentet Competitor Credentials.

### I Dashboarden kan du:

- Se hur mycket tävlingstid som återstår
- Hitta länken till webbplatsen där ditt projekt publiceras
- Hitta en länk till Gitea-tjänsten
- Hitta en länk till phpMyAdmin-tjänsten
- Hitta en länk till [instruktioner och dokumentation](https://mc.nstrim.io/docs/competitor)
- Utföra repository mapping, dvs. välja vilket repository som publiceras

---

## Projektstart och publicering i korthet

- Skapa ett repository från en mall
- Klona repositoriet
- Inga ändringar i koden krävs
- Pusha den första committen från din lokala miljö
- Gå till Dashboarden
- Koppla modulen till det nya repositoriet (module mapping)
- Applikationen fungerar

---

### 1. Skapa ett repository

- Öppna Git-tjänsten (länken finns i Competitor Dashboard):
  [https://git.taitaja2026.nstrim.app/](https://git.taitaja2026.nstrim.app/)
- Logga in med de inloggningsuppgifter som finns i Competitor Dashboard.
- Skapa ett nytt repository från en färdig mall (framework eller ”vanilla”).

![new repo](/img/orgs.png)

- Namnge repositoriet valfritt:
  - använd endast **små bokstäver**
  - inga mellanslag

- Under **Template items**, välj:
  - ☑ **Git content (Default Branch)**

![new repo](/img/new_repo.png)

Mallarna innehåller den konfiguration som krävs för automatisk deployment.

---

### 2. Kloning av repository och utveckling

**Klona repositoriet:**

- Kopiera repository-URL:en från Gitea-gränssnittet:

![git clone](/img/clone.png)

- Klona repositoriet till din lokala dator

**Kodning:**

- Gör ändringar lokalt
- Commitera regelbundet (ofta)
- Uppdatera README-filen vid behov (installationsanvisningar, beroenden)

---

### 3. Repository mapping (obligatoriskt)

⚠️ **Detta steg är obligatoriskt för att din webbplats ska kunna publiceras**

- Öppna Competitor Dashboard
- Välj rätt repository från listan över repositories i ditt Gitea-konto
- Spara valet

![Repository mapping](/img/select_repo.png)

Utan repository mapping **publiceras ditt arbete inte automatiskt**, även om pushen lyckas.

---

### 4. Automatisk deployment och publicering

- Varje Git-push startar en automatisk deployment

- Deploy-processen tar en stund:
  - till exempel kan Next.js och Laravel ta upp till cirka 2 minuter

- Du kan se deploy-statusen i fliken **Gitea Actions**
  ![workflows](/img/status.png)

**Var projektet publiceras:** Tävlingens URL finns i Dashboarden under **Module Work URL**

![module url](/img/url.png)

**Rekommendationer:**

- Commitera ofta, men pusha endast när en större helhet är färdig.
- Kontrollera alltid deploy-statusen innan du fortsätter.
- Säkerställ att din sista push sker innan modulens tidsgräns löper ut.

---

## Ansluta till databasen – använda phpMyAdmin

Du når tjänsten enkelt via **Dashboarden**.

**Inloggning:**

- Klicka på MySQL-ikonen i Dashboarden, som tar dig till:
  [https://pma.taitaja2026.nstrim.app](https://pma.taitaja2026.nstrim.app)
- Logga in med de inloggningsuppgifter som finns i Competitor Dashboard.

**Databasanslutning i applikationen:**

```php
define('DB_HOST', 'db.taitaja2026.nstrim.app');
```

Databasens användarnamn och lösenord finns i Competitor Dashboard.

---
