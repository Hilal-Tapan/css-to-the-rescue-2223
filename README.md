# Css to the rescue
Hilal Tapan

## Docenten
- Vasilis van Gemert
- Sanne 't Hooft

## Debrief
Het doel van deze cursus is om te experimenteren met CSS om iets leuks te ontwikkelen. Er zijn vier thema's om uit te kiezen voor deze opdracht:
* Een modulair bedieningspaneel
* Een interactieve vuurwerkshow
* Een 3D Rubiks kubus
* Een Tailwind-project converteren naar moderne CSS.

Als eerste trok de kubus me erg aan omdat ik nog nooit met 3d had gewerkt maar toen ik hoorde dat je hier een rekenwonder voor moet zijn ben heb ik toch maar de interactieve vuurwerkshow gekozen. Bij dit project zal ik kijken naar de mogelijkheden van CSS en de nieuwe functies die we hebben geleerd de afgelopen weken. Tijdens dit project zal ik zoveel mogelijk van mijn proces proberen vast te leggen.

Het is de bedoeling dat we echt alleen HTML en CSS gebruiken, Javascript is verboden! ID's en Classes zijn ook verboden, dit is om goed te oefenen met de CSS selectoren. Als laatste is het de bedoeling dat we het lekker interactief maken.

***

## Leerdoelen
Er zijn een aantal dingen waar ik mee aan de slag wil gaan en beter in wil worden:
* Meer leren over :has, je kan hier namelijk ontzettend veel mee
* Container queries uitproberen
* Pixel art leren maken met css
* Nette CSS schrijven 

*** 

## Proces
### Week 1
In Week 1 ben ik begonnen met brainstormen naar vuurwerk ideeen. Ik wist dat ik sowieso al een hele tijd pixel art wou uitproberen dus vond dit een goed moment om dit te doen! Pixel vuurwerk zie je ook niet zo snel dus werd al gauw enthousiast hiervan. Ik begon met schetsen maken en een plan op stellen voor de HTML. 

