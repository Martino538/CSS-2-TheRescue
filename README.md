![Banner-fireworks](https://github.com/Martino538/CssFinalAssignment/assets/32341318/1137ad7c-6917-434f-88d5-2d957df52f34)


# Proces verslag
## Week 1
### Donderdag feb 27
Vandaag heb ik een schets gemaakt van mijn idee. Het is een combinatie tussen het onderwerp vuurwerk en een control panel. 
Er zullen verschillende elementen zoals radio buttons en toggle beschikbaar zijn om het type vuurwerk te beïnvloeden.

- Er zijn meerdere opties vuurwerk beschikbaar.
- Met de toggle kan je schakelen tussen dag en nacht modus. In dag modus kan het vuurwerk niet worden afgevuurd.
- Er zijn knoppen aanwezig waarmee de hoogte van het vuurwerk kan worden ingesteld.
- Er zijn knoppen aanwezig waarmee kan worden in-en-uitgezoomt.

<img width="1020" alt="Scherm­afbeelding 2024-03-14 om 09 34 37" src="https://github.com/Martino538/CssFinalAssignment/assets/32341318/4c7f1640-66aa-40aa-863f-23b667990bf6">


### Vrijdag march 1
Ik ga maandag beginnen met het maken van het deel wat ik moeilijk vind: animatie. Ik ga proberen een vuurwerk animatie te maken door een 'article' van beneden naar boven te animeren. Als dit element boven is aangekomen moeten de binnenliggende 'div' tags iedere een eigen richting opschieten.

## Week 2

### Maandag march 4
Vandaag heb ik een begin gemaakt aan de vormgeving. De vormgeving is een visuele ondersteuning voor hetgene wat ik wil maken en zie ik meteen wat er gebeurd met de code die ik schrijf. Dit is het resultaat van wat ik nu heb: 
<img width="1525" alt="Scherm­afbeelding 2024-03-13 om 17 28 30" src="https://github.com/Martino538/CssFinalAssignment/assets/32341318/e4b7874e-14b3-4a8e-a984-1d61727cffe1">

De bron om deze gradiënts te maken is: https://cssgradient.io/

`background: rgb(80,108,0);`</br>
`background: -moz-linear-gradient(0deg, rgba(80,108,0,1) 0%, rgba(175,217,57,1) 100%);`</br>
`background: -webkit-linear-gradient(0deg, rgba(80,108,0,1) 0%, rgba(175,217,57,1) 100%);`</br>
`background: linear-gradient(0deg, rgba(80,108,0,1) 0%, rgba(175,217,57,1) 100%);`</br>

Via [WhatCanIUse.com](https://caniuse.com/?search=linear-gradient) kwam ik erachter dat gradiënts eigenlijk goed ondersteund worden door de meeste browsers, waardoor webkit en moz niet meer nodig waren.

<img width="1377" alt="Scherm­afbeelding 2024-03-13 om 17 38 41" src="https://github.com/Martino538/CssFinalAssignment/assets/32341318/fc6e8ba9-f15e-43d3-a70e-320978ea3a62">




### Dinsdag march 5
Nu de basis van de vormgeving staat ben ik gaan werken aan de animatie. Ik heb een checkbox omgebouwd naar een normale knop, waardoor er een vuurwerkje kan worden afgeschoten.

Om de checkbox onzichtbaar te maken heb ik de volgende code gebruikt:

`Appearance: none`;

Vervolgens heb ik het label gestijlt, zodat deze op de knop lijkt. Als op het label drukt kan je de state van de checkbox beïnvloeden.

De daadwerkelijke animatie om het vuurwerk af te schieten bestaat uit 2 delen.

Deel 1 (schiet omhoog):</br>
`@keyframes launchFirework {`</br>
    `  from {`</br>
      `    transform: translate(0px, 0px);`</br>
    `  }`</br>
    `  to {`</br>
      `    transform: translate(0px, -300px);`</br>
    `  }`</br>
  `}`</br>

Deel 2 (Vuurwerk uitfaden):</br>
`@keyframes hideLaunch {`</br>
    `  from {`</br>
      `    opacity: 1;`</br>
    `  }`</br>
    `  50% {`</br>
      `    opacity: 1;`</br>
    `  }`</br>
    `  to {`</br>
      `    opacity: 0;`</br>
    `  }`</br>
  `}`</br>

Deel 3 (Explodeer functie):</br>
`@keyframes explode {`</br>
    `  from {`</br>
      `    top: 50%;`</br>
      `    left: 50%;`</br>
      `    transform: translate(-50%, -50%);`</br>
      `    opacity: 1;`</br>
    `  }`</br>
    `  50% {`</br>
      `    opacity: 1;`</br>
    `  }`</br>
    `  to {`</br>
      `    top: var(--explode-top, 150px);`</br>
      `    left: var(--explode-left, 50%);`</br>
      `    opacity: 0;`</br>
    `  }`</br>
  `}`</br>

Met deze animaties krijg je bij elkaar dit resultaat:</br>
![chrome-capture-2024-3-13](https://github.com/Martino538/CssFinalAssignment/assets/32341318/da1efdcf-26e0-45f5-a613-2b885f5ae6ef)

Wat ik hier van geleerd heb is het stijlen van een checkbox. Voorheen wist ik niet dat je deze dusdanig kon stijlen zodat het op een knop leek. Hiernaast heb ik geleerd hoe je de pseuodo-class :has() kunt gebruiken. D.m.v. deze code worden zowel het schieten als de explosie animatie in gang gezet als de checkbox is aangevinkt:

`body:has(section:nth-of-type(2) input[type="checkbox"]:checked) section:nth-of-type(2) article`</br>

`body:has(section:nth-of-type(2) input[type="checkbox"]:checked) section:nth-of-type(2) article ul li`</br>

Als laatste heb ik een toggle button toegevoegd om later te kunnen switchen tussen light en darkmode, radio buttons toegevoegd om de verschillende modussen aan te geven en heb ik een een font uitgekozen die bij het stijltje past. Het resultaat ziet er nu zo uit:</br>
<img width="1782" alt="Scherm­afbeelding 2024-03-13 om 21 01 38" src="https://github.com/Martino538/CssFinalAssignment/assets/32341318/cd3ecbf8-3493-443a-bcde-b3744bd81143">

### Vrijdag march 8
Deze dag heb ik mijn voortgang besproken. Mijn plan is om volgende week te gaan werken met states. Hierdoor kan ik werken met een dag-en-nacht modus en verschillende effecten toepassen op het vuurwerk met mijn radio buttons. Ik heb niet heel veel moeilijke dingen geleerd, maar vooral kleine dingen. Zo weet ik nu hoe ik een radio button visueel kan ombouwen naar een knop en hier een animatie aan koppel. Ook weet ik hoe ik een switch knop maak met behulp van CSS. Ik ben mij ervan bewust dat in browsers als safari een switch makkelijk gemaakt kan worden d.m.v. het html attribuut 'switch', maar aangezien dit niet door alle browsers wordt ondersteund kies ik ervoor om dit handmatig te maken. Volgende week ga ik mij focussen op het werken met verschillende modussen.

## Week 3

### Maandag march 11
Vandaag heb ik mij bezig gehouden met het maken van een dag-en-nacht modus. Nu deze modus gemaakt is, ga ik ervoor zorgen dat het afschieten van vuurwerk alleen mogelijk is als de nachtmodus actief is. Met andere woorden: De 'launch' knop is alleen beschikbaar als de checkbox voor dag-en-nacht modus is gecheckt. Het resultaat ziet er als volgt uit:


Hiernaast vond ik het lastig om te kunnen switchen tussen modussen met de radio buttons. Samen met Roel heb ik dit ervoor gezorgd dat het mogelijk is om te schakelen tussen veschillende modussen vuurwerk. Dit heb ik namelijk gedaan door met :has() chaining te werken. De code ziet er als volgt uit:</br>

`body:has(section:nth-of-type(1) ul li:nth-of-type(2) input[type="radio"]:checked):has(section:nth-of-type(2) input[type="checkbox"]:checked) section:nth-of-type(2) article ul li`</br>

Deze manier was voor mij nieuw waardoor ik weer extra functionaliteiten kan realiseren. Morgen ga ik verder met de in-en-uitzoom functie, gepaard met de kracht om vuurwerk af te schieten.


### Dinsdag march 12
Vandaag heb ik thuis gewerkt en flink wat functionaliteiten toegevoegd. Nu ik weet hoe je met modussen kunt werken d.m.v. :has() heb ik functionaliteiten voor vuurwerk toegevoegd. Zo is het nu mogelijk om met verschillende kracht de vuurpijl af te shieten. Hiernaast kan je ook in-en-uitzoomen om de vuurpijl van verschillende afstanden te bekijken en switchen tussen verschillende kleuren vuurwerk. Als laatste heb ik een pop-up toegevoegd die aangeeft dat je overdag geen vuurwerk kunt afsteken. Tot de pop-up is aangeklikt kan er geen interactie met de interface plaatsvinden. Nu ik :has() beter onder de knie heb en de functionaliteiten begin te snappen vind ik de opdracht echt leuk worden. Hiernaast heb ik ook uitgevogeld hoe je een transition op gradiënts kunt zetten. Dit doe je d.m.v. custom properties in CSS:</br>

De layout ziet er nu als volgt uit.
<img width="1784" alt="Scherm­afbeelding 2024-03-15 om 09 39 07" src="https://github.com/Martino538/CssFinalAssignment/assets/32341318/096a4d9d-406c-472d-acd7-4ec9a2c54304"></br>
<img width="1779" alt="Scherm­afbeelding 2024-03-15 om 09 37 01" src="https://github.com/Martino538/CssFinalAssignment/assets/32341318/b2470c16-20ce-4cc7-9ac8-2ec62de1f89d"></br>


`@property --groundColor2 {`</br>
  `    syntax: '<color>';`</br>
  `    initial-value: rgb(175, 217, 57);`</br>
  `    inherits: false;`</br>
`}`</br>


### Vrijdag 15 maart
Komende dagen ga ik mij vooral richten op het refactoren van mijn code. Momenteel is er nog veel dubbele code die ik kan vervangen. 

## Week 4
### Maandag 18 maart
Deze dag was ik ziek. Maar ondanks dat heb ik thuis doorgewerkt. Ik heb verschillende vuurwerk modussen toegevoegd. Nu is het mogelijk om vuurwerk in de vorm van een hartje en een ster af te schieten. Deze functionaliteiten had ik eigenlijk eerder deze week al gemaakt, maar hoef ik nu alleen om te bouwen. Het resultaat is als volgt: 


Modussen toegevoegd. Animatie in titel en responsive gemaakt.

### Dinsdag 19 maart
Vandaag heb ik een container query gemaakt om verschillende styling modussen toe te passen. Dit was nieuw voor mij en nuttig om hier meer van te weten. D.m.v. een custom CSS property kan ik een 'Nachtmodus' inschakelen. Als deze is ingeschakeld kan ik elementen verschillende styling meesturen. Het gebruik van een container query vervangt het gebruik van :has() bij het omzetten naar een dark mode. Hierdoor krijg je gestructureerde code waarin alle opties bij een dark mode bij elkaar staan. De code is hieronder te zien:

`html:has(input[name="dayNightMode"]:checked) {`</br>
  `--dayAndNight: night;`</br>
`}`</br>

`@container style(--dayAndNight:night) {`</br>
`  body {`</br>
  `  --skyColor1: rgb(0, 0, 0, 1);`</br>
  `  --skyColor2: rgb(30, 100, 151);`</br>
  `}`</br>

  `body section:nth-of-type(2) div:last-of-type label {`</br>
    `border-color: var(--red);`</br>
    `color: var(--red);`</br>
    `pointer-events: all;`</br>
    `border-radius: 10px;`</br>
  `}`</br>
  
  `body section:nth-of-type(2) div:last-of-type label:hover {`</br>
    `color: var(--white);`
  `}`</br>
`}`</br>

Hiernaast heb ik de code gelegd op het refactoren van mijn code. Ik heb een kleurenschema aangemaakt waarin alle kleuren in mijn applicatie worden gebruikt zijn gedefinieerd:


Daarnaast heb ik ook voor het eerst CSS nesting toegepast. Dit vind ik erg fijn werken omdat het de code veel makkelijker leesbaar en geordend houd. Dit ga ik in de toekomst veel vaker toepassen in mijn projecten.