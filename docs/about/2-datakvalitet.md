## Datakvalitet

Alle kjøretøyregistreringer blir kontrollert mot et sett med kvalitetsregler, som er utarbeidet i samråd med utstyrsleverandørene og basert på Statens vegvesens egne tester av registreringsutstyret.

### Kvalitetsregler

Kvalitetsreglene er i korthet skissert her.

For motorkjøretøy:

Selve registreringen merkes ugyldig dersom:

- Kjørefeltverdien er fraværende.
- Kjørefeltverdien er utenfor de kjørefeltene som eksisterer på vegsnittet.

Lengde- og kjøretøyklasseregistreringen merkes ugyldig dersom:

- Lengdemålingen er < 1 m eller > 27 m.
- Absoluttverdi av fart < 7 km/h.

Fartsregistreringen merkes ugyldig dersom:

- Absoluttverdi av fart > 300 km/h
- Absoluttverdi av fart < 7 km/h.

I tillegg kommer noen apparatspesifikke regler som baseres på leverandørenes egne kvalitetsparametre.

For sykkelregistreringer har vi ikke flere regler enn at selve registreringen er ugyldig dersom utstyret mener det var noe annet enn en sykkel som ble registrert.

### Kvalitetsmerker

Resultatet av kontrollen er at enkeltkjøretøydata lagres med følgende kvalitetsmerker i databasen:

<dl>
    <dt>valid_event</dt>
    <dd><i>False</i> dersom selve registreringen er ugyldig. Disse utelates fra alle aggregater og beregninger.</dd>
    <dt>valid_length</dt>
    <dd><i>False</i> dersom lengdemålingen er ugyldig. Disse utelates fra alle oppdelinger i lengdeklasser.</dd>
    <dt>valid_speed</dt>
    <dd><i>False</i> dersom fartsmålingen er ugyldig. Disse utelates fra alle fartsberegninger.</dd>
    <dt>valid_classification</dt>
    <dd><i>False</i> dersom kjøretøyklassifiseringen er ugyldig. Disse utelates fra alle oppdelinger i kjøretøyklasser.</dd>
</dl>

Basert på dette kan vi angi andelen godkjente registreringer i et tidsintervall med en _kvalitetsgrad_:

- `fartskvalitetsgrad = (antall registreringer med gyldig fartsmåling i perioden) / (totalt antall gyldige registreringer i perioden) * 100 %`

- `lengdekvalitetsgrad = (antall registreringer med gyldig lengdemåling i perioden) / (totalt antall gyldige registreringer i perioden) * 100 %`

- `klassifiseringskvalitetsgrad = (antall registreringer med gyldig klassifisering i perioden) / (totalt antall gyldige registreringer i perioden) * 100 %`

### Bortfall av data

Det kan være ulike grunner til at data ikke blir registrert eller får systematisk lavere kvalitet i perioder.

#### Operasjonell status på målestasjon

Registreringsutstyret er operasjonelt fra det tidspunktet det blir igangsatt til det blir satt ut av drift. Dette er manuelle handlinger. Perioder utenfor det operasjonelle intervallet skal ikke være tellende med nulltrafikk i beregninger. Derfor har trafikkdatasystemet lagret informasjon om alle tidspunkt for igangsetting og ut-av-driftssettelse.

#### Fulltallighet

Fulltallighet er et mål på andelen overførte data fra registreringsapparatet.
Fulltallighet er definert slik:

`Fulltallighet = (antall løpenummer i perioden) / (største løpenummer innenfor perioden - minste løpenummer innenfor perioden + 1) * 100%`

Fulltalligheten gjelder for hele timer, og gjelder samlet for en målestasjons registreringsapparat. Fulltalligheten er per definisjon 100 % i timer helt uten trafikk, unntatt i tilfeller hvor det mangler overføring av data over flere timer.

#### Manuell merking

Manuell merking brukes av de målestasjonsansvarlige til å legge inn informasjon om hendelser på vegen eller med registreringsutstyret som påvirker trafikkregistreringene. Perioder kan merkes per kjørefelt med:

- unormal trafikkmengde (påvirker trafikkindekser)
- stengt veg (påvirker trafikkmengdestørrelser og trafikkindekser)
- unormal fart (påvirker fartsstørrelser)
- feil på utstyr (påvirker alle størrelser)

Senere vil de manuelle merkingene bli tilgjengeliggjort sammen med data de gjelder for i trafikkdataportalen og API-et.

#### Dekningsgrad

Dekningsgrad angir hvor mye data (antall timer og dager) av god nok kvalitet vi har, sammenlignet med det vi hadde hatt uten bortfall.
For aggregerte data (timetrafikk og døgntrafikk) vil en dekningsgrad på 50% bety at vi bare har data fra 50% av perioden og at den reelle trafikkmengden derfor er større.

Dekningsgraden beregnes basert på målestasjonens operasjonelle status og fulltallighet, samt eventuelle manuelle merkinger som gjelder for kjørefeltene på det aktuelle trafikkregistreringspunktet.

Gjennomsnittstallene (f.eks. ÅDT, MDT) beregnes som gjennomsnittlig trafikkmengde for dager med 95% dekningsgrad eller høyere.
Dekningsgrad for gjennomsnittstrafikk er gjennomsnittet av dekningsgrad for dagene som inngår i gjennomsnittstrafikken, multiplisert med andelen dager som inngår.
Som eksempel: Hvis halvparten av dagene i februar (14 dager) har dekningsgrad 60%, og halvparten (14 dager) har 96%, vil bare dagene med dekningsgrad 96% være inkludert, og dekningsgraden for februar vil bli 96%\*(14/28) = 48%.
En lav dekningsgrad for gjennomsnittstall indikerer derfor at gjennomsnittstallet er mindre representativt enn det ville vært med 100% dekningsgrad.

Størrelser som har dekningsgrad lik null, får ingen verdi for trafikkmengde.