![schets 1](https://github.com/Hilal-Tapan/css-to-the-rescue-2223/blob/main/Css-to-the-rescue/images/schets1.jpg)
![schets 2](https://github.com/Hilal-Tapan/css-to-the-rescue-2223/blob/main/Css-to-the-rescue/images/schets%202.jpg)
![schets 3](https://github.com/Hilal-Tapan/css-to-the-rescue-2223/blob/main/Css-to-the-rescue/images/schets%203.jpg)

### Week 2
In Week 2 ben ik begonnen aan de CSS. Ik begon met een pixel art show. Ik had deze volledig gemaakt in pixels en toen kwam ik erachter dat ik hem niet kon animeren. Hiervoor benaderde ik Sanne en die had een [codepen](https://codepen.io/shooft/pen/YzOPBXM) gemaakt die ik als voorbeeld heb gebruikt met de pixel art keyframes.

![Eerste versie pixel](https://github.com/Hilal-Tapan/css-to-the-rescue-2223/blob/main/Css-to-the-rescue/images/eerste-versie.png)

Daarnaast ben ik in deze week verder gegaan met de andere twee vuurwerk shows en heb hier veel lol mee gehad.

### Week 3
Week 3 ben ik verder gegaan met de styling. Hier heb ik container queries en :has uitgeprobeerd om het interactief te maken. 
De :has ging best wel goed, ik denk ook door de mini cursusjes waar het is behandeld. De container querie lukte me niet helaas. 
``` 
section:nth-of-type(1):has(:checked) > div div{
  position: absolute;
  width: .1em;
  aspect-ratio: 1/1;
  background-color: var(--color-yellow);
  filter: drop-shadow(-.2em -1em .1em var(--color-orange));
  box-shadow: 0 0 0 1px var(--color-red);
  animation: vuurwerk1 1s ease-out infinite;
  animation-fill-mode: forwards;
} 
```

### Week 4
In week 4 ben ik alles gaan fine tunen en heb ik extra interactie toegevoegd. Ik heb een manual light/dark mode toegevoegd die de gebruiker kan aanklikken. Ook ben ik aan de slag gegaan met mediaqueries omdat container queries niet echt lukte. Bij het kleiner maken van het scherm veranderen de border colors.

```
@media screen and (prefers-color-scheme: light) {
	:has(div > label input:checked) {
    --color-black:darkblue;
    --color-darkblue:lightblue;
    --color-purple:pink;
	}	
}

@media screen and (prefers-color-scheme: dark) {
	:has(div > label input:checked) {
    --color-black:darkblue;
    --color-darkblue:lightblue;
    --color-purple:pink;
	}	
}
```

*** 

## Wat ging goed?
Pixel art maken ging super goed. Ik heb er ook veel lol bij gehad en soms was ik er uren mee bezig aan een stuk door zonder dat ik het doorhad. Ik kon hier echt me creativiteit in kwijt. 
Daarnaast ging de :has ook goed. Ik heb wel ff geknoeid bij de manual light/dark mode maar uiteindelijk was dat ook gelukt.
Ik heb ook voor mijn idee best nette CSS geschreven. Normaal doe ik de custom properties pas achteraf maar dit keer ben ik hier in het begin mee begonnen. De structuur van me bestand vind ik ook best netjes opgebouwd en kan goed me weg erin vinden.

![Vuurwerkshow 1](https://github.com/Hilal-Tapan/css-to-the-rescue-2223/blob/main/Css-to-the-rescue/images/vuurwerkshow%201.png)
![Vuurwerkshow 2](https://github.com/Hilal-Tapan/css-to-the-rescue-2223/blob/main/Css-to-the-rescue/images/vuurwerkshow2.png)

***

## Wat ging minder goed?
De container queries gingen minder goed. Ik heb hier best mee geknoeid en kwam er gewoon niet uit dus heb het gelaten voor wat het is. 
Daarnaast had ik in het begin dat me achtergrond gradient zichzelf bleef repeaten maar later kwam ik erachter dat ik hem op 100% moest zetten.
![repeating gradient](https://github.com/Hilal-Tapan/css-to-the-rescue-2223/blob/main/Css-to-the-rescue/images/gradient%20is%20repeating.png)


*** 

## Aantekeningen mini cursusjes
### Vormpjes maken
Pixel art
Dit doe je met box-shadow solid maken en van positie veranderen steeds
https://codepen.io/shooft/pen/XWPJrzo

Gradient om cirkel te maken
https://codepen.io/shooft/pen/MWqYgRZ

### :Has
:has (handig voor interactief maken zonder javascript)
Hier selecteert die alle p’s binnen alle sections
Section:has(p){
}

Hier selecteert die alle h1’s die die een p erna hebben
H1:has(+p)

Hier selecteert die alle h1’s met de class een classje
H1:has(.eenclassje)

Hier selecteert die de body wanneer de body met id decor gecheckt is
Body:has(#decor:checked){
}

Hier selecteert die de img wanneer de body met steen id gecheckt is
Body:has(#steen:checked) img {
}

:has met dropdown
Dropdown met <option>

Hier veranderd die de body als je de rode optie aanklikt
Body:has( option[value=“red”]:checked ) {
}

### Keyframes
Css ceasar is om te kijken hoe je de ease-in-out etc wil.

### Filters
Je kan filters chainen, hierin maakt de volgorde uit in wat je het zet.
filter: blur(2px) grayscale(100%);
Hier blurt die eerst daarna grayscaled die.

Filter is soms mooier dan dropshadow want hij gaat dan om de png vorm heen.
Filter:dropshadow(1em 1em o black);

Wanneer je een donkere achtergrond hebt kan je 
filter:brightness(.75) gebruiken op een element 
om het wat prettiger voor je ogen te maken.

Hiermee kan je een element wit maken door de invert.
Filter:grayscale(1) brightness(0) invert(1);

Filter:hue-rotate(90deg);
Hiermee kan je de kleuren veranderen op de kleuren ladder van een element.

Neon kan je dus ook maken met filters

H2{
Backdrop-filter:blur(10px) 
}.  -> dit maakt het element erachter blurred waardoor bijv een text meer zichtbaar is
Je kan deze backdrop-filter met alle filter opties gebruiken

***

## Gastsprekers
**Killian Valkhof**
Polypane kan je een jaar gratis gebruiken als student zijnde.
- Choose the least powerful language suitable for a given purpose.

Toegankelijkheid
Doe outline-color: transparent ipv none. Hierdoor kan je bij toegankelijkheid van extra contrast die outline contrastvol maken.

Input type =“color”
Hiermee kan je een colorpicker op je browser scherm krijgen

Scroll-behaviour:smooth -> hiermee scroll je smooth

Backdrop kan je gebruiken voor javascript vrije pop up scherm

**Manuel**
Heeft een project 100 dagen bloggen van CSS.
- frontend-ontwikkelaar
- fan van css
- :has & container-query's

Zijn favoriete eigenschappen:
- rgb zonder komma of schuine streep
- kleurenschema met mediaquery's
- accentkleuren
- kleurlettertypen

*** 

## bronnen
containerqueries: 
* https://www.youtube.com/watch?v=rrLAg7xNERA
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries 
* https://medium.com/markdown-monster-blog/getting-images-into-markdown-documents-and-weblog-posts-with-markdown-monster-9ec6f353d8ec 
* https://developer.mozilla.org/en-US/docs/Web/CSS/:has 
* https://css-tricks.com/a-complete-guide-to-dark-mode-on-the-web/
* https://codepen.io/shooft/pen/YzOPBXM 
