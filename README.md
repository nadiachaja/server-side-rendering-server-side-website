> _Fork_ deze leertaak en ga aan de slag. Onderstaande outline ga je gedurende deze taak in jouw eigen GitHub omgeving uitwerken. De instructie vind je in: [docs/INSTRUCTIONS.md](docs/INSTRUCTIONS.md)

# Milledoni - cadeau
Milliedoni is een bedrijf waar je cadeaus op de website kan zoeken met behulp van filtertags. Ze geloven dat een cadeau mensen dichter bij elkaar brengt. 

## Inhoudsopgave

  * [Beschrijving](#beschrijving)
  * [Gebruik](#gebruik)
  * [Kenmerken](#kenmerken)
  * [Installatie](#installatie)
  * [Bronnen](#bronnen)
  * [Licentie](#licentie)

## Beschrijving
[Live-link](https://server-side-rendering-server-side-website-v1wv.onrender.com/) <br>
<br>
Ik heb een overzichtpagina en een detailapagina gemaakt en heb verschillende data opgehaald. Ik heb het figma design aangehouden wat we tijdens de briefing hadden gekregen. 
[Figma bestand ]([url](https://www.figma.com/design/iSlNaEtdQrLDkBoUJpikUh/Untitled?node-id=0-1&p=f&t=zax0UBdNOr0g0Dwh-0)) Ik heb het gekopieerd en in een eigen bestand gezet, zodat ik niet per ongelijk iets aanpas. 

De homepagina bestaat uit een header die overal terug komt. Daarnaast heeft de homepagina een chat en alle cadeaus. Door te chatten in de chat filter je door de cadeaus. Je kan cadeaus opslaan in een lijst. Als je op een cadeau klikt ga je naar de detailpagina waar je meer informatie krijgt over het cadeau. Ook kan je zien waar je het cadeau kan kopen en wat je misschien ook interessant vind. 

<video src="https://github.com/user-attachments/assets/02293021-f309-4d8c-837d-b8802e4ac642" controls muted autoplay playsinline></video>
<video src="https://github.com/user-attachments/assets/501405e4-da26-4bc2-8645-e5152a7637a9" controls muted autoplay playsinline></video>
<video src="https://github.com/user-attachments/assets/e5ff1ec7-5967-4551-a6f5-b168eef0dfb5" controls muted autoplay playsinline></video>
<video src="https://github.com/user-attachments/assets/7fc0fffc-17bf-4954-8d77-d6721e6834f5" controls muted autoplay playsinline></video>


## Gebruik
Bij de overzichtpagina kan je door de verschillende cadeaus scrollen en als je op een cadeau klikt ga je naar de detailpagina waar je meer infomatie hebt over het cadeau. Ook heb je daar dat je ziet welke winkel het product heeft en wat je misschien ook interessant is. Als die de pagina niet kan vinden ga je naar de 404 pagina en weet je dat de pagina er niet is. <br>
<br>
Ik heb via mobile first gewerkt op allebei de pagina's. Ik heb breakpoints op 550px,100px en 1230px. Dit zijn de belangrijkste breakpoints <br>
Ik heb 550px alleen gebruikt bij de overzichtpagina. de cadeus staan dan niet meer onder de chat filters, maar er komt een rij ernaast waar de cadeaus staan. Bij 1000px komt er een rij en nog een rij bij 1280px.
Bij de detailpagina was zag de mobiele versie er op kleinere tablet nog goed uit bij 1000px komt er een rij bij en komt de img aan de linkerkant en de rest aan de rechterkant. 

<video src="https://github.com/user-attachments/assets/28586cbd-8a73-497a-8bc1-252560d16553" controls muted autoplay playsinline></video>

## Kenmerken
<!-- Bij Kenmerken staat welke technieken zijn gebruikt en hoe. Wat is de HTML structuur? Wat zijn de belangrijkste dingen in CSS? Wat is er met Javascript gedaan en hoe? Misschien heb je een framwork of library gebruikt? -->

Ik heb gebruik gemaakt van Node.JS, Express en CSS. Door de Node.JS gebruikt ik Liquid om mijn HTML te maken en mijn pagina dynamisch te maken. <br>
<br>

**app.get('/', async function (request, response)** <br>
Haalt alle data op die ik eerder erin heb gezet <br>
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/server.js#L13-L14
Wordt getoond in index.liquid
<br>
<br>
**app.get('/cadeau/:slug', async function (request, response)** <br>
Zoekt een product op uit de database met een specifieke slug. De slug wordt ook gebruikt in de url. <br>
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/server.js#L38-L43
Wordt getoond in cadeau.liquid
<br>
<br>

**Loop cadeau producten** 
In de index.liquid
Alle cadeaus worden geladen en er wordt een register/log in kaartje erin gezet door een forloop die het kaartje op de 2de plek in de rij van de cadeau loop zet.
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/views/index.liquid#L8-L18
<br>
In de cadeau.liquid 
Hier worden de cadeaus in geladen.
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/views/cadeau.liquid#L138-L140
<br>
<br>

**Aparte size voor de loop cadeau producten**
Ik heb aparte sizes voor de loops, omdat de styling anders is.
<br>
index.liquid heeft de loop een size van large
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/views/index.liquid#L17
<br>
cadeau.liquid heeft de loop een size van small
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/views/cadeau.liquid#L139
<br>
CSS <br>
De class card is de large en de small heb ik apart neergezet.
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/public/styles.css#L364-L377

**404 pagina**
Ik heb een 404 pagina als de pagina niet gevonden is.
Hier wordt de pagina gemaakt en dat die komt als het niet gevonden wordt. 
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/server.js#L76-L78
<br>
Ik heb een if en else gemaakt zodat als de url niet klopt bij de detailpagina dat die dan naar de 404 pagina gaat.
https://github.com/nadiachaja/server-side-rendering-server-side-website/blob/88c9acee52ff7812e44caf25c653fdb11dfb4465/server.js#L50-L54


## Installatie
1. Download NodeJS
2. Fork deze repository
3. Clone het op je laptop
4. Open het in Github
5. Open de terminal in je Github
6. Typ in de terminal npm install om alles te installeren 
7. Typ in de terminal npm start om de server te starten
8. Je krijg een local host in de terminal klik daarop om je project te zien

## Bronnen

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
