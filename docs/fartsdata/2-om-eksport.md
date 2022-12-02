# Om fartsdatafilen

Data blir eksportert som en CSV-fil. CSV står for "Comma-separated values", et filformat som representerer data i tabellform. Første linje i filen definerer kolonnetitler, mens påfølgende linjer representerer rader. For å gjøre bruk i norske versjoner av Excel enklere er hver rad delt i kolonner med semikolon som separatortegn. For andre versjoner av Excel må en selv spesifisere semikolon som separatortegn. Det finnes ikke fartsdata på sykkelpasseringer.

CSV-filene som blir eksportert inneholder følgende begreper:

<dl>
  <dt>Trafikkregistreringspunkt</dt>
  <dd>Punktets unike ID.</dd>
  <dt>Vegreferanse</dt>
  <dd>Punktets plassering på vegnettet.</dd>
  <dt>Navn</dt>
  <dd>Punktets navn.</dd>
  <dt>Felt</dt>
  <dd>Kjørefeltet som kjøretøyet er registrert i. Angir fysisk plassering i vegbanen.</dd>
<dt>Dato</dt>
  <dd>Dato for periodens aggregater.</dd>
<dt>Dag</dt>
  <dd>Dagen for den aktuelle perioden.</dd>
<dt>Måned</dt>
  <dd>Måneden for den aktuelle perioden.</dd>
<dt>Timestart</dt>
  <dd>Tidspunkt måleperioden begynner.</dd>
<dt>Antall passeringer</dt>
  <dd>Antall passeringer totalt for den aktuelle perioden.</dd>
<dt>Gyldige passeringer</dt>
  <dd>Antallet registreringer der kvaliteten på fartsmålingen er gyldig. Fartsmålinger som ikke er gyldige er ekskludert fra utregninger av gjennomsnittsfart og 85-fraktil.</dd>
<dt>Gjennomsnittsfart</dt>
  <dd>Gjennomsnittsfart for alle gyldige passeringer i den aktuelle perioden.</dd>

<dt>85-fraktil</dt>
<dd>85-fraktilen regnes ut ved å sortere fartsmålingene etter fart, fra tregest til rasket. 85-fraktilen er farten til den 15% raskeste bilen i denne listen.</dd>
<dt>Fartsfordeling</dt>
<dd>Antall kjøretøy inndelt i fartsintervaller på 5 km/t, fra og med 7 km/t til og med 300 km/t.</dd>
<dt>Lengdeklasse</dt>
<dd>Inndeling av registrerte kjøretøyen basert på kjøretøyenes lengde.</dd>
<dt>Lette kjøretøy</dt>
<dd>Kjøretøy med en lende som er kortere enn 5,6 m.</dd>
<dt>Tunge kjøretøy</dt>
<dd>Kjøretøy med en lende som er lengre enn eller lik 5,6 m. Øvre grense for gyldig lengdemåling er 27,0 m.</dd>
