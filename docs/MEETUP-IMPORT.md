# Prenos z Meetup.com

**Posodobitev 20. septembra 2026:** na željo organizatorja so uredniške obnove na vseh 32 straneh zamenjane s celotnim besedilom pripadajočih objav na Meetup.com. Vsaka kartica uporablja odlomek iz istega besedila. Objavljen je tudi [33. meetup, Sokratski seminar](https://www.meetup.com/bitcoin-maribor/events/316592529/), 24. septembra 2026 ob 19.00 v hotelu Betnava, z izvirnim opisom in naslovno sliko. Izvirni opisi prvih 32 dogodkov so preverljivi prek SHA-256 v `meetup-sources.json`; ta vsebuje tudi novi prihajajoči dogodek. Spodnji odsek opisuje prejšnjo fazo prenosa, ko so bili na strani še povzetki.

Preverjeno 19. septembra 2026. Skupina [Bitcoin Maribor](https://www.meetup.com/bitcoin-maribor/) je navajala **32 preteklih dogodkov**. Pridobljene in preverjene so bile vse posamezne javne objave, od 14. 9. 2023 do 27. 8. 2026. Vsaka je imela status `PAST`; prihodnji dogodki in osnutki niso vključeni.

## Kaj je preneseno

- Vseh 32 dogodkov ima svojo stran, kratek slovenski povzetek za kartico, slovensko besedilo, datum, uro, kraj in povezavo na izvirno objavo.
- Besedila so uredniški povzetki **napovedi**, ne neodvisna poročila o dejanskem poteku srečanj. Izpuščeni so ponavljajoči se pozivi k prijavi, donacijam, promocije in podvojene angleške različice. Ni dodanih domnevnih izjav, zaključkov ali števil udeležencev.
- Priložene so slike, ki jih javne objave uporabljajo za naslovnico. Gre za 14 različnih datotek za 32 dogodkov; ponovitve društvenih grafik so že v viru. Pri prvem dogodku ni posebne naslovne fotografije, zato je uporabljena njegova `displayPhoto`, tj. skupinska slika, in to je zapisano tudi na strani.
- Slike so lokalno shranjene kot `banner.jpg`, brez spreminjanja ali obrezovanja izvornih datotek. Prikaz kartic in člankov ostaja izvorni Zolarwind. Vzorčne slike iz teme so odstranjene iz map meetupov.
- Slike iz Meetup objav nimajo licence Unsplash iz teme. Ohranjene so kot gradivo uporabnikove skupine za naročeni prenos; njihov vir je zabeležen pri vsaki datoteki v manifestu.
- Tri obstoječe predstavitve iz GitHuba so ohranjene. Naslovne slike **ne** nadomeščajo 48 manjkajočih prilog znotraj predstavitev.
- Prvotna migrirana besedila GitHuba so za primerjavo shranjena v `docs/archive/github-meetups/`. Ne objavljajo se kot dodatne spletne strani.

## Popravki in posebnosti

- **11. 4. 2024:** osmi meetup je bil namenjen uredbi MiCA, gostja je bila Anja Blaj. Napačni decembrski dvojnik je zamenjan in osnutek je objavljen na obstoječem URL-ju `/meetups/202404/`.
- **13. 2. 2025:** dodan manjkajoči meetup o bitcoin zakladnicah in podjetju Strategy s Klemnom K. Verstovškom. Dodane so preusmeritve za stari manjkajoči `meetup-notes/202502`.
- **18. 4. 2025:** dopolnjena nekdanja napoved kriptografije; gost je bil Nino Cajnkar.
- **22. 1. in 5. 2. 2026:** naslova na Meetupu pomotoma navajata leto 2025. Uporabljeno je leto **2026** iz strukturiranega datuma; januarsko besedilo ga tudi izrecno potrjuje. Izvirna naslova ostajata v metapodatkih in manifestu.
- **Marec 2026:** dogodka 10. in 26. marca sta ločena (`20260310` in `20260326`); združevanje samo po mesecu bi izgubilo enega od njiju. Angleški del prve napovedi pomotoma navaja 25. srečanje; naslov in slovenski del pravilno navajata 26.
- **20. 12. 2023:** začetek je ob **18.00**, kar potrjujeta besedilo in strukturirani podatek; drugi dogodki imajo pretežno 19.00.
- **25. 6. 2026:** kraj je **Koblarjev zaliv, Na Otok 20, Kamnica**, ne običajni Hotel Betnava. V opisu je ohranjena tudi napovedana možnost ob dežju, brez trditve, katera lokacija je bila dejansko uporabljena.

## Sledljivost

`meetup-sources.json` vsebuje ID-je, URL-je, izvirne naslove, datume s časovnimi odmiki, kraje, vire slik, mere slik in SHA-256 datotek ter izvornih opisov. Ne vsebuje profilov obiskovalcev, seznamov prijav ali njihovih fotografij.

Opisi in slike so zdaj del repozitorija. Gradnja ne potrebuje povezave z Meetupom in poznejše spremembe na Meetupu se ne uvozijo samodejno. Urejajte `content/meetups/` kot običajno; GitHub Actions objavi spremembe po commitu.

| Št. | Datum | Meetup | Lokalna mapa |
| --- | --- | --- | --- |
| 1 | 2023-09-14 | [Genesis meetup: prvo srečanje Bitcoin Maribor](https://www.meetup.com/bitcoin-maribor/events/295799198/) | `202309` |
| 2 | 2023-10-19 | [Kaj je denar?](https://www.meetup.com/bitcoin-maribor/events/296617495/) | `202310` |
| 3 | 2023-11-23 | [Bitcoin omrežje: kako se vključiti](https://www.meetup.com/bitcoin-maribor/events/297116095/) | `202311` |
| 4 | 2023-12-20 | [Strojne denarnice](https://www.meetup.com/bitcoin-maribor/events/297751006/) | `202312` |
| 5 | 2024-01-25 | [Prvi bitcoin: nakup in hramba](https://www.meetup.com/bitcoin-maribor/events/298581433/) | `202401` |
| 6 | 2024-02-27 | [ASIC rudarjenje bitcoina](https://www.meetup.com/bitcoin-maribor/events/299297257/) | `202402` |
| 7 | 2024-03-21 | [Novosti s konference Bitcoin Atlantis](https://www.meetup.com/bitcoin-maribor/events/299867135/) | `202403` |
| 8 | 2024-04-11 | [MiCA: evropska regulacija kriptosredstev](https://www.meetup.com/bitcoin-maribor/events/300205839/) | `202404` |
| 9 | 2024-05-30 | [Lightning denarnica in XOXO](https://www.meetup.com/bitcoin-maribor/events/301035999/) | `202405` |
| 10 | 2024-06-27 | [Genealogija tehnologije veriženja blokov](https://www.meetup.com/bitcoin-maribor/events/301708211/) | `202406` |
| 11 | 2024-08-29 | [Vprašanja udeležencev](https://www.meetup.com/bitcoin-maribor/events/302961636/) | `202408` |
| 12 | 2024-09-25 | [Finančna neodvisnost in FU money](https://www.meetup.com/bitcoin-maribor/events/303563160/) | `202409` |
| 13 | 2024-10-24 | [Nazaj k osnovam Bitcoina](https://www.meetup.com/bitcoin-maribor/events/304128285/) | `202410` |
| 14 | 2024-11-21 | [Zemljevidi in lokacije s plačili v bitcoinu](https://www.meetup.com/bitcoin-maribor/events/304602600/) | `202411` |
| 15 | 2025-01-15 | [Vprašanja udeležencev: januarski pogovor](https://www.meetup.com/bitcoin-maribor/events/305514749/) | `202501` |
| 16 | 2025-02-13 | [Bitcoin zakladnice in strategija podjetja Strategy](https://www.meetup.com/bitcoin-maribor/events/306026002/) | `202502` |
| 17 | 2025-03-20 | [NYKNYC: hramba ključev in varnostnih kopij](https://www.meetup.com/bitcoin-maribor/events/306644561/) | `202503` |
| 18 | 2025-04-18 | [Kriptografija in Bitcoin](https://www.meetup.com/bitcoin-maribor/events/307279799/) | `202504` |
| 19 | 2025-05-29 | [Zlom denarja: slovenski prevod knjige Lyn Alden](https://www.meetup.com/bitcoin-maribor/events/307975569/) | `202505` |
| 20 | 2025-07-31 | [Predlog zakona o kriptosredstvih: pripombe društva](https://www.meetup.com/bitcoin-maribor/events/310150440/) | `202507` |
| 21 | 2025-10-02 | [Kripto davek: predlog ZDDOKS in odziv društva](https://www.meetup.com/bitcoin-maribor/events/311243623/) | `202510` |
| 22 | 2025-11-06 | [Inflacija, prihranki in vrednost denarja](https://www.meetup.com/bitcoin-maribor/events/311807221/) | `202511` |
| 23 | 2025-12-01 | [Strojne denarnice: pregled 2025](https://www.meetup.com/bitcoin-maribor/events/312186660/) | `202512` |
| 24 | 2026-01-22 | [Zlorabe v svetu kriptovalut s Tadejem Hrenom](https://www.meetup.com/bitcoin-maribor/events/312876115/) | `202601` |
| 25 | 2026-02-05 | [Pogovor z Guyem Swannom](https://www.meetup.com/bitcoin-maribor/events/313188011/) | `202602` |
| 26 | 2026-03-10 | [Sestavljanje denarnice Specter DIY](https://www.meetup.com/bitcoin-maribor/events/313680496/) | `20260310` |
| 27 | 2026-03-26 | [Specter DIY: pogovor s Schnuartzom](https://www.meetup.com/bitcoin-maribor/events/313816710/) | `20260326` |
| 28 | 2026-04-23 | [Bitcoin posojila](https://www.meetup.com/bitcoin-maribor/events/314292140/) | `202604` |
| 29 | 2026-05-28 | [Kvantni računalniki in Bitcoin](https://www.meetup.com/bitcoin-maribor/events/314932502/) | `202605` |
| 30 | 2026-06-25 | [Bitcoin PlebWalk ob Dravi](https://www.meetup.com/bitcoin-maribor/events/315325907/) | `202606` |
| 31 | 2026-07-23 | [Podjetja iz okolice: BC Vault](https://www.meetup.com/bitcoin-maribor/events/315756905/) | `202607` |
| 32 | 2026-08-27 | [Sledenje gotovini](https://www.meetup.com/bitcoin-maribor/events/316218171/) | `202608` |

## Preverjanje prenosa

Končni pregled je opravljen 20. septembra 2026.

- Gradnja z Zolo 0.23.4 in `zola check --skip-external-links` uspeta.
- Vseh 32 datumov in naslovnih slik je primerjanih z manifestom; slike so veljavni JPEG-i z ustreznimi SHA-256.
- Tri predstavitve so besedilno enake različicam pred tem prenosom.
- V gradnji pod GitHubovo podpotjo je preverjenih 1.224 lokalnih povezav in šest strani kartic.
- V brskalniku so preverjeni naslovnica s šestimi naloženimi slikami, mobilni članek in iskanje. Iskanje »MiCA« vrne en dogodek, »Specter« pa dva ločena marčevska dogodka.
- Zola pri prosojnem razdelku podvoji dogodke v iskalnem indeksu. Pred vnosom v MiniSearch se zapisi zdaj združijo po URL-ju.
- Zunanje povezave v starih predstavitvah niso bile v celoti preverjene; objava na GitHubu še ni izvedena.
