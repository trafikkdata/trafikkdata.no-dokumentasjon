Trafikkdata er data om trafikk på vegnettet. Statens vegvesens trafikkdata omfatter punktmålinger og strekningsmålinger foretatt med måleutstyr langs vegen. <a href="http://trafikkdata.no"  style="color: #44f55; text-decoration: underline;">Trafikkdata.no</a> har punktmålinger fra trafikkregistreringsstasjoner på det statlige og fylkeskommunale vegnettet samt noen kommunale veger. <a href="https://vegvesen.no/trafikk/"  style="color: #44f55; text-decoration: underline;">Vegvesen.no/trafikk</a> har strekningsmålinger av reisetid mellom reisetidsregistreringsstasjoner i og rundt de største byene og på noen hovedveger.

Statens vegvesen har som mål å kunne levere trafikkdata med kjent kvalitet og riktig detaljeringsgrad, samt at disse dataene er etterspurt og samlet fra riktig vegnett.

Trafikkregistreringsstasjonene registrerer både sykler og motorkjøretøy. I sykkelpunktene blir hver enkelt sykkel registrert med fart og retning. For motorkjøretøy blir fart, lengde, kjøretøyklasse og avstand mellom kjøretøyene registrert i hvert kjørefelt.

Trafikkregistreringsstasjoner har ett eller flere trafikkregistreringspunkter knyttet til seg. Trafikkregistreringspunkter er stedfesting på vegen der trafikken blir registrert, og all informasjon om trafikkregistreringspunktene og tilhørende trafikkdata er tilgjengelige her i trafikkdataportalen.

Trafikkregistreringsstasjoner består av fysisk infrastruktur ved vegen, som skap o.l. Informasjon om disse kan være relevant for de som drifter og vedlikeholder veg og tilknyttet infrastruktur, og er tilgjengelig i NVDB, se for eksempel <a href="http://vegkart.no"  style="color: #44f55; text-decoration: underline;">vegkart.no</a>. 

### Motorkjøretøy

Trafikken registreres ved hjelp av induktive sløyfer i vegbanen. Når en bil kjører over sløyfene registreres lengde, fart, kjøretøyklasse og avstand i sekunder til forangående kjøretøy. Det registreres også hvilket kjørefelt og kjøreretning bilen kjører i. Kjørefeltet angis alltid som den faktiske, fysiske plasseringen av bilen i vegbanen. Kjøreretningen angis som den faktiske kjøreretningen til bilen. I tilfeller der bilen kjører på "feil" side av vegen, blir kjøreretningen angitt som den motsatte av feltets angitte retning. Dette vil forekomme ved forbikjøringer. Dersom bilen passerer midt mellom de induktive sløyfene i to motgående kjørefelt, kan bilen få angitt motsatt kjørefelt, men likevel riktig, faktisk kjøreretning.

Registreringen overføres i sanntid til Statens vegvesen sitt trafikkdatasystem hvor registreringene blir kontrollert og aggregert. Aggregerte data blir tilgjengelig i trafikkdataportalen to til tre timer etter.

Motorsykler og lignende kjøretøy som moped og scooter registreres og inngår i datagrunnlaget på lik linje med andre kjøretøy. Tidligere var ikke motorsykler en del av trafikkregistreringene, men dette ble gradvis innført i perioden 2015 - 2018. Tidspunktet for denne endringen er ulikt for hvert trafikkregistreringspunkt, men sammenfaller med overgangen fra “ukjent” til “kjent” datakvalitet som er angitt i datovelgeren på hvert punkt.

Kvaliteten på registrering av motorsykler kan være dårligere enn for øvrige motorkjøretøy. Enkelte motorsykler blir ikke registrert i tilfeller hvor de passerer sensorene på en ugunstig måte, for eksempel ved å kjøre mellom to kjørefelt.

