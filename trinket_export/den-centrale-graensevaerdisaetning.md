# Den central grænseværdisætning
Igen ifølge Den Store Danske

"Den centrale grænseværdisætning, det hovedresultat i sandsynlighedsregning, der udsiger, at summen **Sn** af **n** uafhængige, tilfældige tal med samme fordeling (middelværdi og varians) har en asymptotisk fordeling, der er en normalfordeling."

Vi tager igen udgangspunkt i møntkastet som har den binomialfordelte variabel, **X**.

## Uafhængige variable
Simuleringen giver to serier med samme sandsynlighedsparameter men forskellig antalsparametre.


<iframe src='https://trinket.io/embed/python/19ac55c975?start=false' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

### Øvelse
* Undersøg visuelt forskellen på middelværdi og spredning for det to dataserier.
* Kopier data, vælg i linje 24-25 hvad I vil printe, ind i Maple.
* Undersøg om data er normalfordelt og hvad middelværdien og spredningen er.


## Afhængige variable
I **Den Centrale Grænseværdisætning** er et af kravene at udfaldende af de enkelte forsøg skal være uafhængige. Vi vil undersøge dette krav ved at generere data som er afhængigt. Det er igen gennemsnit af 100 binomialfordelte realisationer med antalsparamter, n=100 og sandsynlighedsparameter p=0.5. De blå er uafhængige mens de røde er afhængige. Afhængigheden er lavet så en succes, krone, ændrer sandsynligheden for at næste bliver krone med 0.002. Ved plat bliver sandsynligheden for plat også ændret med 0.002. 

I denne simulation bliver afhængigheden nulstillet efter 100 kast, så sanfsynligheden igen starter på p=0.5.

<iframe src='https://trinket.io/embed/python/201e87a52e?start=false' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>
### Øvelse
* Kør programmet og undersøg hvad sandsynlighedsparametren og antalsparametren er i de to tilfælge.
* Hvad er foreksellen på de to serier.
* Argumenter ud fra den centrale grænseværdisætning for at de røde ikke er normalfordelte.

## Undersøgelse af data
Hvis I kopierer data ind i Maple kan I undersøge det, eks. med disse kommandoer
```
with(Statistics):
with(Gym):


HX := Histogram(X, transparency = 0.2):
HY := Histogram(Y, color = "red"):
HXF := DensityPlot(Normal(Mean(X), sqrt(Variance(X))), range = 0 .. 1, color = "black"):
HYF := DensityPlot(Normal(Mean(Y), sqrt(Variance(Y))), range = 0 .. 1, color = "black"):
plots[display](HX, HXF, HY, HYF)

```
kommer dette fine histogram
![HistogramBinomialfordeltVatiabel.jpg](billeder/histogrambinomialfordeltvatiabel.jpeg "HistogramBinomialfordeltVatiabel.jpg")
### Øvelse
* Prøv selv at lav histogram og fortolk på om data er normalfordelt.
* Prøv at lav om på hvordan **p** bliver opdateret så effekten ikke er helt så voldsom.
* Vælg en opdatering af **p** værdien så du visuelt ikke kan se at data ikke er normalfordelt. Lav et QQplot og argumenter ud fra det for at data ikke er normalfordelt.
* Hvad sker der med spredningen når variablene er korrelerede (ikke uafhængige)?


### Finanskrisen i 2008
Gary Crittenden, Citi’s chief financial officer, hævdede at firmaet havde været udsat for en 25 sigma event,
"Apparently, as of September 30th, Citigroup’s subprime portfolio was worth
every penny of the $55 billion that Citi’s models said it was worth. Then,
whoa, in came one of those 25-sigma events" [Dowd, https://arxiv.org/pdf/1103.5672.pdf].

Dette var selvfølgeligt ud fra en antagelse om at kurserne på subprime lån var uafhængige og derfor normalfordelte.

### Øvelse
* Beregn hvor usandsynlig en 25 sigma event er ved normalfordelte variable.
* Argumenter for at Gary Crittender ikke tog højde for, at kurserne på subprime lånene nok ikke var uafhængige. 



