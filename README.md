# Jul på Islandsvej

Et flerårigt projekt for julebelysning af hus, carport og have, styret via Home Assistant (HA).

**Status pr. 1. november 2026:** Planlægning. Ingen indkøb, montering eller HA-integration er registreret som gennemført.

## Målet

Et imponerende, men roligt og sammenhængende udtryk med **kun varmt hvidt lys**. Belysningen skal kunne opsættes sikkert, genbruges hver jul, udbygges år for år og styres i separate zoner fra Home Assistant.

### Årsplan

| År | Fokus | Budget | Status |
| --- | --- | ---: | --- |
| **2026** | Istaplys langs facadens tagrende samt lys på carportens forkant, granguirlander og hoveddør | **2.500 kr.** | Planlagt |
| **2027** | **Rigtige små juletræer plantes** og får belysning; mulig lys i hækken | **3.500 kr.** | Foreløbig |
| **2028** | Vinduesstjerner og eventuelt flytbar belysning langs **egen flisekant, ikke fortovet** | **2.000 kr.** | Foreløbig |
| **2029** | Justeringer, reparationer og ekstra dekorationer efter erfaringer | **1.000 kr.** | Foreløbig |
| | **Samlet grundbudget** | **9.000 kr.** | |
| | Ekstra økonomisk reserve uden for årsbudgetterne | 1.000-1.500 kr. | Valgfri |

Det tidligere skøn på 7.600 kr. er opjusteret, fordi 2027 nu omfatter **plantning af levende træer** i stedet for køb af kunstige lystræer. Beløb er planlægningsestimater, ikke tilbud eller køb.

## Vigtig afgrænsning af 2026

**Kun** facadens istaplys og carport/indgang får julebelysning i 2026. **Ingen** træer, hæklys, vinduesstjerner, lys langs flisekant/fortov, facade-buske, tagryg eller taggavl indgår i 2026.

To eksisterende forsyningspunkter er oplyst: et udendørs strømudtag under tagrenden og et ved hoveddøren i carporten. Begge skal kontrolleres før brug. Placeringer er bevidst kun beskrevet overordnet, da repositoryet er offentligt.

## Dokumentation

- [Plan og etaper](docs/plan.md)
- [Budget og indkøbsprincipper](docs/budget.md) samt [budgetposter i CSV](budget/budget.csv)
- [Visuel retning og afgrænsning](docs/design.md)
- [Teknik, zoner og sikkerhed](docs/teknik.md)
- [Home Assistant](docs/home-assistant.md) og [YAML-eksempel](ha/automations.example.yaml)
- [Montering, sæsondrift og opbevaring](docs/montering.md)
- [Beslutninger og åbne spørgsmål](docs/beslutninger.md)
- [Udstyr og køb](docs/inventar.md)

## Arbejdsproces i GitHub

1. Planlæg i **Issues**: én konkret opgave pr. issue, med år i titlen, fx `[2026]`.
2. Afklar mål, indkøb og monteringsmetode, **før** bestilling.
3. Notér købspris og faktisk status i `budget/budget.csv` og `docs/inventar.md`.
4. Dokumentér HA-entity-id'er og testresultater i `docs/home-assistant.md`.
5. Marker issue færdigt først, når kriterierne er verificeret på stedet.
6. Afhold sæsonreview efter nedtagning og opdatér næste års plan.

Til illustrationer findes foreløbig kun visualiseringerne fra planlægningssamtalen. **De er inspirationsbilleder og ikke opmåling eller dokumentation for gennemført arbejde.** Et udvalgt billede kan senere tilføjes i `assets/` med tydelig versionsangivelse og uden private oplysninger.
