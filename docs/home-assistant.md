# Home Assistant

## Målet for 2026

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
