# Om eksportfilene

Data blir eksportert som en CSV-fil. CSV står for "Comma-separated values", et filformat som representerer data i tabellform. Første linje i filen definerer kolonnetitler, mens påfølgende linjer representerer rader. For å gjøre bruk i norske versjoner av Excel enklere er hver rad delt i kolonner med semikolon som separatortegn. For andre versjoner av Excel må en selv spesifisere semikolon som separatortegn.

CSV-filene som blir eksportert inneholder følgende begreper:

<dl>
  <dt>Trafikkregistreringspunkt</dt>
    <dd>Punktets unike ID.</dd>
  <dt>Vegreferanse</dt>
    <dd>Punktets plassering på vegnettet.</dd>
  <dt>Navn</dt>
    <dd>Punktets navn.</dd>
  <dt>Kjørefelt</dt>
    <dd>Kjørefeltet som kjøretøyet er registrert i. Angir fysisk plassering i vegbanen.</dd>
  <dt>Dato</dt>
    <dd>Dato for periodens aggregater.</dd>
  <dt>Dag</dt>
    <dd>Dagen for den aktuelle perioden.</dd>
  <dt>Måned</dt>
    <dd>Måneden for den aktuelle perioden.</dd>
  <dt>År</dt>
    <dd>Året for den aktuelle perioden.</dd>
  <dt>Sesong</dt>
    <dd>sesong for den aktuelle perioden.</dd>
  <dt>Fra</dt>
    <dd>Starttidspunktet for periodens aggregater.</dd>
  <dt>Til</dt>
    <dd>Sluttidspunktet for periodens aggregater.</dd>
  <dt>Fra tidspunkt (kun for timetrafikk)</dt>
    <dd>Starttidspunktet for timen.</dd>
  <dt>Til tidspunkt (kun for timetrafikk)</dt>
    <dd>Sluttidspunktet for timen.</dd>
  <dt>Trafikkmengde</dt>
    <dd>Trafikkens størrelse uttrykt i antall kjøretøy evt. personbilenheter. For måned-, sesong- og årsdøgntrafikk er dette gjennomsnittlig trafikkmengde per døgn.</dd>
  <dt>Gyldige passeringer</dt>
    <dd>Antallet registreringer der kvaliteten på fartsmålingen er gyldig. Fartsmålinger som ikke er gyldige er ekskludert fra utregninger av gjennomsnittsfart og 85-fraktil.</dd>
  <dt>Gjennomsnittshastighet</dt>
    <dd>Gjennomsnittshastighet for alle gyldige passeringer for den aktuelle perioden.</dd>
  <dt>85-fraktil</dt>
    <dd>85-fraktilen regnes ut ved å sortere fartsmålingene etter fart, fra tregest til rasket. 85-fraktilen er farten til den 15% raskeste bilen i denne listen.</dd>
  <dt>Fartsfordeling</dt>
    <dd>Antall kjøretøy inndelt i fartsintervaller på 5 km/t.</dd>
  <dt>Lengdeklasse</dt>
    <dd>Inndeling av registrerte kjøretøyen basert på kjøretøyenes lengde.</dd>
  <dt>Lette kjøretøy</dt>
    <dd>Kjøretøy med en lende som er kortere enn 5,6 m.</dd>
  <dt>Tunge kjøretøy</dt>
    <dd>Kjøretøy med en lende som er lengre enn eller lik 5,6 m. Øvre grense for gyldig lengdemåling er 27,0 m.</dd>
  <dt>Konfidensintervall start (kun for måned-, sesong- og årsdøgntrafikk)</dt>
    <dd>Nedre grense for 95%-konfidensintervall for trafikkmengden for den aktuelle perioden.</dd>
  <dt>Konfidensintervall slutt (kun for måned-, sesong- og årsdøgntrafikk)</dt>
    <dd>Øvre grense for 95%-konfidensintervall for trafikkmengden for den aktuelle perioden.</dd>
  <dt>Antall timer eller døgn total</dt>
    <dd>Antall timer eller døgn i perioden.</dd>
  <dt>Antall timer inkludert (kun for time- og døgntrafikk)</dt>
    <dd>Antall timer som har data i perioden.</dd>
  <dt>Antall timer ugyldig (kun for time- og døgntrafikk)</dt>
    <dd>Antall timer i perioden med ukjent kvalitet.</dd>
  <dt>Antall døgn inkludert (kun for måned-, sesong- og årsdøgntrafikk)</dt>
    <dd>Antall døgn som har dekningsgrad på minst 95% i perioden, og som dermed er inkludert i gjennomsnittet.</dd>
  <dt>Antall døgn ugyldig (kun for måned-, sesong- og årsdøgntrafikk)</dt>
    <dd>Antall døgn som har dekningsgrad lavere enn 95% i perioden.</dd>
  <dt>Ikke gyldig lengde</dt>
    <dd>Antall kjøretøy som er vurdert til å ha underkjent lengdemåling. Disse kjøretøyene inngår ikke i lengdeklassifiseringen.</dd>
  <dt>Lengdekvalitetsgrad</dt>
    <dd>Andel i prosent av kjøretøy med godkjent lengdemåling.</dd>
  <dt>Felt gyldig fra (kun for time- og døgntrafikk)</dt>
    <dd>Gyldighet for vegens inndeling i kjørefelt. (Dette kan endre seg over tid, f.eks. når en veg utvides fra 2 til 4 kjørefelt).</dd>
  <dt>Felt gyldig til (kun for time- og døgntrafikk)</dt>
    <dd>For historiske feltinndelinger vil det angis et sluttidspunkt her. Fravær av verdi her betyr at oppgitt felt fortsatt er gyldig i dag.</dd>
</dl>


CSV for sykkelpunkter bruker akkurat samme oppsett som for kjøretøy, bare
en "-" for alle lengdeklassevolumtall.
