# 🌴 Biitsi Palautelomakejärjestelmä

Täydellinen palautelomake ja analytiikka-dashboard Biitsin asiakaspalautteen hallintaan.

## 📋 Sisältö

- **feedback.html** – Asiakkaiden täyttämä palautelomake
- **dashboard.html** – Hallintapaneeli vastausten analysoinnille
- **SETUP.html** – Vaihe-vaiheelta asennusohje
- **README.md** – Tämä tiedosto

## ⚡ Pika-aloitus

### 1. Kloonaa repo
```bash
git clone <repo-url>
cd feedback
```

### 2. Testaa paikallisesti
```bash
# Python 3
python -m http.server 8000

# tai Node.js
npx http-server
```

Avaa selaimen: `http://localhost:8000/feedback/`

### 3. Muuta salasana (tärkeää!)
Avaa **dashboard.html** ja etsi:
```javascript
const DEFAULT_PASSWORD = 'biitsi2024';
```
Vaihda uuteen salasanaan ennen julkaisua.

## 📝 Palautelomake (feedback.html)

### Ominaisuudet
- ✅ Kaksikielinen (Suomi & Englanti)
- ✅ Nimi ja yritys erillisinä kentinä
- ✅ NPS 0-10 asteikko
- ✅ Klikkaa poistamaan valittu vastaus
- ✅ 12 arviointialuetta (tunnelma, musiikki, tilat, jne.)
- ✅ Avoin palaute -kenttä
- ✅ Urheilijatuen valinnainen tuki

### Data-tallennus
Vastaukset tallennetaan selaimen `localStorage`-muistiin automaattisesti. Dashboard lukee nämä vastaukset.

## 📊 Dashboard (dashboard.html)

### Kirjautuminen
Salasana on oletuksena: `biitsi2024`

### Näkymät
- **Yhteenveto**: Vastausmäärä, NPS-pisteet, keskiarvo
- **Kaaviot**: NPS-jakauma, odotuksia vastaaminen, lähdeanalyysi
- **Yksittäiset vastaukset**: Hae, suodata ja hallitse vastauksia

### Toiminnot
- 📥 **Vie CSV** – Vie kaikki vastaukset Excel-muotoon
- 📤 **Tuo CSV** – Tuo aiempia vastauksia
- 🗑️ **Poista** – Poista yksittäisiä vastauksia
- 🔍 **Suodattimet** – Etsi nimen, yrityksen tai sisällön perusteella

## 🔐 Turvallisuus

- Dashboard on suojattu salasanalla
- Data on paikallisesti selaimessa (ei pilvessä)
- **Vaihda oletussalasana** ennen julkaisua!

## 🌐 URL-osoitteet

Kun järjestelmä on julkaistu:

```
Palautelomake:   https://biitsi.fi/feedback/
Hallintapaneeli: https://biitsi.fi/feedback/dashboard.html
Ohje:           https://biitsi.fi/feedback/SETUP.html
```

## 📱 Tekniikka

- **Pohja**: Puhdas HTML/CSS/JavaScript (ei riippuvuuksia)
- **Storage**: Selaimen localStorage
- **Kaaviot**: Chart.js
- **Kielituki**: data-fi/data-en attribuutit
- **Responsive**: Toimii kaikilla laitteilla

## 🔧 Konfiguraatio

### Salasanan vaihto
Avaa `dashboard.html` ja muuta:
```javascript
const DEFAULT_PASSWORD = 'ominensalasana123';
```

### Värien muutos
Etsi `:root` CSS-sektiosta:
```css
:root {
  --lime: #FBFFA8;    /* Keltainen */
  --black: #111111;   /* Musta */
  --cream: #FEFFEE;   /* Tausta */
}
```

## 📤 Deployaus GitHub Pagesiin

1. Paina muutokset GitHubiin
2. Ota GitHub Pages käyttöön repon asetuksista
3. Aseta Branch: main, Folder: /
4. Järjestelmä on saatavilla osoitteesta: `https://<username>.github.io/feedback/`

## 🆘 Ongelmanratkaisu

**Data ei näy dashboardissa?**
- Tarkista, että käytät samaa verkkotunnusta
- Avaa F12 → Application → localStorage → biitsi_responses

**Salasana ei toimi?**
- Tyhjennä selaimen välimuisti
- Tarkista, että muutit salasanan oikein dashboard.htmlssa

**CSV-viennin ongelmat?**
- Vie-nappi lataa tiedoston `biitsi-palautteet-YYYY-MM-DD.csv`
- Tuonnin yhteydessä nykyiset tiedot korvataan

## 📚 Lisätiedot

Katso **SETUP.html** yksityiskohtaisen asennusohjeen saamiseksi.

## 📄 Lisensointi

© 2025 Biitsi.fi / Suomen Beach Volley Oy

---

**Versionumero**: 2.0  
**Päivitetty**: 2026-05-07  
**Tekijä**: Claude AI  
