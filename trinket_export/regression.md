### Normalfordelte residualer
En måde at tjekke om man har brugt den rigtige model når man laver regression er ved at tjekke om residualerne er normalfordelte. Hvis det er tilfældet, kan man ikke finde en bedre model og det som er tilbage er rent tilfældighed. 

I simuleringen bruger vi at summen af en binomialfordeling er normalfordelt. x og y data bliver udskrevet nedenfor

<iframe src='https://trinket.io/embed/python/9b548fef149a?start=result' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

* Foretag lineær regression og undersøg om residualerne er normalfordelte.
* Prøv at lav om i modellen linje 24.

Når residualerne er normalfordelte kan man også bestemme konfidensintervaller for konstanterne i regressionen.

Det gøres i Maple med ```testLin(x,y)```

* Undersøg hvad usikkerheden er på a og b


Vi kan også teste hypotesen H0 at eks. a=0. p-værdien giver sandsynligheden for at H0 hypotesen er rigtig.

* Hvad siger testet om a-værdien.