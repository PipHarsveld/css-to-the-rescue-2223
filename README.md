# Interactieve vuurwerkshow | CSS to the Rescue 

## Week 1
### Opdracht
Ik heb ervoor gekozen om mij de aankomende weken bezig te houden met de interactieve vuurwerkshow, omdat deze opdracht heel vrij is en ik hiermee veel kan experimenteren met CSS. Ik heb nog niet meteen een heel duidelijk beeld van heb mijn vuurwerkshow eruit zou moeten zien, maar daar zit bij deze opdracht ook de kracht in; het vuurwerk gaat zich vormen door te doen en fouten te maken. Wel wil ik naast het vuurwerk iets gaan doen met een light/darkmode switch, waarbij het vuurwerk alleen zichtbaar is wanneer het donker is, en wil ik dat de gebruiker invloed heeft op de vuurwerkshow door een aantal dynamiet ontstekers (detonators) te maken, die allemaal ander vuurwerk laten zien wanneer de gebruiker erop drukt.

### CSS technieken
Voor mijn vuurwerkshow wil ik meerdere CSS technieken uitproberen. Ik heb er al een aantal bedacht die ik sowieso wil gebruiken en waar ik mee wil beginnen, maar ik weet zeker dat die lijst blijft groeien wanneer ik eenmaal ga beginnen. Dit zijn een paar technieken waar ik mee wil beginnen:
* Animations - Ik wil beginnen met het opfrissen van mijn animation kennis. Dit is alweer een tijdje geleden maar wel een belangrijke basis voor vuurwerk.
* Halftone Patterns - Ik een afbeelding tonen in de stipjes van een halftone pattern, wat op die manier gezien kan worden als vuurwerk.
* Path animations (Offset-path) - Ik wil vormen van vuurwerk een bepaald path laten volgen

### Grootste uitdagingen
Ik wil zelf altijd een heel goed beeld heben van wat ik ga maken en precies weten hoe het eruit moet komen te zien, voor ik ergens aan begin. Juist bij deze opdracht vormt het eindresultaat door het proberen, experimenteren en fouten maken waardoor ik niet kan beginnen met een compleet vooruitgedacht plan. Dat is voor mij wel een uitdaging, maar dat is dan ook de reden dat ik voor deze opdracht heb gekozen.

