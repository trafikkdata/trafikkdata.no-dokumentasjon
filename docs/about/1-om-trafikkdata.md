Trafikkdata er data om trafikk på vegnettet. Statens vegvesens trafikkdata omfatter punktmålinger og strekningsmålinger foretatt med måleutstyr langs vegen. [Trafikkdata.no](http://trafikkdata.no) har punktmålinger fra trafikkregistreringsstasjoner på det statlige og fylkeskommunale vegnettet samt noen kommunale veger. [Reisetider.no](https://reisetider.no) har strekningsmålinger av reisetid mellom reisetidsregistreringsstasjoner i og rundt de største byene og på noen hovedveger.

Statens vegvesen har som mål å kunne levere trafikkdata med kjent kvalitet og riktig detaljeringsgrad, samt at disse dataene er etterspurt og samlet fra riktig vegnett.

Trafikkregistreringsstasjonene registrerer både sykler og motorkjøretøy. I sykkelpunktene blir hver enkelt sykkel registrert med fart og retning. For motorkjøretøy blir fart, lengde, kjøretøyklasse og avstand mellom kjøretøyene registrert i hvert kjørefelt.

Trafikkregistreringsstasjoner har ett eller flere trafikkregistreringspunkter knyttet til seg. Trafikkregistreringspunkter er stedfesting på vegen der trafikken blir registrert, og all informasjon om trafikkregistreringspunktene og tilhørende trafikkdata er tilgjengelige her i trafikkdataportalen.

Trafikkregistreringsstasjoner består av fysisk infrastruktur ved vegen, som skap o.l. Informasjon om disse kan være relevant for de som drifter og vedlikeholder veg og tilknyttet infrastruktur, og er tilgjengelig i NVDB, se for eksempel [vegkart.no](http://vegkart.no). For tiden er ikke NVDB oppdatert med de siste endringene for trafikkregistreringsstasjoner, men dette er under arbeid.

## Motorkjøretøy

Trafikken registreres ved hjelp av induktive sløyfer i vegbanen. Når en bil kjører over sløyfene registreres lengde, fart, kjøretøyklasse og avstand i sekunder til forangående kjøretøy. Det registreres også hvilket kjørefelt og kjøreretning bilen kjører i. Kjørefeltet angis alltid som den faktiske, fysiske plasseringen av bilen i vegbanen. Kjøreretningen angis som den faktiske kjøreretningen til bilen. I tilfeller der bilen kjører på "feil" side av vegen, blir kjøreretningen angitt som den motsatte av feltets angitte retning. Dette vil forekomme ved forbikjøringer. Dersom bilen passerer midt mellom de induktive sløyfene i to motgående kjørefelt, kan bilen få angitt motsatt kjørefelt, men likevel riktig, faktisk kjøreretning.

Registreringen overføres i sanntid til Statens vegvesen sitt trafikkdatasystem hvor registreringene blir kontrollert og aggregert. Aggregerte data blir tilgjengelig i trafikkdataportalen to til tre timer etter.

Motorsykler registreres og inngår i datamaterialet på lik linje med andre kjøretøy.

![Figuren viser hvordan trafikken blir registrert og overført til trafikkdatasystemet i sanntid.](images/data-collection.png)

## Sykkel

Sykkeltrafikk kan registreres med ulike sensorer. I dag benyttes induktive sløyfer og piezoelektriske kabler som legges i gang/sykkelvegene. Når en syklist passerer sensoren registreres farten. Registreringene overføres på samme måte som for motorkjøretøy.

![Sløyfer og måleskap på St. Olavs Pir ved Skansen i Trondheim.](images/loop-and-datalogger.png)

## Tilgjengelige data

Følgende data er nå tilgjengelig fra registreringsutstyr tilpasset ny løsning:

- Sykkelregistreringer fra juli 2015 (dvs. alle registreringer i ny løsning)
- Motorkjøretøyregistreringer fra november 2014 (dvs. alle registreringer i ny løsning)

Første registreringsutstyr i ny løsning ble satt i drift for motorkjøretøy i november 2014 og for sykkel i juli 2015. Deretter ble nye trafikkregistreringspunkter satt i drift jevnlig fram til i dag, og ytterligere noen trafikkregistreringspunkter vil settes i drift framover.

## Stedfesting på vegnettet

Alle trafikkregistreringspunkter er stedfestet på vegnettet med en vegsystemreferanse. Vegsystemreferansen angir blant annet vegens vegkategori, vegnummer og strekningsnummer. En del av vegsystemreferansen er en meterverdi som kommer fra oppmåling av vegen i sin lengderetning. Denne oppmålingen omtales som "metrering". Vegene måles opp på vegtrasenivå og har dermed samme meterverdi for alle kjørefelt, unntatt når vegen har adskilte løp som metreres for seg. Vegene metreres ut fra et geografisk punkt, som varierer fra veg til veg.

Trafikken registreres i hvert kjørefelt, som benevnes med et kjørefeltnummer. Kjørefeltene nummereres fra midten av vegen og utover til hver side. Det brukes oddetall på felt som har kjøreretning med metreringsretningen, og partall på kjørefelt mot metreringsretningen.

For mer detaljer om vegsystemreferansen, se Statens vegvesens Håndbok V830 Nasjonalt vegreferansesystem, som er tilgjengelig på [vegvesen.no](https://www.vegvesen.no/fag/publikasjoner/handboker).

### Kjørefeltnummer ved snudd metreringsretning

Vegsystemreferansen endrer seg når selve vegnettet endrer seg, som ved bygging av ny veg. Retningen som vegen er oppmålt i kan snus, og dette har skjedd i en del tilfeller i forbindelse med innføring av nytt vegreferansesystem i 2019. Endret metreringsretning medfører at kjørefeltnummer også endrer seg. I Trafikkdataportalen vises alltid kjørefeltnummer i henhold til nåværende metrering, også for historiske data. Kjørefeltenes beskrivelser med stedsnavn vil alltid være korrekt og uendret for det fysiske kjørefeltet, selv om nummeret har endret seg.

Trafikkregistreringspunktenes vegreferansehistorikk angir periodene hvor metreringsretningen er snudd siden første gang punktet ble satt i drift.
