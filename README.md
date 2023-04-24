# CCS To The Rescue

## Interactive control panel

Om mijn interactive control panel te gebruiker ga je naar [https://jimflament.github.io/css-to-the-rescue-2223/](https://jimflament.github.io/css-to-the-rescue-2223/) en dan kan je spelen met de controls die beschikbaar zijn.

Voor deze course heb ik een interactive control panel gemaakt. Ik had nog weinig kennis van css en ben begonnen met het leren omgaan met selectoren, na wat gedoe ging het lampje bij me branden en kon ik duidelijk HTML tags selecteren zonder het gebruik van id’s of classes.

In de 2e week ben ik begonnen met het leren van grid om een scherm en controls een vaste plek te geven op het scherm. Daarna ben ik :has gaan leren wat en dat duurde wel even voordat ik dat door had.

In week 3 heb ik mij verdiept in animaties om elementen op het scherm te animeren doormiddel van :has om de animaties te starten. Daarnaast heb ik ook gekeken naar gradients en hoe die zijn opgebouwd om later te gebruiken.

Met deze nieuwe kennis heb ik in week 3 en 4 een nieuw control panel gebouwd die animaties liet zien doormiddel van interacties me de knoppen.

## Switch

Ik ben begonnen met het maken van een switch. Deze switch is gemaakt doormiddel van een checkbox met een label waarin een div staat. Ik heb gekozen voor een simple aan uit switch die je vaak terug ziet in de UI van een IPhone. Als je op de switch klikt speelt er een animatie die de achtergrond kleur veranderd en een animatie die het bolletje verplaatst.

![Scherm­afbeelding 2023-03-09 om 11.17.34.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.17.34.png)

![Scherm­afbeelding 2023-03-09 om 11.17.42.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.17.42.png)

Hieronder vind je de code die ik heb gebruikt om de switch te maken.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div></div>
    <form>
        <label for="switch"><div></div></label>
        <input type="checkbox" id="switch">
    </form>
    <form>
        
    </form>
    <form>

    </form>
</body>
</html>
```

```css
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
body{
    width: 100vw;
    height: 100vh;
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(6, 1fr);
}
input{
		display: none;
}
/* Screen */
div:nth-of-type(1){
    grid-column: 1 / 7;
    grid-row: 1 / 5;
    background-color: antiquewhite;
}
/* switch */
form:nth-of-type(1){
    grid-column: 1 /3;
    grid-row: 5 / 7;
    background-color: lightgray;
    border: 5px solid black;

    display: flex;
    justify-content: center;
    align-items: center;
}
form:nth-of-type(1) > label{
    height: 200px;
    width: 100px;
    background-color: red;
    border-radius: 100px;

    display: flex;
    justify-content: center;
    align-items: end;
}
form:nth-of-type(1) > label > div{
    height: 90px;
    width: 90px;
    background-color: white;
    border-radius: 100%;
    margin-top: 10px;
    margin-bottom: 10px;
}
body :has(#switch:checked) label:nth-of-type(1){
    animation: switchOn 0.2s ease-in 1 normal forwards;
}
body :has(#switch:checked) div:nth-of-type(1){
    animation: switchUp 0.2s ease-in 1 normal forwards;
}
body :has(#switch:not(:checked)) label:nth-of-type(1){
    animation: switchOff 0.2s linear 1 normal forwards;
}
body :has(#switch:not(:checked)) div:nth-of-type(1){
    animation: switchDown 0.2s linear 1 normal forwards;
}
/* Animations */
@keyframes switchOn{
    from{background-color: red;}
    to{background-color: rgb(0, 226, 19);}
}
@keyframes switchOff{
    from{background-color: rgb(0, 226, 19);}
    to{background-color: red;}
}
@keyframes switchUp{
    from{transform: translateY(0px);}
    to{transform: translateY(-90px);}
}
@keyframes switchDown {
    from{transform: translateY(-90px);} 
    to{transform: translateY(0px);}
}
```

## Draaiknop & gradient

Toen de switch af was ben ik begonnen met het bouwen van een draaiknop. De draaiknop is opgebouwd uit een div met daarin 4 radio buttons. De div bestaat uit een grid waardoor ik de plaatsing van de radio buttons kon bepalen en de knop op 4 verschillende plaatsen kon activeren.

Het kleine ronde op de bolletje geeft de huidige draai positie van de knop aan. Het bolletje veranderd van plek door te drukken op de radio button boven, recht, onder, of links. De radio button is niet zichtbaar maar als je op de draai knop staat met je muis en je komt op een radio button dan veranderd je cursor naar een pointer. 

![Scherm­afbeelding 2023-03-09 om 11.22.16.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.22.16.png)

![Scherm­afbeelding 2023-03-09 om 11.22.28.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.22.28.png)

![Scherm­afbeelding 2023-03-09 om 11.35.41.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.35.41.png)

![Scherm­afbeelding 2023-03-09 om 11.35.50.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.35.50.png)

Toen ik de draaiknop draaiend had gekregen heb ik aan elke radio button een animatie toegevoegd die verschillende gradients weergeeft of het weergave scherm.

![Scherm­afbeelding 2023-03-09 om 11.46.32.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.46.32.png)

Hieronder vind je de code voor de draaiknop en gradients

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <section>
        <div></div>
    </section>
    <form>
        <label for="switch"><div></div></label>
        <input type="checkbox" id="switch">
    </form>
    <form>
        <div>
            <input type="radio" name="dial" id="dialUp">
            <input type="radio" name="dial" id="dialRight">
            <span></span>
            <input type="radio" name="dial" id="dialDown">
            <input type="radio" name="dial" id="dialLeft">
        </div>
    </form>
    <form>

    </form>
</body>
</html>
```

```css
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
body{
    width: 100vw;
    height: 100vh;
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(6, 1fr);
}
form:nth-of-type(1) > input{
    display: none;
}
input[type=radio]{
    opacity: 0;
    cursor: pointer;
}
/* Screen */
section{
    grid-column: 1 / 7;
    grid-row: 1 / 5;
    background-color: antiquewhite;
    display: flex;
    justify-content: center;
    align-items: center;

}
section div{
    width: 300px;
    height: 300px;
    background-color: violet;
}
/* switch */
form:nth-of-type(1){
    grid-column: 1 /3;
    grid-row: 5 / 7;
    background-color: lightgray;
    border: 5px solid black;

    display: flex;
    justify-content: center;
    align-items: center;
}
form:nth-of-type(1) > label{
    height: 200px;
    width: 100px;
    background-color: red;
    border-radius: 100px;

    display: flex;
    justify-content: center;
    align-items: end;
}
form:nth-of-type(1) > label > div{
    height: 90px;
    width: 90px;
    background-color: white;
    border-radius: 100%;
    margin-top: 10px;
    margin-bottom: 10px;
}
body :has(#switch:checked) label:nth-of-type(1){
    animation: switchOn 0.2s ease-in 1 normal forwards;
}
body :has(#switch:checked) div:nth-of-type(1){
    animation: switchUp 0.2s ease-in 1 normal forwards;
}
body :has(#switch:not(:checked)) label:nth-of-type(1){
    animation: switchOff 0.2s linear 1 normal forwards;
}
body :has(#switch:not(:checked)) div:nth-of-type(1){
    animation: switchDown 0.2s linear 1 normal forwards;
}
/* Dial */
form:nth-of-type(2){
    grid-column: 3 /5;
    grid-row: 5 / 7;
    background-color: lightgray;
    border: 5px solid black;

    display: flex;
    justify-content: center;
    align-items: center;
}
form:nth-of-type(2) > div{
    width: 200px;
    height: 200px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    border-radius: 100%;
    background-color: antiquewhite;
}
span{
    width: 20px;
    height: 20px;
    background-color: black;
    grid-column: 2 / 3;
    grid-row: 2 / 3;
    justify-self: center;
    border-radius: 100%;
    margin: 5px;
    align-self: center;
    transform: translateY(-80px);
}
input[type=radio]:nth-of-type(1){
    grid-column: 2 / 3;
    grid-row: 1 / 2;
}
input[type=radio]:nth-of-type(2){
    grid-column: 3 / 4;
    grid-row: 2 / 3;
}
input[type=radio]:nth-of-type(3){
    grid-column: 2 / 3;
    grid-row: 3 / 4;
}
input[type=radio]:nth-of-type(4){
    grid-column: 1 / 2;
    grid-row: 2 / 3;
}
form:nth-of-type(3){
    grid-column: 5 /7;
    grid-row: 5 / 7;
    background-color: lightgray;
    border: 5px solid black;
}
body :has(#dialUp:checked) span{
    animation: dialUp 0.5s linear 1 normal forwards ;
}
body :has(#dialRight:checked) span{
    animation: dialRight 0.5s linear 1 normal forwards ;
}
body :has(#dialDown:checked) span{
    animation: dialDown 0.5s linear 1 normal forwards ;
}
body :has(#dialLeft:checked) span{
    animation: dialLeft 0.5s linear 1 normal forwards ;
}
body:has(#dialRight:checked) section{
    animation: gradient1 3s linear 1 alternate both;
}
body:has(#dialDown:checked) section{
    animation: gradient2 3s linear 1 alternate both;
}
body:has(#dialLeft:checked) section{
    animation: gradient3 3s linear 1 alternate both;
}
/* Animations switch */
@keyframes switchOn{
    from{background-color: red;}
    to{background-color: rgb(0, 226, 19);}
}
@keyframes switchOff{
    from{background-color: rgb(0, 226, 19);}
    to{background-color: red;}
}
@keyframes switchUp{
    from{transform: translateY(0px);}
    to{transform: translateY(-90px);}
}
@keyframes switchDown {
    from{transform: translateY(-90px);} 
    to{transform: translateY(0px);}
}
/* Animations dial */
@keyframes dialRight {
    from{transform: rotate(0deg)
                  translateY(-80px);}
    to{transform: rotate(90deg)
                  translateY(-80px);
}
}
@keyframes dialDown {
    from{transform: rotate(90deg)
                  translateY(-80px);}
    to{transform: rotate(180deg)
                  translateY(-80px);
}
}
@keyframes dialLeft {
    from{transform: rotate(180deg)
                  translateY(-80px);}
    to{transform: rotate(270deg)
                  translateY(-80px);
}
}
@keyframes dialUp {
    from{transform: rotate(270deg)
                  translateY(-80px);}
    to{transform: rotate(360deg)
                  translateY(-80px);
}
}
/* Gradient animations */
@keyframes gradient1 {
    0%{background-image: linear-gradient(to right, blue, green);}
    25%{background-image: radial-gradient(circle, pink, purple);}
    50%{background-image: repeating-linear-gradient(to right, red, yellow 10%, green 20%);}
    75%{background-image: conic-gradient(red, yellow, green);}
    100%{background-image: linear-gradient(to right, red, yellow);}
}
@keyframes gradient2 {
    0%{background-image: linear-gradient(to left, purple, orange);}
    25%{background-image: radial-gradient(circle, rgb(26, 172, 216), rgb(192, 40, 52));}
    50%{background-image: repeating-linear-gradient(to bottom, rgb(0, 255, 102), yellow 10%, rgb(128, 0, 115) 20%);}
    75%{background-image: conic-gradient(rgb(29, 142, 81), rgb(216, 216, 122), rgb(53, 0, 128));}
    100%{background-image: linear-gradient(to right, rgb(0, 200, 255), rgb(255, 0, 144));}
}
@keyframes gradient3 {
    0%{background-image: linear-gradient(to right, rgb(0, 255, 102), rgb(210, 165, 3));}
    25%{background-image: radial-gradient(circle, rgb(159, 26, 48), rgb(0, 49, 128));}
    50%{background-image: repeating-linear-gradient(to right, rgb(82, 150, 8), rgb(158, 66, 216) 10%, rgb(18, 218, 18) 20%);}
    75%{background-image: conic-gradient(rgb(156, 14, 14), rgb(18, 143, 103), rgb(49, 229, 49));}
    100%{background-image: linear-gradient(to right, rgb(25, 144, 4), rgb(181, 7, 36));}
}
```

## Switch vierkant animatie

Ik wilde graag nog iets van een animatie koppelen en de switch, er zat al een zichtbare animatie in de switch zelf maar ik wilde graag dat de switch iets deed. Ik ben me daarvoor gaan verdiepen in transform. Ik heb op het weergave scherm een vierkant gerenderd die alleen zichtbaar is als de switch aan staat. Als de switch aan staat zal het vierkantje ook allemaal rare bewegingen maken die ik heb gemaakt doormiddel van transform in een animatie. In de transform heb ik gebruik gemaakt van rotate, scale, skew en translate. 

![Scherm­afbeelding 2023-03-09 om 11.51.37.png](https://github.com/Jimflament/css-to-the-rescue-2223/blob/main/images/Scherm%C2%ADafbeelding%202023-03-09%20om%2011.51.37.png)

Hieronder vind je de code voor de vierkant animatie

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <section>
        <div></div>
    </section>
    <form>
        <label for="switch"><div></div></label>
        <input type="checkbox" id="switch">
    </form>
    <form>
        <div>
            <input type="radio" name="dial" id="dialUp">
            <input type="radio" name="dial" id="dialRight">
            <span></span>
            <input type="radio" name="dial" id="dialDown">
            <input type="radio" name="dial" id="dialLeft">
        </div>
    </form>
    <form>

    </form>
</body>
</html>
```

```css
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
body{
    width: 100vw;
    height: 100vh;
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(6, 1fr);
}
form:nth-of-type(1) > input{
    display: none;
}
input[type=radio]{
    opacity: 0;
    cursor: pointer;
}
/* Screen */
section{
    grid-column: 1 / 7;
    grid-row: 1 / 5;
    background-color: antiquewhite;
    display: flex;
    justify-content: center;
    align-items: center;

}
section div{
    width: 300px;
    height: 300px;
    background-color: violet;
}
/* switch */
form:nth-of-type(1){
    grid-column: 1 /3;
    grid-row: 5 / 7;
    background-color: lightgray;
    border: 5px solid black;

    display: flex;
    justify-content: center;
    align-items: center;
}
form:nth-of-type(1) > label{
    height: 200px;
    width: 100px;
    background-color: red;
    border-radius: 100px;

    display: flex;
    justify-content: center;
    align-items: end;
}
form:nth-of-type(1) > label > div{
    height: 90px;
    width: 90px;
    background-color: white;
    border-radius: 100%;
    margin-top: 10px;
    margin-bottom: 10px;
}
body :has(#switch:checked) label:nth-of-type(1){
    animation: switchOn 0.2s ease-in 1 normal forwards;
}
body :has(#switch:checked) div:nth-of-type(1){
    animation: switchUp 0.2s ease-in 1 normal forwards;
}
body :has(#switch:not(:checked)) label:nth-of-type(1){
    animation: switchOff 0.2s linear 1 normal forwards;
}
body :has(#switch:not(:checked)) div:nth-of-type(1){
    animation: switchDown 0.2s linear 1 normal forwards;
}
body:has(#switch:not(:checked)) section div{
    display: none;
}
body:has(#switch:checked) section div{
    animation: moveSquare 5s ease-in 1 normal forwards;
}
/* Dial */
form:nth-of-type(2){
    grid-column: 3 /5;
    grid-row: 5 / 7;
    background-color: lightgray;
    border: 5px solid black;

    display: flex;
    justify-content: center;
    align-items: center;
}
form:nth-of-type(2) > div{
    width: 200px;
    height: 200px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    border-radius: 100%;
    background-color: antiquewhite;
}
span{
    width: 20px;
    height: 20px;
    background-color: black;
    grid-column: 2 / 3;
    grid-row: 2 / 3;
    justify-self: center;
    border-radius: 100%;
    margin: 5px;
    align-self: center;
    transform: translateY(-80px);
}
input[type=radio]:nth-of-type(1){
    grid-column: 2 / 3;
    grid-row: 1 / 2;
}
input[type=radio]:nth-of-type(2){
    grid-column: 3 / 4;
    grid-row: 2 / 3;
}
input[type=radio]:nth-of-type(3){
    grid-column: 2 / 3;
    grid-row: 3 / 4;
}
input[type=radio]:nth-of-type(4){
    grid-column: 1 / 2;
    grid-row: 2 / 3;
}
form:nth-of-type(3){
    grid-column: 5 /7;
    grid-row: 5 / 7;
    background-color: lightgray;
    border: 5px solid black;
}
body :has(#dialUp:checked) span{
    animation: dialUp 0.5s linear 1 normal forwards ;
}
body :has(#dialRight:checked) span{
    animation: dialRight 0.5s linear 1 normal forwards ;
}
body :has(#dialDown:checked) span{
    animation: dialDown 0.5s linear 1 normal forwards ;
}
body :has(#dialLeft:checked) span{
    animation: dialLeft 0.5s linear 1 normal forwards ;
}
body:has(#dialRight:checked) section{
    animation: gradient1 3s linear 1 alternate both;
}
body:has(#dialDown:checked) section{
    animation: gradient2 3s linear 1 alternate both;
}
body:has(#dialLeft:checked) section{
    animation: gradient3 3s linear 1 alternate both;
}
/* Animations switch */
@keyframes switchOn{
    from{background-color: red;}
    to{background-color: rgb(0, 226, 19);}
}
@keyframes switchOff{
    from{background-color: rgb(0, 226, 19);}
    to{background-color: red;}
}
@keyframes switchUp{
    from{transform: translateY(0px);}
    to{transform: translateY(-90px);}
}
@keyframes switchDown {
    from{transform: translateY(-90px);} 
    to{transform: translateY(0px);}
}
/* Animations dial */
@keyframes dialRight {
    from{transform: rotate(0deg)
                  translateY(-80px);}
    to{transform: rotate(90deg)
                  translateY(-80px);
}
}
@keyframes dialDown {
    from{transform: rotate(90deg)
                  translateY(-80px);}
    to{transform: rotate(180deg)
                  translateY(-80px);
}
}
@keyframes dialLeft {
    from{transform: rotate(180deg)
                  translateY(-80px);}
    to{transform: rotate(270deg)
                  translateY(-80px);
}
}
@keyframes dialUp {
    from{transform: rotate(270deg)
                  translateY(-80px);}
    to{transform: rotate(360deg)
                  translateY(-80px);
}
}
/* Gradient animations */
@keyframes gradient1 {
    0%{background-image: linear-gradient(to right, blue, green);}
    25%{background-image: radial-gradient(circle, pink, purple);}
    50%{background-image: repeating-linear-gradient(to right, red, yellow 10%, green 20%);}
    75%{background-image: conic-gradient(red, yellow, green);}
    100%{background-image: linear-gradient(to right, red, yellow);}
}
@keyframes gradient2 {
    0%{background-image: linear-gradient(to left, purple, orange);}
    25%{background-image: radial-gradient(circle, rgb(26, 172, 216), rgb(192, 40, 52));}
    50%{background-image: repeating-linear-gradient(to bottom, rgb(0, 255, 102), yellow 10%, rgb(128, 0, 115) 20%);}
    75%{background-image: conic-gradient(rgb(29, 142, 81), rgb(216, 216, 122), rgb(53, 0, 128));}
    100%{background-image: linear-gradient(to right, rgb(0, 200, 255), rgb(255, 0, 144));}
}
@keyframes gradient3 {
    0%{background-image: linear-gradient(to right, rgb(0, 255, 102), rgb(210, 165, 3));}
    25%{background-image: radial-gradient(circle, rgb(159, 26, 48), rgb(0, 49, 128));}
    50%{background-image: repeating-linear-gradient(to right, rgb(82, 150, 8), rgb(158, 66, 216) 10%, rgb(18, 218, 18) 20%);}
    75%{background-image: conic-gradient(rgb(156, 14, 14), rgb(18, 143, 103), rgb(49, 229, 49));}
    100%{background-image: linear-gradient(to right, rgb(25, 144, 4), rgb(181, 7, 36));}
}
/* Square animation */
@keyframes moveSquare{
    0%{transform: 
        rotate(0deg)
        scale(1)
        skew(0deg, 0deg)
        translate(0px, 0px);}
    25%{transform: 
        rotate(20deg
        scale(0.5))
        skew(120deg, 200deg)
        translate(200px, 400px);}
    50%{transform: 
        rotate(40deg)
        scale(1)
        skew(240deg, -20deg)
        translate(100px, 50px);}
    75%{transform: 
        rotate(-60deg)
        scale(1.5)
        skew(0deg, -10deg)
        translate(-300px, -100px);}
    100%{transform: 
        rotate(360deg)
        scale(1)
        skew(0deg, 0deg)
        translate(0px, 0px);}
}
```
