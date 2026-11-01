# Teknik, strøm og sikkerhed

Dette er en **plan**, ikke en udført elinstallation eller en elektrikers projektering.

## Fysiske zoner

| Zone | 2026? | Strømforsyning | Lys | HA |
| --- | --- | --- | --- | --- |
| A: Lang facade | Ja | Eksisterende udtag under tagrende, efter kontrol | Varmhvide istaplyskæder | Egen styring |
| B: Carport og hoveddør | Ja | Eksisterende udtag ved hoveddør, efter kontrol | Carportforkant + granguirlander + indgangslys | Egen styring |
| C: Hæk | Tidligst 2027 | Afklares | Varmhvidt lysnet/lyskæder | Egen styring |
| D: Plantede juletræer | Tidligst 2027 | Afklares | Varmhvide lavvoltkæder | Egen styring |
| E: Vinduer og evt. egen flisekant | Tidligst 2028 | Indendørs udtag / afklares | Stjerner / evt. lavvoltbelysning | Uafhængige zoner |

## Opmåling før indkøb

- Facadens **reelle** tagrendelængde i meter: `AFVENTER` (foreløbigt skøn 15-18 m).
- Carportforkantens længde: `AFVENTER`.
- Højde til tagrenden og sikkert adgangsforhold: `AFVENTER`.
- Placering, type, jordforbindelse og beskyttelse ved de to eksisterende udtag: `AFVENTER`.
- Evt. udendørs Zigbee-signal og router/koordinator-rækkevidde: `AFVENTER`.
- Kapacitet og kabelføringsvej, uden krydsning af indkørsel/gangarealer: `AFVENTER`.

## Principskitse: El- og HA-opbygning

```mermaid
flowchart TD
  HA[Home Assistant] --> Z[Zigbee-koordinator / kompatibel integration]
  Z --> A[Udendørs smart-stik A]
  Z --> B[Udendørs smart-stik B]
  U1[Eksisterende udtag under tagrende] --> A
  U2[Eksisterende udtag ved hoveddør] --> B
  A --> FA[Egnet udendørs strømforsyning til facade-lyskæder]
  B --> CA[Egnet udendørs strømforsyning til carport + indgang]
```

**Bemærk:** Skitsen er logisk, ikke en forskrift for fysisk samling. Én zone kan bestå af flere transformerbaserede lyskæder, men kun hvis fordeling, belastning og producenternes instruktioner tillader det. Forskellige produktserier må ikke antages at kunne sammenkobles.

## Sikkerhed før montering

1. Kontroller udtagenes egnethed, fejlstrømsbeskyttelse (RCD) og jordforbindelse. Få en fagperson til at vurdere forhold, der er usikre.
2. Alt monteret elektrisk udstyr, stik og forsyninger skal være beregnet til **udendørs brug**. IP44 kan være et minimum for udsatte dele, men højere kapslingsgrad kan være nødvendig afhængigt af eksponering og producentens anvisning.
3. Placér stik og transformere væk fra stående vand, hævet over terræn og så de ikke kan trække vand ind. En kasse er ikke automatisk sikker uden passende ventilations-/kabelanvisninger.
4. Brug egnede kabeltværsnit, ledningsføring og godkendte fordelingsløsninger. Undgå klemning ved døre, hjulpassage, træk og snublerisiko.
5. Lav **ingen** ændringer af den faste installation som gør-det-selv-arbejde. Skal der etableres nye faste udtag, bruges autoriseret elinstallatør.
6. Montér aldrig fra tagfladen alene for julebelysningen. Kan tagrenden ikke nås på sikker vis, hyr egnet fagperson og justér budget.
7. Til træer og dekorationer på jorden foretrækkes fabrikantgodkendt lavvolt efter strømforsyning.
8. Gennemgå strømforbrug og belastning for alle kæder og smart-stik før tænding.

## Materialevalg

- Ens varmt hvidt på alt lys, gerne fra samme system for et ensartet udtryk.
- Vælg system efter **reelle mål**, aftagelige tagrendekroge og sikker monteringshøjde.
- Smart-stik: vælg først når HA-teknologi (ZHA eller Zigbee2MQTT), danske stikforhold og udendørs klassifikation er verificeret.
- Flere kæder i samme zone skal have kompatible strømforsyninger; ikke klip og splejs fabriksfremstillede kæder uden dokumenteret mulighed.

## Vedligehold

Inspektion før hver sæson, efter kraftig vind/regn og inden nedtagning. Registrér eventuelle fejl i GitHub Issues.
