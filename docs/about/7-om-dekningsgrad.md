# Om dekningsgrad
## Generell informasjon 
Et trafikkregistreringspunkt har ikke alltid klart å fange opp all trafikk med gode måleverdier. Måleusikkerhet er noe en bruker av trafikkdata må være oppmerksom på. Derfor bør alle trafikkdataverdier ha tilknyttet informasjon om måleusikkerheten. Dekningsgrad sier noe om måleusikkerheten ved å angi hvor stor andel av et tidsintervall en trafikkregistrering har data for.

I filene som kan eksporteres fra trafikkdataportalen finnes det tre ulike dekningsgrader: dekningsgrad for trafikkmengde, dekningsgrad for fart, og dekningsgrad for fart med lendeklasser.

## Manuelle merkinger
Manuelle merkinger er lagt inn av fagpersoner som har vurdert datakvaliteten på den aktuelle trafikkregistreringen. En merking gjelder for et angitt tidsintervall og kan enten synliggjøre bortfall av data eller være til opplysning om unormale trafikkforhold.  
  
Manuelle merkinger kan gjelde ett eller flere av følgende forhold:  
* Stengt veg  
* Feil på utstyr (ingen gyldige data)  
* Feil lengdemålinger  
* Feil fartsmålinger  
* Feil kjøretøyklassifisering  
* Unormal trafikkmengde  
* Unormalt fartsnivå

## Matematisk formulering
Dekningsgraden er satt sammen av flere komponenter som hver enkelt kan beskrives som en funksjon av en parameter.  
  
Operasjonelltid kan modelleres som en enhetsstegfunksjon som er lik 1 når trafikkregistreringspunktet er operasjonelt og 0 ellers.  
  
Dataoverføringskomplettheten (også kalt fulltallighet) kan modelleres som en kontinuerlig funksjon med verdimengde mellom 0 og 1, der 1 angir at alle data er overført og 0 angir at ingen data er overført.  
  
Manuelle merkinger for stengt veg og for feil i registrering kan hver for seg modelleres som enhetsstegfunksjoner som er lik 1 når registreringen ikke har feil ved seg, og lik 0 dersom en manuell merking er lagt inn for det aktuelle tidsintervallet.  
  
Andel gyldige verdier for lengde, fart og kjøretøyklasse kan hver enkelt modelleres som en kontinuerlig funksjon med verdimengde mellom 0 og 1, der 1 angir at alle data har gyldig verdi for respektive målestørrelse.  
  
Dekningsgraden kan dermed enkelt regnes ut som produktet av de relevante funksjonene. Utregningsmetoden for de ulike dekningsgradene er beskrevet i det følgende.

## Dekningsgrad for trafikkmengde
Dekningsgrad for trafikkmengde settes sammen av følgende verdier som vist i figur 1:  
* Operasjonelltid  
* Dataoverføringskompletthet (fulltallighet)  
* Manuell merking for stengt veg  
* Manuell merking for feil på utstyr (ingen gyldige data)


![Figur 1. Beregning av dekningsgrad for trafikkmengde](images/dekningsgrad-for-trafikkmengde.svg)


## Dekningsgrad for fart
Dersom et målepunkt har mulighet til å måle fart, men ikke lende på kjøretøyene, vil en dekningsgrad som kun tar hensyn til fart brukes.  
  
Dekningsgrad for fart settes sammen av følgende verdier som vist i figur 2:  
* Operasjonelltid  
* Dataoverføringskompletthet (fulltallighet)  
* Andel gyldige fartsmålinger delt på total andel fartsmålinger
* Manuell merking for stengt veg  
* Manuell merking for feil på utstyr (ingen gyldige data)  
* Manuell merking for feil fartsmålinger


![Figur 2. Beregning av dekningsgrad for fartsmålinger](images/dekningsgrad-for-fart.svg)

## Dekningsgrad for fart med lengdeklasser
Måling av fart og lengde er gjerne sterkt korrelert på grunn av måten de regnes ut av registreringsutstyret på. Et aggregat av trafikkdata må derfor ha knyttet til seg en andel av registreringene som har både gyldig lengdemåling og fartsmåling.  
  
Dekningsgrad for fart med lengdeklasser settes sammen av følgende verdier som vist i figur 3:  
* Operasjonelltid  
* Dataoverføringskompletthet (fulltallighet)  
* Andel med både gyldig lengde- og fartsmåling delt på total andel fartsmålinger
* Manuell merking for stengt veg  
* Manuell merking for feil på utstyr (ingen gyldige data)  
* Manuell merking for feil lengdemålinger  
* Manuell merking for feil fartsmålinger


![Figur 3. Beregning av dekningsgrad for fartsmålinger med lengdeklassifisering](images/dekningsgrad-for-fart-med-lengdeklasser.svg)

## Samlet dekningsgrad for flere enn ett kjørefelt
Trafikkdatastørrelser som er beregnet for flere enn ett kjørefelt får en tilsvarende dekningsgrad. Dersom alle kjørefelt har dekningsgrad forskjellig fra null er dekningsgraden for kjøreretningen lik det aritmetiske gjennomsnittet av kjørefeltenes dekningsgrad. Dersom minst ett kjørefelt har dekningsgrad lik null, så blir dekningsgraden for den kjøreretningen også null.  
  
Samme metodikk gjelder også for begge kjøreretningene samlet.
