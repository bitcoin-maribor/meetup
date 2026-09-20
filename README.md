# Bitcoin Maribor

Samostojna statična stran skupnosti Bitcoin Maribor, zgrajena z Zolo in priloženo temo Zolarwind. Vključuje arhiv meetupov, predstavitve, slovenski vmesnik, lokalno iskanje, svetli/temni način in Atom vir.

## Lokalni zagon

Potrebujete **Zolo 0.23.4** (preizkušena različica, uporabljena tudi v GitHub Actions). Tema je vključena v repozitorij; Node.js in Git submoduli niso potrebni.

```sh
cd bdsmb-website
zola serve
```

Odprite **http://127.0.0.1:1111**. Zola ob shranjevanju vsebine ali predlog ponovno zgradi stran in osveži brskalnik. Če je vrata 1111 že zasedla druga stran: `zola serve --port 1112`.

Med delovanjem `zola serve` gradite produkcijsko različico v drug direktorij, npr. `zola build --output-dir /tmp/bdsmb-production`. Tako produkcijske datoteke ne prepišejo datotek predogleda. Če po urejanju JavaScripta brskalnik poroča o napačni kontrolni vsoti (`integrity`), ponovno zaženite `zola serve`.

```sh
zola check --skip-external-links
zola build
```

Končna statična stran nastane v `public/`; ta direktorij ni del repozitorija.
`zola check` brez dodatnih zastavic preveri tudi zunanje povezave, kar zahteva internet in je odvisno od dosegljivosti starih strani.

## Dodajanje in urejanje meetupov

Vsebina je v **`content/meetups/`**. Vsak meetup ima svojo mapo z `index.md` in naslovno sliko `banner.jpg`. Ime mape določa URL, npr. `202503/index.md` → `/meetups/202503/`.

1. Ustvarite mapo `content/meetups/LLLL-MM-DD-naslov/` in vanjo kopirajte `examples/meetup.md` kot `index.md`.
2. V začetnem bloku TOML med `+++` uredite naslov, opis, dejanski datum in teme. `date` pomeni datum srečanja in določa vrstni red.
3. Pod blokom napišite opis, lokacijo, povezavo do prijave in po srečanju dodajte gradiva. Za naslovno sliko dodajte `banner.jpg` ob `index.md` in pod `[extra]` nastavite `image = "banner.jpg"`. Tema jo prikaže nad kartico na seznamu in na vrhu članka.
4. Za predogled osnutkov uporabite `zola serve --drafts`.
5. Ko je zapis pripravljen, nastavite `draft = false` ali odstranite to vrstico.
6. Shranite spremembo na glavno vejo `main`. Po začetni nastavitvi GitHub Pages se stran samodejno objavi.

Za sliko ustvarite npr. `static/img/meetups/srecanje.jpg` in jo vključite z `![Opis slike](/img/meetups/srecanje.jpg)`. Za objavo tudi pod podpotjo uporabite priloženi shortcode `{{<image page={page} src="/img/meetups/srecanje.jpg" alt="Opis slike" />}}` (možnosti v `themes/zolarwind/docs/shortcodes.md`). Dokument PDF lahko shranite v `static/gradiva/` in povežete iz zapisa.

Vsebino lahko urejate neposredno na GitHubu: odprite Markdown datoteko, izberite **Edit**, nato **Commit changes**. Pull request pred objavo preveri gradnjo; merge v `main` sproži objavo. Spletna stran se posodobi po uspešni gradnji in objavi, običajno v nekaj minutah.

## Prva objava na GitHub Pages

**Vsebina tega direktorija naj bo koren novega repozitorija**, tako da sta `zola.toml` in `.github/` neposredno v korenu. Tema je že vključena. Datotek iz sosednjih direktorijev `meetup` ali `zolarwind` ne potrebujete.

1. Ustvarite prazen repozitorij na GitHubu z glavno vejo `main` in vanj naložite vsebino tega direktorija, vključno s skritim direktorijem `.github/`.
2. V **Settings → Pages → Build and deployment → Source** izberite **GitHub Actions**.
3. V zavihku **Actions** zaženite **Build and deploy Zola → Run workflow**, če je prvi zagon pred nastavitvijo Pages spodletel.
4. Po uspešni objavi preverite povezavo, prikazano v **Settings → Pages**.

Workflow preveri vsebino, zgradi stran in objavi `public/` z uradnimi GitHub Pages actions. Uporablja `GITHUB_TOKEN`; osebni žeton ali veja `gh-pages` nista potrebna. URL za gradnjo prebere iz nastavitev GitHub Pages, zato deluje tudi začetni naslov `https://bitcoin-maribor.github.io/IME-REPOZITORIJA/`.

### Prehod obstoječe domene

Projekt vsebuje `base_url = "https://www.bitcoin-maribor.si"` in `static/CNAME` za obstoječo domeno. Sama datoteka CNAME pri objavi z Actions ne nastavi domene v GitHub Pages.

Ko je nova stran preverjena, v **Settings → Pages → Custom domain** novega repozitorija nastavite `www.bitcoin-maribor.si` in vključite **Enforce HTTPS**, ko je na voljo. Če je domena še vezana na stari repozitorij `meetup`, jo najprej odstranite iz njegovih nastavitev Pages. Domeno premaknite šele ob dejanskem prehodu. DNS za poddomeno `www` naj s CNAME kaže na `bitcoin-maribor.github.io`, ne na pot do repozitorija. Preverite obstoječe DNS nastavitve pred spremembo.

