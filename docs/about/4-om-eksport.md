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
  <dt>Navn</dt>
  <dd>Punktets navn.</dd>
  <dt>Vegreferanse</dt>
  <dd>Punktets plassering på vegnettet.</dd>
  <dt>Fra</dt>
  <dd>Starttidspunktet for periodens aggregater.</dd>
  <dt>Til</dt>
  <dd>Sluttidspunktet for periodens aggregater.</dd>
  <dt>Dato (kun for time- og døgntrafikk)</dt>
  <dd>Dato for periodens aggregater.</dd>
  <dt>Fra tidspunkt (kun for timetrafikk)</dt>
  <dd>Starttidspunktet for timen.</dd>
  <dt>Til tidspunkt (kun for timetrafikk)</dt>
  <dd>Sluttidspunktet for timen.</dd>
  <dt>År (kun for måned-, sesong- og årsdøgntrafikk)</dt>
  <dd>Året for den aktuelle perioden.</dd>
  <dt>Måned (kun for månedsdøgntrafikk)</dt>
  <dd>Måned for den aktuelle perioden.</dd>
  <dt>Sesong (kun for sesongdøgntrafikk)</dt>
  <dd>Sesong for den aktuelle perioden.</dd>
  <dt>Trafikkmengde</dt>
  <dd>Trafikkmengden for den aktuelle perioden. For måned-, sesong- og årsdøgntrafikk er dette gjennomsnittlig trafikkmengde per døgn.</dd>
  <dt>Konfidensintervall start (kun for måned-, sesong- og årsdøgntrafikk)</dt>
  <dd>Nedre grense for 95%-konfidensintervall for trafikkmengden for den aktuelle perioden.</dd>
  <dt>Konfidensintervall slutt (kun for måned-, sesong- og årsdøgntrafikk)</dt>
  <dd>Øvre grense for 95%-konfidensintervall for trafikkmengden for den aktuelle perioden.</dd>
  <dt>Dekningsgrad (%)</dt>
  <dd>Andel tid det er gode data for i perioden.</dd>
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
  <dd>
  Antall kjøretøy som er vurdert til å ha underkjent lengdemåling. Disse
  kjøretøyene inngår ikke i lengdeklassifiseringen.
  </dd>
  <dt>Lengdekvalitetsgrad</dt>
  <dd>Andel i prosent av kjøretøy med godkjent lengdemåling.</dd>
  <dt>Felt</dt>
  <dd>
    <i>Felt:</i> Kjørefeltet som kjøretøyet er registrert i. Angir fysisk plassering i vegbanen. </br>
    <i>Retning:</i> Den faktiske kjøreretningen til kjøretøyet. I tilfeller der bilen kjører på "feil" side av vegen, blir kjøreretningen angitt som den motsatte av feltets angitte retning. </br>
    <i>Totalt:</i> angir summen av alle kjørefelt (det samme som summen av begge retninger).
  </dd>
  <dt>Felt gyldig fra (kun for time- og døgntrafikk)</dt>
  <dd>
  Gyldighet for vegens inndeling i kjørefelt. (Dette kan endre seg over
  tid, f.eks. når en veg utvides fra 2 til 4 kjørefelt).
  </dd>
  <dt>Felt gyldig til (kun for time- og døgntrafikk)</dt>
  <dd>
  For historiske feltinndelinger vil det angis et sluttidspunkt her.
  Fravær av verdi her betyr at oppgitt felt fortsatt er gyldig i dag.
  </dd>
  <dt>&lt; 5,6 m</dt>
  <dd>
  Antall kjøretøy målt til å være kortere enn 5,6 m. Grensen 5,6 m brukes
  som skille på lette og tunge kjøretøy.
  </dd>
  <dt>&gt; 5,6 m</dt>
  <dd>Antall kjøretøy målt til å være større enn eller lik 5,6 m.</dd>
  <dt>5,6 m - 7,6 m</dt>
  <dd>
  Antall kjøretøy målt til å være større enn eller lik 5,6 m og mindre enn
  7,6 m.
  </dd>
  <dt>7,6 m - 12,5 m</dt>
  <dd>
  Antall kjøretøy målt til å være større enn eller lik 7,6 m og mindre enn
  12,5 m.
  </dd>
  <dt>12,5 m - 16,0 m</dt>
  <dd>
  Antall kjøretøy målt til å være større enn eller lik 12,5 m og mindre
  enn 16,0 m.
  </dd>
  <dt>16,0 m - 24,0 m</dt>
  <dd>
  Antall kjøretøy målt til å være større enn eller lik 16,0 m og mindre
  enn 24,0 m.
  </dd>
  <dt>&gt; 24,0 m</dt>
  <dd>
  Antall kjøretøy målt til å være større enn eller lik 24,0 m. Øvre grense
  for gyldig lengdemåling er 27,0 m.
  </dd>
</dl>

CSV for sykkelpunkter bruker akkurat samme oppsett som for kjøretøy, bare
en "-" for alle trafikkmengder for lengdeklasser.
