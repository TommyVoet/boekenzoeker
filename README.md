# 📚 Boekenzoeker

Kleine web-app om onderweg (bijv. op boekenjacht) snel te checken of je een boek al hebt.
Iedereen gebruikt zijn eigen boekenlijst in Google Sheets; de app haalt die automatisch op.

## Eénmalige instelling per persoon

1. **Zet je boekenlijst om naar een Google Spreadsheet** (als dat nog een `.xlsx`-bestand is):
   open het bestand in Google Drive en kies *Bestand ▸ Opslaan als Google Spreadsheet*.
   Bewerken doe je voortaan in deze Spreadsheet (kan ook met de gratis Google Sheets-app op je telefoon).

2. **Maak de lijst leesbaar voor de app.** Kies één van beide:
   - *Delen* (knop rechtsboven) ▸ Algemene toegang: **Iedereen met de link – Kijker**, en kopieer de gewone link; **of**
   - *Bestand ▸ Delen ▸ Publiceren op internet* ▸ kies het blad en **CSV** ▸ kopieer die link.

3. **Open de app** op je telefoon en plak de link bij de instellingen. Vul eventueel je naam in.
   Zet daarna de app op je beginscherm: in Chrome/Safari via *Delen* of menu ▸ **Zet op beginscherm**.

Klaar. De app onthoudt alles; bij het openen zie je meteen je lijst (ook zonder bereik: dan de laatst opgehaalde versie) en wordt hij op de achtergrond ververst.

### Iemand anders op weg helpen

Open ⚙️ *Instellingen* in de app: onderaan staat een **deel-link** die de app automatisch instelt met jouw lijst. Voor iemand met een *eigen* lijst stuur je gewoon de kale app-link en doorloopt die persoon stap 1–3 met de eigen Spreadsheet.

## Verwachte kolommen

De eerste rij van het blad moet kolomkoppen hebben; de app herkent ze op naam
(kleine afwijkingen zijn oké):

| Auteur - achternaam | Auteur - voornaam | Titel | Oorspronkelijke titel | Opmerkingen |
|---|---|---|---|---|

Alleen *Titel* en/of *achternaam* zijn echt nodig; de rest is optioneel.

## Techniek

- Eén statische pagina ([index.html](index.html)), geen framework, geen backend.
- De Sheet-link wordt omgezet naar een CSV-adres (gepubliceerde link of `gviz`-export) en in `localStorage` bewaard, net als de laatst opgehaalde lijst (offline bruikbaar).
- [sw.js](sw.js) cachet de app-bestanden zodat de app ook zonder internet opent (PWA).
- Gehost op GitHub Pages.
- `test.csv` is alleen voor lokaal testen en wordt niet mee gedeployed (zie `.gitignore`).
