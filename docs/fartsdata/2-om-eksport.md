# Om eksport

Data blir eksportert som en .CSV-fil. CSV står for "Comma-separated
values", et filformat for å representere data i tabellform. Første linje i
filen definerer kolonnetitler, mens påfølgende linjer representerer rader.
For å lette bruk i norske versjoner av Excel, er hver rad delt i kolonner
med semikolon som separatortegn. For andre versjoner av Excel må man selv
spesifisere at semikolon er separatortegn.

CSV-filene som blir eksportert inneholder følgende kolonnetitler:

<dl>
  <dt>Trafikkregistreringspunkt</dt>
  <dd>Punktets unike ID.</dd>
  <dt>Vegreferanse</dt>
  <dd>Punktets plassering på vegnettet.</dd>
  <dt>Navn</dt>
  <dd>Punktets navn.</dd>
  <dt>Feltnummer</dt>
  <dd>Kjørefeltet som kjøretøyet er registrert i. Angir fysisk plassering i vegbanen. </dd>
<dt>Dato</dt>
  <dd>Dato for periodens aggregater.</dd>
<dt>Dag</dt>
  <dd>Dagen for den aktuelle perioden.</dd>
<dt>Måned</dt>
  <dd>Måneden for den aktuelle perioden.</dd>
<dt>Timestart</dt>
  <dd>Starttidspunktet for timen.</dd>
<dt>Antall passeringer</dt>
  <dd>Antall passeringer totalt for den aktuelle perioden</dd>
<dt>Antall gyldige passeringer</dt>
  <dd>Antall passeringer totalt med gyldig fartsmåling for den aktuelle perioden</dd>
<dt>Gjennomsnittshastighet</dt>
  <dd></dd>

<dt>85 persentil hastighet</dt>
<dd></dd>
<dt>Hastighetsfordeling</dt>
<dd>[7.0-30.0) km/t</dd>
<dd>[30.0-35.0) km/t</dd>
<dd>[35.0-40.0) km/t</dd>
<dd>[40.0-45.0) km/t</dd>
<dd>[45.0-50.0) km/t</dd>
<dd>[50.0-55.0) km/t</dd>
<dd>[55.0-60.0) km/t</dd>
<dd>[60.0-65.0) km/t</dd>
<dd>[65.0-70.0) km/t</dd>
<dd>[70.0-75.0) km/t</dd>
<dd>[75.0-80.0) km/t</dd>
<dd>[80.0-85.0) km/t</dd>
<dd>[85.0-90.0) km/t</dd>
<dd>[90.0-95.0) km/t</dd>
<dd>[95.0-100.0) km/t</dd>
<dd>[100.0-105.0) km/t</dd>
<dd>[105.0-110.0) km/t</dd>
<dd>[110.0-115.0) km/t</dd>
<dd>[115.0-120.0) km/t</dd>
<dd>[120.0-125.0) km/t</dd>
<dd>[125.0-130.0) km/t</dd>
<dd>[130.0-135.0) km/t</dd>
<dd>[135.0-140.0) km/t</dd>
<dd>[140.0-145.0) km/t</dd>
<dd>[145.0-150.0) km/t</dd>
<dd>[150.0-300.0) km/t</dd>

<dt>Lette kjøretøy (Snittfart)</dt>
<dd>Snittfart for alle lette kjøretøy under den aktuelle perioden</dd>
<dt>Tunge kjøretøy (Snittfart)</dt>
<dd>Snittfart for alle tunge kjøretøy under den aktuelle perioden</dd>
<dt>Lette kjøretøy (Antall)</dt>
<dd>Totalt antall lette kjøretøy under den aktuelle perioden</dd>
<dt>Tunge kjøretøy (Antall)</dt>
<dd>Totalt antall lette kjøretøy under den aktuelle perioden</dd>


  <dt>5,6 m - 7,6 m</dt>
  <dd>
  Snitthastighet og antall kjøretøy målt til å være større enn eller lik 5,6 m og mindre enn
  7,6 m.
  </dd>
  <dt>7,6 m - 12,5 m</dt>
  <dd>
    Snitthastighet og antall kjøretøy målt til å være større enn eller lik 7,6 m og mindre enn
  12,5 m.
  </dd>
  <dt>12,5 m - 16,0 m</dt>
  <dd>
    Snitthastighet og antall kjøretøy målt til å være større enn eller lik 12,5 m og mindre
  enn 16,0 m.
  </dd>
  <dt>16,0 m <</dt>
  <dd>
    Snitthastighet og antall kjøretøy målt til å være større enn eller lik 16,0 m.
  </dd>
</dl>