Po spremembi domene ponovno zaženite workflow, da so vse povezave, Atom in sitemap zgrajeni s pravim naslovom. Za trajno uporabo druge domene spremenite tudi `base_url` in `static/CNAME`; za uporabo samo `github.io` odstranite `static/CNAME`.

Nastavitve domene in objava na GitHubu še niso izvedene; ta projekt je pripravljen za poznejši prenos.

## Struktura in prilagoditve

| Pot | Namen |
| --- | --- |
| `content/meetups/` | Meetupi in predstavitve |
| `content/pages/` | Stran o skupnosti in iskalnik |
| `templates/search.html` | Iskalnik teme z dodano dostopno oznako statusa |
| `static/js/search.js` | Prilagoditev iskanja za slovenski indeks |
| `i18n/sl.toml` | Slovenski prevodi vmesnika |
| `themes/zolarwind/` | Vključena kopija teme z izvirnimi licencami |
| `zola.toml` | Naslov strani, meniji, povezave in nastavitve |
| `.github/workflows/pages.yml` | Gradnja ob PR in objava ob spremembi `main` |
| `docs/MEETUP-IMPORT.md` | Pregled prenosa vseh 32 dogodkov z Meetup.com |
| `docs/meetup-sources.json` | Izvorni URL-ji, datumi in viri naslovnih slik |
| `docs/MIGRATION.md` | Zgodovina prvega prenosa iz GitHuba in manjkajoče priloge |

Stran uporablja izvorni videz in predloge Zolarwind za naslovnico, kartice s slikami, članke, navigacijo ter nogo. Lastnega CSS ali vizualnih prepisov predlog ni. Izjema je dostopna oznaka statusa v iskalniku, ki ne spreminja videza. Zolarwind ohranja svoj prevedeni Tailwind CSS. Če spreminjate njegov `css/main.css` ali dodajate nove Tailwind razrede, potrebujete Node.js: v `themes/zolarwind/` zaženite `npm ci` in `npm run css:build` ter vključite spremenjeni `static/css/generated.css` v commit. Za običajno urejanje vsebine tega ne potrebujete.

Slovensko iskanje uporablja Zolin `fuse_javascript` indeks in MiniSearch iz teme. Vsa sredstva se nalagajo lokalno; zunanje povezave se odprejo šele ob kliku. Komentarji in sledenje niso vključeni.

Datumske predloge tega projekta uporabljajo strftime za Zolo **0.23.4**, čeprav README vključene teme opisuje 0.23.5. Pri nadgradnji na 0.23.5 preverite spremembo datumskih vzorcev v Tera in posodobite vse `date(format=...)` ter `settings_date_format`, vključno s podedovanimi predlogami; nato posodobite različico in SHA-256 v workflowu. Različice so namenoma pripete, da lokalna in CI gradnja ostaneta primerljivi.

## Vsebina in naslovne slike z Meetup.com

Stran vsebuje **32 preteklih dogodkov** od septembra 2023 do avgusta 2026 in **33. meetup, Sokratski seminar**, napovedan za 24. september 2026. Besedilo vsakega članka je v celoti preneseno iz objave [skupine Bitcoin Maribor](https://www.meetup.com/bitcoin-maribor/) na Meetup.com, vključno z angleškimi različicami, napovedmi kraja in povezavami. Kratek opis na kartici je odlomek iz iste objave. Obstoječe predstavitve iz GitHuba so ohranjene pod izvirnimi opisi.

Naslovne slike so prenesene iz objav in shranjene lokalno kot `banner.jpg`. Nekaj dogodkov ima enako društveno grafiko, ker je enaka tudi na Meetupu. Prvi dogodek uporablja skupinsko sliko, ki jo prikazuje Meetup. To niso več vzorčne slike teme. Za zamenjavo prepišite sliko v mapi dogodka ali uredite `image` pod `[extra]`.

Podrobnosti, odpravljene neskladnosti in viri so v [poročilu o prenosu](docs/MEETUP-IMPORT.md) ter [manifestu virov](docs/meetup-sources.json). Marec 2026 ima dva dogodka v mapah `20260310` in `20260326`. Drugi dogodki ohranjajo mesečne poti, npr. `202503` in `202609`.

Gradnja in lokalni zagon ne potrebujeta dostopa do Meetupa. Poznejše spremembe na Meetupu se ne prenašajo samodejno; besedila urejajte v tem repozitoriju.

## Prenesena vsebina in licence

Objavljenih je 33 meetupov, od tega eden prihajajoči. April 2024 je popravljen po objavi o MiCA, februar 2025 je dopolnjen. Ohranili smo tri predstavitve iz GitHuba; njihovih 48 notranjih slikovnih prilog še vedno manjka v izvirnem repozitoriju. Seznam prilog je v [poročilu prvega prenosa](docs/MIGRATION.md). Naslovne slike z Meetupa teh prilog ne nadomeščajo.

Vsebina iz repozitorija Bitcoin Maribor je pod licenco MIT (`LICENSE`); Zolarwind in vključene knjižnice ohranjajo svoje licence v `themes/zolarwind/`. Slike iz Meetup objav so gradivo skupine; ne spadajo pod licenco Unsplash za vzorčne slike teme. Njihovi izvorni URL-ji so navedeni v manifestu virov.

Referenci za objavo: [Zola – GitHub Pages](https://www.getzola.org/documentation/deployment/github-pages/) in [GitHub – custom workflows](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages). Za domeno: [GitHub – managing a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