### Experimenten
[Codepen - proces na de eerste week](https://codepen.io/pipharsveld/pen/rNZLWzx)
#### Basis animatie met emoji
Ik ben begonnen met het opfrissen van mijn kennis van animations, en om hier weer even in te komen heb ik een hele simpele animatie gemaakt van een emoji die de lucht in schiet en vervolgens vervaagd. Dit is de basis van elke vuurpijl, dus vond ik het handig om daar te beginnen. Toen dit eenmaal gelukt was heb ik een begin gemaakt aan het landschap waar de vuurwerkshow zich afspeeld. Later ga ik dit nog verder uitbereiden.

#### Eerste vuurpijl
Ik vond het lastig om te bedenken hoe je ervoor kon zorgen dat de vuurpijl in het begin een stipje is, en pas op een bepaald punt in de lucht uit elkaar zou spatten tot vuurwerk. Om een idee op te doen over hoe ik dit zou kunnen aanpakken ben ik gaan zoeken naar voorbeelden en technieken, en daar heb ik een interessante tutorial gevolgd. Hierbij maak je een section met daarin een stipje door het gebruiken van een radial-gradient. In de section plaats je dan meerdere stipjes op verschillende plekken in de vorm van het uiteengespatte vuurwerk. Vervolgens maak je deze section heel klein (waardoor alle stipjes zo dicht bij elkaar komen dat het één stip lijkt) en ga je deze animeren. Tijdens de animatie geef je een bepaald punt mee waarop je wil dat de vuurpijl overgaat in het vuurwerk en vergroot je dan de width en height van de section.

#### Vuurwerkshow starten bij donker thema
Het leek mij leuk dat de vuurwerkshow alleen zou starten in het donker, en dat de gebruiker dit kan beïnvloeden door de thema instellingen van zijn browser aan te passen. Ik heb dit gedaan door `@media (prefers-color-scheme: dark)` te gebruiken en daarin de animatie aan te roepen. Voor de gebruiksvriendelijkheid is het natuurlijk wel belangrijk dat de gebruiker weet dat de show alleen begint in een donker thema, dus heb ik een paragraaf element toegevoegd met de tekst "Zet je browserinstellingen naar darkmode om van de vuurwerkshow te genieten", die d.m.v. `display: none` onzichtbaar wordt in de darkmode.

## Week 2
### 'Mislukte' experimenten
Toen ik begon met het maken van de ontstekers, heb ik dit gedaan met het `<button>` element. Later, toen ik ervoor wilde zorgen dat het indrukken van de button een vuurpijl zou activeren, kwam ik erachter dat dit met het button element niet ging zonder javascript. Ik heb toen de button omgezet in een `<input type="checkbox"`, waarmee ik de vuurpijl wel af kon laten gaan door de animatie te zetten op `body:has(label:first-of-type > input:checked)`.

### Nieuwe inzichten
- Ik heb eigenlijk heel weinig gewerkt met animaties, dus daar wilde ik tijdens dit vak handiger in worden. Ik heb hier dan ook mee gespeeld en elke vuurpijl bevat een animatie.
- Het leek mij leuk om de animatie alleen te starten als de gebruiker zijn browser in een donker thema heeft staan. Ik ben gaan onderzoeken hoe ik dit het beste kon aanpakken en heb dat gedaan met `prefers-color-scheme: dark`, en daarin heb ik de animatie geplaatst. De animaties gaan dus alleen starten als het browserthema donker is, dan veranderen de kleuren van het landschap ook.
- Voor het maken van de vuurwerkshow heb ik ook `calc()` gebruikt, wat ik eerder eigenlijk nog nooit gedaan had. Na een uitleg van Sanne over de mogelijkheden van calc wilde ik hier ook iets mee doen en dat heb ik dan ook gebruikt voor het positioneren van de hendels van de ontsteker.
- Met `:before` en `:after` werken was ook niet iets wat ik eerder had gedaan, normaalgesproken maakte ik dan een container met daarin meerdere children die ik een andere styling gaf, maar ik heb nu geleerd dat het beter is om een item wat bij elkaar hoort te stylen met behulp van :before en :after. Voor het maken van de ontstekers heb ik het hendel gemaakt met :before en :after en zo is de ontsteker gemaakt met één html tag i.p.v. een container met drie children.
- Tijdens een gastcollege in de les heb ik gehoord over de `:has` selector en de mogelijkheden daarvan. Ik vond het nog wel lastig om te bedenken waar ik dit allemaal zou kunnen toepassen, maar voor het activeren van de ontstekers heb ik dit wel kunnen gebruiken. De ontstekers zijn radiobuttons die ik de animatie laat uitvoeren als de checkbox gecheckt, oftewel ingedrukt, is. Ik doe dit met `body:has(label:first-of-type > input:checked)`.
- Tot slot heb ik nog met veel selectoren gewerkt. Ik gebruikte voor dit vak al redelijk wat selectoren, maar wel de basis als `:first-of-type` en `:nth-of-type()`. Voor het maken van de vuurwerkshow wilde ik hier wat meer mee experimenteren, waar dat nuttig was uiteraard. Voor het maken van de bergen wilde ik de laatste 3 `<div>` selecteren, maar ik wist nog niet hoe veel divs daarvoor zouden komen en dus moest het dynamisch zijn. Ik heb dit toen gedaan door de selector `section:nth-of-type(2)>div:nth-last-child(-n+3)`. Deze selctor gaat in de tweede section opzoek naar de laatste drie divs. Door `(-n+3)` wordt voor n elke keer een hoger getal ingevuld en worden dus de eerste drie divjes geselcteerd. Door daar weer `div:nth-last-child` voor te zetten worden niet de eerste drie maar de laatste drie geselecteerd.
- Voor het maken van de bergen wilde ik driehoeken maken, maar ik wist niet hoe ik dit het beste kon aanpakken. Na wat zoeken ben ik erachter gekomen dat je dit kan doen door een div een hight en width van 0 te geven, en die vervolgens drie borders te geven. Door de hight en width van 0 komen de borders tegen elkaar en door 3 borders te gebruiken wordt het een driehoek.

### Wat ga ik vaker gebruiken
Ik heb tijdens deze twee weken veel nieuwe mogelijkheden en snufjes van CSS geleerd, alleen had ik ze nog meer willen toepassen. Tijdens dit vak heb ik geleerd wat je allemaal kan doen met dingen als `calc()`, `:before` en `:after`, animaties, `:has` en de wat specialere selectoren, en hier wil ik dan ook in nog volgende projecten meer gebruik van gaan maken. 



## Themasessies
### Typografie | 22-02-2023
Ik was aan de late kant met inschrijven voor de themasessies van vandaag, en dus waren de opties die nog beschikbaar waren niet meteen heel relevant voor mijn idee met de vuurwerkshow. Ik heb mij toen ingeschreven voor de themasessie typografie, omdat ik ook een idee had om vuurwerk in de vorm van een letter of tekst te maken. Ik ben toen met Vasillis over dit idee gaan sparren en kwamen toen tot de conclusie dat dit niet mogelijk is met typografie properties, maar dat ik dit zou kunnen aanpakken door een letter te scalen, meerdere emoji's uit elkaar te laten spatten (emoji's zijn ook typografie!), een letter een gradient te geven die een andere richting op schuift dan de letter of iets te animeren over een path (in de vorm van een letter). Kortom, genoeg opties om dit aan te pakken. Vooral iets animeren over een path sprak mij erg aan, dus daar ga ik tijdens de themasessie van morgen meer over leren.

### Paden animeren | 23-02-2023
Lijn tekenen in illustrator, daarna naar svgomg

svgomg --> markup --> path --> code gebruiken bij offset-path

M is het beginpunt

Cubic bezier (?) = vloeiende lijn in bijv illustrator, in svg is dit een letter C

```
@keyframe{
    100%{
        offset-distance: 100% <!--In hoeverre de animatie het pad volgt--> 
    }
}
```

Je kan het pad ook tijdens de animatie veranderen

Hoe animeert het over het path:
* `auto`: volgt precies het path
* `45deg`: object draait 45 graden en blijft op zelfde positie
* `auto 45deg`: object volgt het pad en eindigd 45 graden gedraaid

Anker waardes van de animatie veranderen
offset-anchor: anchorX anchorY;

Get moving (or not) with css motion path van daniel wilson

Teken je path niet te groot, de paths zijn niet schaalbaar

Clipping en masking van css tricks om de achtergrond achter het object te laten animeren

On hover kan je het path veranderen 

### Container Queries | 23-02-2023
Bij media queries wordt er gekeken naar de breedte van het scherm, bij container querties wordt gekeken naar de breedte van een bepaald element.

cqw is een unit die je kan gebruiken voor schaalbaarheid.

```
section{
    container-type: inline-size;
    container-name: testje;
    <!-- Shortcut: -->
    container: testje / inline-size;
}

@container testje (min-width: 500px){
    color: hotpink;
}
```
