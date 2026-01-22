# Ohjeet

## Ohjeet pähkinänkuoressa

1. Luo repositorio valmiiden mallipohjien avulla osoitteessa [https://git.taitaja2026.nstrim.app/](https://git.taitaja2026.nstrim.app/). On tärkeää käyttää annettuja pohjia, koska ne sisältävät Gitea Actions -ominaisuuden ja julkaisevat työsi automaattisesti pushin yhteydessä.
2. Kloonaa projekti ja työskentele paikallisesti. Commitoi usein, mutta pushaa vain, kun suurempi kokonaisuus on valmis. Jokainen push kestää jonkin aikaa julkaista (esim. Next.js ja Laravel jopa 2 minuuttia). Ole maltillinen.
3. Voit käyttää phpMyAdminia osoitteessa [pma.taitaja2026.nstrim.app](pma.taitaja2026.nstrim.app).

---

## 1. Luo uusi repositorio

- Mene Git-palvelimelle: [https://git.taitaja2026.nstrim.app/](https://git.taitaja2026.nstrim.app/).
- Kirjaudu sisään käyttäjätunnuksellasi ja salasanallasi.
- Siirry **Organisaatio → Frameworks**.

  ![orgs](/img/orgs.png)

- Valitse framework, jota haluat käyttää, tai "vanilla"-pohja.
- Klikkaa **"Use this template"** luodaksesi uuden repositorion.
- Nimeä repositorio moduulin nimen mukaan: **frontend** tai **backend**. Vanilla-projektissa nimeä repositorio **frontend**.

  ![secrets settings](/img/new_repo.png)

- Avaa repositoriosi asetukset: **Settings → Actions → Secrets**.
- Lisää seuraavat:
  - **USER:** Käyttäjänimesi (esim. comp01)
  - **PASS:** Salasanasi (esim. test123)

  ![secrets settings](/img/add-secret.png)

  ![secrets settings](/img/secrets.png)

- Tee commit ja tarkista, että Gitea Actions toimii oikein.
- Tarkista muutokset URL-osoitteessa:

  ```
  https://<aliverkko>-<moduulinimi>.taitaja.webkehitys.fi
  ```

> Jokaisella kilpailijalle on annettu käyttäjätunnus, salasana ja alias.
> Alias muodostaa aliverkon osoitteen, jota käytetään kilpailuympäristössä.
>
> Esimerkiksi alias **`skdjf`** näkyy näin:
>
> - Frontend: https://skdjf-frontend.taitaja2026.nstrim.app/
> - Backend: https://skdjf-backend.taitaja2026.nstrim.app/

---

## 2. Repositorion kloonaus ja käyttö

**Kloonaa repositorio:**

- Käytä repositorion URL-osoitetta kloonaukseen:

  ```bash
  git clone https://git.taitaja2026.nstrim.app//<käyttäjänimi>/<moduulinimi>.git
  ```

  **Esimerkki:**

  ```bash
  git clone https://git.taitaja2026.nstrim.app//comp01/frontend.git
  ```

**Muokkaa, committaa ja kehity:**

- Tee säännöllisesti committeja, jotta työ pysyy järjestyksessä.
- Päivitä **README-tiedosto** tärkeillä tiedoilla, kuten asennusohjeilla ja riippuvuuksilla.

---

## 3. phpMyAdmin käyttö

**Avaa phpMyAdmin:**

- Mene osoitteeseen [pma.taitaja2026.nstrim.app](pma.taitaja2026.nstrim.app).
- Kirjaudu sisään käyttäjätunnuksellasi ja salasanallasi.

**Tietokantayhteys:**

- Käytä alla olevaa host-asetusta yhdistääksesi tietokantaan:

  ```php
  define('DB_HOST', 'db.taitaja.webkehitys.fi');
  ```

Jokaisella käyttäjällä on ennalta määrätyt tietokannat:

```
username_frontend
username_backend
```

**Esimerkki:**

```
comp01_frontend
comp02_backend
```

---

## 4. Automaatio ja julkaisu

- Jokainen **push** julkaisee automaattisesti kilpailu-URL-osoitteeseen:

  ```
  https://<aliverkko>-<moduulinimi>.taitaja2026.nstrim.app/
  ```

- Koska jokainen Git push käynnistää deploy-prosessin, joka vie aikaa ja kuluttaa resursseja, suosittelemme kokoamaan muutokset ja tekemään pushit harvemmin.
- Tarkista muutokset kilpailu-URL-osoitteessa jokaisen pushin jälkeen.

---

> Jokaisella kilpailijalle on annettu käyttäjätunnus, salasana ja alias.
> Alias muodostaa aliverkon osoitteen, jota käytetään kilpailuympäristössä.
>
> Esimerkiksi alias **`skdjf`** näkyy näin:
>
> - Frontend: https://skdjf-frontend.taitaja2026.nstrim.app/
> - Backend: https://skdjf-backend.taitaja2026.nstrim.app/