Alle registrerte kjøretøy blir klassifisert etter kjøretøytype, og motorsykkel er en egen klasse. Trafikkdata med kjøretøyklasser er ikke publisert ennå, men kontakt oss dersom det er ønskelig å utforske dette.

![Figuren viser hvordan trafikken blir registrert og overført til trafikkdatasystemet i sanntid.](images/data-collection.png)

### Sykkel

Sykkeltrafikk kan registreres med ulike sensorer. I dag benyttes induktive sløyfer og piezoelektriske kabler som legges i gang/sykkelvegene. Når en syklist passerer sensoren registreres farten. Registreringene overføres på samme måte som for motorkjøretøy.

![Sløyfer og måleskap på St. Olavs Pir ved Skansen i Trondheim.](images/loop-and-datalogger.png)

### Registreringshyppighet

Med registreringshyppighet menes hvor ofte trafikken registreres ved et trafikkregistreringspunkt. Hyppigheten kan være en av to verdier: kontinuerlig eller periodisk.

Kontinuerlige registreringer foretas døgnet rundt, hele året, år etter år.

Periodiske registreringer foretas døgnet rundt i kortere perioder, typisk i en ukes tid. Registreringsperioden gjentas så 4-5 ganger samme kalenderår. Prosedyren gjentas så hvert fjerde år.

### Overgang fra “ukjent” til “kjent datakvalitet”

I perioden 2015 - 2018 ble det gradvis gått over til ny løsning for innsamling og kvalitetskontroll av data. Tidspunktet for denne endringen er ulikt for hvert trafikkregistreringspunkt, men sammenfaller med overgangen fra “ukjent” til “kjent” datakvalitet som er angitt i datovelgeren på hvert punkt. Med “kjent” kvalitet menes at hver kjøretøyregistrering er blitt vurdert opp mot kvalitetskriterier og at alle aggregerte og beregnede størrelser kommer med kvalitetsinformasjon i form av dekningsgrad.

### Stedfesting på vegnettet

Alle trafikkregistreringspunkter er stedfestet på vegnettet med en vegsystemreferanse. Vegsystemreferansen angir blant annet vegens vegkategori, vegnummer og strekningsnummer. En del av vegsystemreferansen er en meterverdi som kommer fra oppmåling av vegen i sin lengderetning. Denne oppmålingen omtales som "metrering". Vegene måles opp på vegtrasenivå og har dermed samme meterverdi for alle kjørefelt, unntatt når vegen har adskilte løp som metreres for seg. Vegene metreres ut fra et geografisk punkt, som varierer fra veg til veg.

Trafikken registreres i hvert kjørefelt, som benevnes med et kjørefeltnummer. Kjørefeltene nummereres fra midten av vegen og utover til hver side. Det brukes oddetall på felt som har kjøreretning med metreringsretningen, og partall på kjørefelt mot metreringsretningen.

For mer detaljer om vegsystemreferansen, se Statens vegvesens Håndbok V830 Nasjonalt vegreferansesystem, som er tilgjengelig på <a href="https://www.vegvesen.no/fag/publikasjoner/handboker"  style="color: #44f55; text-decoration: underline;">vegvesen.no</a>. 

#### Kjørefeltnummer ved snudd metreringsretning

Vegsystemreferansen endrer seg når selve vegnettet endrer seg, som ved bygging av ny veg. Retningen som vegen er oppmålt i kan snus, og dette har skjedd i en del tilfeller i forbindelse med innføring av nytt vegreferansesystem i 2019. Endret metreringsretning medfører at kjørefeltnummer også endrer seg. I Trafikkdataportalen vises alltid kjørefeltnummer i henhold til nåværende metrering, også for historiske data. Kjørefeltenes beskrivelser med stedsnavn vil alltid være korrekt og uendret for det fysiske kjørefeltet, selv om nummeret har endret seg.

Trafikkregistreringspunktenes vegreferansehistorikk angir periodene hvor metreringsretningen er snudd siden første gang punktet ble satt i drift.