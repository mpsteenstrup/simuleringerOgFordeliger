# Store tals lov
Ifølge Den store Dansk er store tals lov

"De store tals lov, fundamentalt resultat i sandsynlighedsregning, der siger, at hvis X1,X2,... er en uendelig følge af uafhængige, tilfældige tal med samme fordeling med middelværdi μ, vil gennemsnittet (X1+∙∙∙+Xn)/n for n gående mod uendelig konvergere mod μ. Fx vil i en uendelig serie af møntkast, hvor plat og krone er lige sandsynlige, hyppigheden af de kast blandt de første n, der viser krone, være tæt på 1/2 for n stor."


### Øvelse
* Beskriv hvad det betyder at tallene er tilfældige med samme fordeling.
* Beskriv hvad det betyder at de er uafhængige.
* Beskriv hvad det betyder at gennemsnittet konvergerer mod $\(\mu\)$.  

I praksis er det selvfølgeligt ikke muligt at have uendeligt mange observationer. 
Vi vil  i det efterfølgende undersøge hvad antagelsen om uafhængighed betyder for Store tals lov.


## Uafhængige variable
Programmet generere binomialfordelte variable, **X** og beregner gennemsnittet, **Xmean**.

<iframe src='https://trinket.io/embed/python/9c2b3db4f5?start=false' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

### Øvelse
* Kør programmet og beskriv i ord hvordan du kan se Store tals lov.
* Lav om i linje 22 så du får færre tal, hvornår gælder STL?
* Prøv at lav om på antals eller sandsynlighedsparametren og se om STL stadigt holder.
* Argumenter for at *X* kan fortolkes som sandsynligheden for krone.
* Kopier evt. data ind i Maple og tjek for normalfordeling.

## Afhængige variable
En af betingelserne for STL er at observationerne er uafhængige. I nedenstående simulation har vi tilføjet
```
if r<=p:
      x = x+1
      p +=0.0001
    else:
      p -=0.0001
```
sandsynligheden for krone, **p**, afhænger nu af om vi tidligere har fået krone. For hver krone bliver sandsynligheden 0.001 større mens den ved plat bliver 0.001 mindre. I simuleringen bliver **p** ført videre til næste stokastiske variabel, så den starter med en sandsynlighedsparameter som den forige sluttede med.

<iframe src='https://trinket.io/embed/python/3d0f7b8deb?start=false' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

### Øvelse
* Kør simuleringen og beskriv hvad du ser.
* Argumenter for hvorfor gennemsnittet ikke konvergerer mod en middelværdi.
* Undesøg hvor meget ændringen i **p** betyder for STL.
* Prøv at byt så en krone nu ændrer sandsynligheden negativt.



