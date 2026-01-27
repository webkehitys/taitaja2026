# Ohjeet

(päivitetty 27.1.)

## Tärkeää tietoa muutoksista ohjeissa

- Edellisestä vuodesta poiketen tänä vuonna on käytössä vain yksi repositorio, joka julkaistaan. Viime vuonna oli erilliset repositoriot backendille ja frontendille. Kaikkien kohdalla tämä ei ollut ongelmatonta, joten tänä vuonna käytössä on vain yksi.
- Kilpailijan tehtävänä on konfiguroida oma projektinsa niin, että se ei tarvitse backendille ja frontendille erillisiä repositorioita.
  - Jos esimerkiksi haluat yhdistää olemassa olevat Laravel- ja React-Vite-templatet, tämä täytyy tehdä itse, esimerkiksi buildaamalla React-projektin dist-kansio ja kopioimalla se Laravel-projektiin.

> _Pahoittelut siitä, että näiden ajantasalla olevien ohjeiden tekemisessä meni näin pitkään. Ongelmat julkaisuputkessa ja reposition mappaamisessä aiheuttivat sen, etten päässyt päivittämään ohjeita, kun omakaan ympäristö ei toiminut. -Laura/semifinaalivastaava_

## Tunnukset ja osoitteet

- Kilpailijoille lähetetetyssä Competitor Credentials -dokumentista löytyy kaikki tarvittavat tunnukset, salasana, access code ja url-osoitteet. Tiedot löytyvät myös Hallintapaneelista.

- Samat tunnukset ovat käytössä ennen kilpailua ja kilpailun aikana.

## Dashboard eli kilpailijan hallintapaneeli

- Pääset kaikkiin kilpailussa tarvittaviin palveluihin helposti [kilpailijan hallintapaneelista (Competitor Dashboard)](https://mc.nstrim.io/cd)

- Sinne kirjautumiseen tarvittava **6-numeroinen access code** löytyy Competitor Credentials -dokumentista.

### Hallintapaneelista:

- Näet paljonko kilpailuaikaa on jäljellä
- Löytyy linkki verkkosivulle, johon oma projektisi julkaistaan
- Löytyy linkki Gitea -palveluun
- Löytyy linkki PHPMyAdmin -palveluun
- Löytyy linkki [ohjeisiin ja dokumentaatioon](https://mc.nstrim.io/docs/competitor)
- Teet repositorion mappayksen eli julkaistavan repositorion valinnan

---

## Projetin aloitus ja julkaisu pähkinänkuoressa

- Luo repositorio mallipohjasta
- Kloonaa repositorio
- Koodiin ei tarvitse tehdä muutoksia
- Työnnä (push) paikallisesta ensimmäinen commit
- Mene hallintapaneeliin (dashboard)
- Kytke moduuli uuteen repositorioon (module mapping)
- Sovellus toimii

---

### 1. Repositorion luominen

- Avaa Git-palvelu (linkki löytyy kilpailijan hallintapaneelista):
  [https://git.taitaja2026.nstrim.app/](https://git.taitaja2026.nstrim.app/)
- Kirjaudu sisään tunnuksilla, jotka löytyvät kilpailijan hallintapaneelista.
- Luo uusi repositorio valmiista mallipohjasta (framework tai “vanilla”).

![new repo](/img/orgs.png)

- Nimeä repositorio haluamallasi tavalla:
  - käytä vain **pieniä kirjaimia**
  - ei välilyöntejä

- Valitse **Template items** -kohdasta:
  - ☑ **Git content (Default Branch)**

![new repo](/img/new_repo.png)

Mallipohjat sisältävät automaattisen deployn vaatimat asetukset.

---

### 2. Repositorion kloonaus ja kehitys

**Kloonaa repositorio:**

- Kopioi repositorion URL Gitean käyttöliittymästä:

![git clone](/img/clone.png)

- Kloonaa repositorio paikalliseen koneeseesi

**Koodaus:**

- Tee muutokset paikallisesti
- Tee committeja säännöllisesti eli usein
- Päivitä tarvittaessa README-tiedosto (asennusohjeet, riippuvuudet)

---

### 3. Repositorion mappaus (pakollinen)

⚠️ **Tämä vaihe on pakollinen, jotta sivusi voidaan julkaista**

- Avaa kilpailijan hallintapaneeli
- Valitse oikea repositorio Gitea-tilisi repositoriolistasta
- Tallenna valinta

![Repository mapping](/img/select_repo.png)

Ilman repositorion mappausta työsi **ei julkaistu automaattisesti**, vaikka push onnistuu.

---

### 4. Automaattinen deploy ja julkaisu

- Jokainen Git-push käynnistää automaattisen deployn
- Julkaisuprosessi kestää hetken:
  - esim. Next.js ja Laravel jopa noin 2 minuuttia

- Deployn tilan näet Gitean Actions -välilehdeltä
  ![workflows](/img/status.png)

Mihin sivu tylee: URL-osoite löytyy hallintapaneelista kohdasta **Module Work URL** alta.
![module url](/img/url.png)

**Suositukset:**

- Commitoi usein, mutta pushaa vain, kun isompi kokonaisuus on valmis.
- Tarkista aina deployn tila ennen jatkamista.
- Varmista, että viimeinen push tapahtuu ennen moduulin aikarajan päättymistä.

---

## Tietokantaan yhdistäminen - phpMyAdminin käyttö

Pääset palveluun helposti **hallintapaneelin** kautta.

**Kirjautuminen:**

- Klikkaa hallintapaneelista MySQL-ikonia, joka vie sinut osoitteeseen:
  [https://pma.taitaja2026.nstrim.app](https://pma.taitaja2026.nstrim.app)
- Kirjaudu sisään tunnuksilla, jotka löytyvät kilpailijan hallintapaneelista.

**Tietokantayhteys sovelluksessa:**

```php
define('DB_HOST', 'db.taitaja2026.nstrim.app');
```

Tietokannan käyttäjätunnus ja salasana löytyvät kilpailijan hallintapaneelista.

---
