# Home Assistant

**Status 20.11.2026:** Den tilsluttede Home Assistant har aktiv MQTT og Zigbee2MQTT-enheder, mens ZHA er ignoreret. Dette er kontrolleret; der er endnu ikke købt/parret julelys-smart-stik. [NOUS A6Z har officiel Zigbee2MQTT-understøttelse](https://www.zigbee2mqtt.io/devices/A6Z.html). Ude-rækkevidde og fysisk stiktype skal testes.

## Valgt styringsprincip for 2026 (23.11.2026)

Én fælles smart-plug før den eksisterende forsyningsrække er nu **valgt som styringsprincip**. Den gamle forlængerledningsrække skal først inspiceres og eventuelt udbedres/udskiftes. Når den er godkendt, kan ét smart-stik tænde og slukke hele julelyset.

Foreslået entity-id til denne variant: `switch.julelys_alle` (**ikke faktisk oprettet**).

Se [vurdering af eksisterende forsyning](stroemfordeling-2026.md#nyt-fund-23112026-fælles-eksisterende-forsyning-mulighed-for-kun-ét-smart-stik).

Det konkrete el-setup er endnu **ikke godkendt**, da en ældre fælles kabelføring og jord/IP er uafklaret. Kameraet får strøm separat via LAN/PoE og påvirkes ikke. Den nedenstående 2-zone-opbygning er alene fallback, hvis der er behov for separate kredse eller selvstændig styring. Eksisterende `ha/automations.example.yaml` er stadig **eksemplet til to zoner**, ikke konfigurationen for én fælles switch. Et eksempel til én switch findes i `ha/automations.one-plug.example.yaml`.

## Alternativt mål: 2 uafhængige udendørs zoner

Kun to uafhængige udendørs zoner:

- `switch.julelys_facade`
- `switch.julelys_carport`

Dette er **foreslåede entity-id'er**, ikke en bekræftet registrering af de faktiske enheder. Udskift ID'er, når udstyret er parret.

## Styringsprincip

- Tænd begge zoner ved solnedgang, evt. 15 minutter før, **kun i den valgte juleperiode** (eksemplet: 1. november til og med 6. januar).
- Sluk kl. 23.00, eller tidligere hvis det ønskes.
- Begge zoner skal kunne overstyres manuelt via HA.
- Undlad farveskift, blink og effekter i den foretrukne 2026-indstilling.
- Planlæg eventuelt rolig aften/fuld belysning som egne scener, når flere zoner findes.

## Eksempel, ikke produktionskonfiguration

Se [`ha/automations.example.yaml`](../ha/automations.example.yaml). Eksemplet består af to selvstændige automationer og skal **tilpasses og testes**. Det er beregnet som fil med automationer, ikke som komplet `configuration.yaml` eller færdig HA-package.

Før aktivering:
1. Afklar om systemet bruger **ZHA** eller **Zigbee2MQTT**, og om Zigbee når udendørs.
2. Kontrollér, at kontakternes strømtilstand efter strømsvigt er hensigtsmæssig.
3. Tilpas entity-id'er efter registrering.
4. Opret de relevante automationer via HA UI eller YAML-indlæsning.
5. Test tænd/sluk manuelt, solnedgangstrigger og tidsstyring.
6. Afprøv genstart, netværksudfald og manuel slukning.
7. Notér endelige entity-id'er her.

## Registrering af endelige enheder

| Zone | Producent/model | Integration | Faktisk entity-id | Testet |
| --- | --- | --- | --- | --- |
| Facade | AFVENTER | AFVENTER | AFVENTER | Nej |
| Carport | AFVENTER | AFVENTER | AFVENTER | Nej |

## Udvidelser

2027: separate styringer for træer og evt. hæk. 2028: vinduer og evt. egen flisekant. Når hardware er valgt, kan der oprettes HA-scenerne **Fuld jul**, **Rolig jul** og **Sluk alt**.

## HA-sikkerhed

Ingen tokens, adgangskoder, lokal IP-plan, cloud-nøgler eller backups må lægges i dette offentlige repo.

## Kontrol af eksisterende IKEA-smart-stik, 23.11.2026

Det er via tilsluttet Home Assistant konstateret, at der findes **fem IKEA TRETAKT** Zigbee-stik (`Lys_jul_hjerter`, `Lys_jul_pakker`, `Lys_jul_snefnug`, `Lys_jul_tree1`, `pool_pumpe`). Ejeren oplyser desuden, at der ligger et ekstra ubrugt eksemplar.

**Konklusion: IKEA TRETAKT må ikke bruges direkte i den åbne carport.** Producenten kræver **indendørs, tørre omgivelser**, driftstemperatur **0-35 °C**, og at produktet ikke udsættes for fugt. En overdækket carport er ikke et frostfrit tørt indendørsrum; en tilfældig plastkasse ophæver ikke fabrikantens krav. Producenten advarer også mod at tildække det under brug. Smart-stikkets 3680 W-mærkning ændrer ikke dette.

Valgt design fastholdes: **ét udendørsgodkendt Zigbee-stik** foran sikkerhedskontrolleret fælles forsyning. Alternativt kan eksisterende TRETAKT bruges i et **reelt tørt, frostfrit indendørsrum** med korrekt og sikker udendørs fremføring, hvis den løsning er praktisk. Begge scenarier kræver kontrol af jordoverførsel, danske stik, IP med tilsluttet stik, RCD/HPFI og de ældre kabler.

Producentens kilder:
- https://www.ikea.com/dk/da/manuals/tretakt-stikprop-smart__AA-2396101-2-2.pdf (dansk side 17-18)
- https://www.ikea.com/dk/da/p/tretakt-stikprop-smart-80540349/
