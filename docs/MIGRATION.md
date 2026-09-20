# Prvotni prenos vsebine iz GitHuba

**Zgodovinsko poročilo:** po tem prvem prenosu je arhiv dopolnjen na 32 meetupov. April 2024 in februar 2025 sta razrešena, naslovne slike pa prenesene z Meetupa. Aktualno stanje opisuje [MEETUP-IMPORT.md](MEETUP-IMPORT.md). Seznam manjkajočih notranjih prilog spodaj ostaja veljaven.

Vir vsebine: https://github.com/bitcoin-maribor/meetup, commit `b48033906e595d099717d9bfcc050280545f34c5`.
Tema: https://github.com/thomasweitzel/zolarwind, commit `b793bc2bff6d31da193fcc8f337729db7e399a76`.
Prenos: 19. september 2026. Izvorna direktorija sta ostala nespremenjena.

## Uredniške odločitve

- 18 izvornih datotek je združenih v 16 zapisov: 15 objavljenih meetupov in en osnutek.
- Predstavitvi za oktober 2023 in marec 2024 sta združeni z opisoma istih dogodkov. Marec 2025 vsebuje predstavitev.
- Naslovi in kratki povzetki za navigacijo so v slovenščini. Izvirna besedila ostajajo v izvirnem jeziku; podvojeni datumi so odstranjeni iz opisov.
- `202404.md` ponavlja december 2023, vključno z datumom 20. 12. 2023. Prenesen je kot `draft = true`. Datum `2024-04-01` je samo mesto za razvrščanje in ga je pred objavo treba popraviti. Vidno pri `zola serve --drafts`.
- README vira povezuje `202502.md`, ki ne obstaja. Zapisa za februar 2025 nismo ustvarili.
- Napoved »TBA – kriptografija« nima datuma ali opisa; ni predstavljena kot potrjen prihodnji dogodek.
- Povezava `btcmap.org` je popravljena na `https://btcmap.org/`.
- Stari URL-ji `/meetup-notes/*.html`, `*.md` in pot brez končnice preusmerjajo na nove strani. Aprilski URL-ji so aktivni šele ob objavi osnutka.
- Povezave do izvirnih datotek ostajajo pri vsakem meetupu za primerjavo; nadaljnje urejanje poteka v `content/meetups/LLLLMM/index.md`.

## Manjkajoče priloge

Slike, zapisane z Obsidian sintakso `![[...]]`, niso v izvirnem repozitoriju.
Na strani je opomba, posamezna imena pa so ohranjena v HTML komentarjih v Markdownu.
Ko dobite slike, jih dodajte v `static/img/meetups/` in komentar zamenjajte s standardno Markdown sliko.

### 2023-10-19-Kaj-je-denar.md

- `Pasted image 20231019171033.png`
- `Pasted image 20231019172552.png`
- `Pasted image 20231019172502.png`
- `Pasted image 20231019173201.png`

### 2024-03-21-Bitcoin-MB-meetup-Bitcoin-Atlantis.md

- `IMG_20240302_112930.jpg`
- `IMG_20240307_110530.jpg`
- `IMG_20240304_160731.jpg`
- `IMG_20240304_101919.jpg`
- `IMG_20240302_190848.jpg`
- `IMG_20240302_190845.jpg`
- `IMG_20240306_204021.jpg`
- `IMG_20240306_205948.jpg`
- `IMG_20240303_092857.jpg`
- `IMG_20240305_132507.jpg`
- `IMG_20240305_131358.jpg`
- `IMG_20240306_124910.jpg`
- `IMG_20240306_122535.jpg`
- `IMG_20240306_122450.jpg`
- `IMG_20240305_140054.jpg`
- `IMG_20240304_185413.jpg`
- `IMG_20240304_185225.jpg`
- `IMG_20240305_123147.jpg`
- `IMG_20240305_170527.jpg`
- `IMG_20240306_161604.jpg`
- `IMG_20240306_185447.jpg`
- `IMG_20240307_132605.jpg`
- `IMG_20240307_114050.jpg`
- `IMG_20240307_115654.jpg`
- `IMG_20240304_113916.jpg`
- `IMG_20240305_150241.jpg`
- `IMG_20240305_182050.jpg`
- `IMG_20240306_172601.jpg`
- `IMG_20240307_110833.jpg`
- `IMG_20240306_164628.jpg`
- `IMG_20240301_083417.jpg`
- `IMG_20240301_092059.jpg`
- `IMG_20240301_155801.jpg`
- `IMG_20240301_172549.jpg`
- `IMG_20240303_094805.jpg`
- `photo_2024-03-03_10-16-15.jpg`
- `IMG_20240301_084828.jpg`
- `IMG_20240302_171448.jpg`
- `17108543579727748942359521248839.jpg`
- `RY3T_ONE_Product_6.jpg`
- `IMG_20240301_102021.jpg`
- `SEC01-url.png`
- `IMG_20240304_165326.jpg`

### 2025-03-20-Bitcoin-MB-meetup-NYKNYC.md

- `meetup_6_qr.png`


## Izvorna postavitev teme in naslovne slike

Po uskladitvi videza so odstranjene lastne vizualne predloge in CSS. Stran uporablja izvorne Zolarwind kartice s slikami in paginacijo po šest zapisov. Datoteke meetupov so preseljene v mape z `index.md` in `banner.webp`; javni URL-ji ostajajo enaki. Naslovne slike so začasni primeri iz teme, opisani v `PREVIEW-IMAGES.md`.
