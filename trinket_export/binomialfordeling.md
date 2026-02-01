#Binomialfordeling
Vi vil i dette afsnit lave simuleringer af den stokastiske vairable *X* som optæller antallet af succeser i ved *n* binære eksperimenter. Standardeksemplet er antallet af "krone" ved kast med en mønt *n* gange. Simuleringerne har den fordel at vi kan få computeren til at kaste mønten mange flere gange end vi selv gider og at vi kan ændre på sandsynlighedsparametren og lave falske mønter, hvor $( P(X=\text{"krone"})\neq 0.5  )$.

# Middelværgi og varians
Simuleringen svarer til at man har kastet en mønt 10 gange og optalt antal krone og så gentaget det 100 gange. Her er antalsparametren, $( n=10 )$, og sandsynlighedsparameteren, $(p=0.5)$.
<iframe src='https://trinket.io/embed/python/a4fd110225?start=false' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

* Kør programmet ved at trykke på play.
* Brug koordinatsystemet til at finde det maksimale og minimale antal krone.
* Kør programmet et par gange og se hvordan det ændrer sig.
* Nederst er data printet, kompier det over i Maple og lav et pindediagram.

Med pindediagrammet kan I se hvordan *X* fordeler sig med en *Middelværdi*, *Median* og *Spredning*.

* Undersøg hvad den mest sandsynlige værdi er *X* er og hvor sandsynlig den er.
* Vurder hvilke andre *X* værdier der også er sandsynlige.
* Prøv med øjemål at lægge et interval omkring middelværdien, $( \pm )$ spredning.
* Vurder hvor stor sandsynligheden er for at finde en *X* værdi inden for $( \pm )$ spredning fra midelværdien.
 

### Eksperiment med forskellig antalsparamter og sandsynlighedsparameter
Vi vil undersøge hvordan fordelingerne ændrer sig når antalsparametren og sandsynlighedsparametren ændrer sig. 

<iframe src='https://trinket.io/embed/python/4db41fdfbe?start=result' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>


I skal nu til undersøge hvilken betydning antalsparametren , *n*, har og selv ændre i koden. Det er vigtigt med variabelkontrol når man eksmperimenterer. Det betyder at de to fordelinger skal være helt ens på nær den variabel vi undersøger.
* lav om i programmet linje 18 så der står ```X.append(bin(100,0.5)) ``` og kør programmet, nu skulle de to fordelinger gerne være ens. Hvorfor er de ikke helt ens?
* Lav en undersøgelse hvor I ændrer på antalsparametren for *X*, eks. $( n = [1,10,40,100,200,1000,10000] )$. Noter middelværdi og spredning.
* Beskriv i ord hvordan spregningen ændrer sig når antalsparametren bliver større. Hvordan kan det ses grafisk?
* Lav to grafer, en *(n,middelværdi)* og en *(n,spredning)* og undersøg sammenhængen.
* Undersøg med regression om der er en potenssammenhæng mellem *n* og *spredning*.

I skal nu undersøge hvilken betydning sandsynlighedsparamtetren, *p*, har.
* Start igen med to ens fordelinger, lav om i programmet linje 18 så der står ```X.append(bin(100,0.5)) ```.
* Lav en undersøgelse hvor I ændrer på sandsynlighedsparametren for *X*, eks. $( p = [0,0.1, 0.2,0.5,0.7,0.9,1] )$. Noter middelværdi og spredning.
* Beskriv i ord hvordan spregning og middelværdi ændrer sig med sandsynlighedsparametren. Hvordan kan det ses grafisk?
* Lav to grafer, en *(p,middelværdi)* og en *(p,spredning)* og undersøg sammenhængen.

### Den dovne version
Det er selvfølgeligt muligt at lade programmet køre en masse gange og lave punktplottene for os.

I dette program kan I se et $( (n,\sigma) )$ plot eller et $( (n,\mu) )$ plot.
<iframe src='https://trinket.io/embed/python/8280b0d3b5?start=result' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

I dette program kan i se hvad der sker når man varierer sandsynlighedsparametren $( (p) )$.

<iframe src='https://trinket.io/embed/python/de6cc963ca?start=result' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

* Hvorfor har $((p,\sigma))$ plottet den form den har. Kan I genkende den?

### sammenligning hvor middelværdien er den samme
Vi laver to binomialfordelte variable, *X* og *Y*, så vi kan sammenligne dem. For at kunne sammenligne dem ser vi nu på frekvensen, altså antal krone divideret med antal kast. Udgangspunktet er *X* antal krone ved 10 kast divideret med 10 og *Y* er ved 100 kast divideret med 100.
<iframe src='https://trinket.io/embed/python/603aca696b?start=false' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>

* Kør programmet og beskriv forskellen på de blå og røde. 
* Nederst bliver middelværdi og spredning beregnet, stemmer det over ens med plottet?
* De grønne linjer er $( \mu \pm \sigma )$ for X variablen. Hvordan fordeler værdierne sig indenfor og udenfor?


### Sammenligning med teoretiske værdier
For at finde middelværdien og spredningen bruger vi data og disse definitioner.

**Middelværdien** af en stokastisk variabel *X* betegnes $( \mu )$ , og udregnes som det vægtede gennemsnit:
$$
\mu = p_1 x_1+p_2 x_2+p_3 x_3+\dots +p_n x_n
$$

**Varians**, Var(*X*), af en stokastisk variabel *X* med middelværdien $( \mu )$ repræsenterer det gennemsnitlige afstandskvadrat til middelværdien $( \mu )$. Det udregnes som:
$$
Var(X)= p_1(x_1 -\mu)^2 + \dots + p_n(x_n -\mu)^2.
$$
**Spredningen**, $\(\sigma\)$, udregnes som kvadratroden af variansen: 
$$
\sigma = \sqrt{Var(X)}.
$$

Hvis *X* er binomialfordelt kan vi også udregne middelværdi og spredning teoretisk. De er givet ved

**Middelværdi om binomialfordelingen**
$$
\mu= p⋅n,
$$
hvor *n* er antalsparameteren, og *p* er sandsynlighedsparameteren.

**Varians og spredning for binomialfordelingen**
Hvis *X* er binomialfordelt med antalsparameter *n* og sandsynlighedsparameter *p*, så er varians og spredning for *X* givet ved:
$$
V(X) = np(1 - p ) \\
\sigma(X)= \sqrt{V(X)}= \sqrt{n⋅p⋅(1-p)}.
$$

**Øvelse**


* Kør simuleringerne igen hvor middelværdi og spredning bliver beregnet. Sammenlign med de teoretisk beregnede værdier for binomialfordelingen

<iframe src='https://trinket.io/embed/python/2020ccf8ed?start=false' width='100%' height='400' frameborder='0' marginwidth='0' marginheight='0' allowfullscreen></iframe>





