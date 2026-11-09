# Østmoen Visuals

Grafisk profil for Østmoen Visuals, et foto- og videoproduksjonsselskap i Drammen. Profilen er lys, myk og varm, med et hint av torv-brunt. Den er laget for at bildene og videoene deres skal stå i sentrum.

Versjon 1, november 2026. Retning «B+ Dagslys med torv». Logoen er uendret.

## Hvem vi er og hvordan vi høres ut

Østmoen Visuals lager moderne og effektive foto- og videoproduksjoner for bedrifter: merkevarefilm, kursvideo, internfilm, korte annonser og foto. Kundene er bedrifter i hele Norge, de fleste i Oslo-området.

Stemmen er rolig, direkte og varm, som en fagperson som forklarer noe over en kaffe.

- **Kort og konkret.** «Vi lager foto og video for bedrifter.» Ikke «Vi skaper unike visuelle opplevelser».
- **Vi og du.** Vi snakker som Østmoen Visuals («vi») til kunden («du»).
- **Setningsbruk overalt.** Versaler er forbeholdt logoen. Overskrifter slutter gjerne med punktum når de er en hel setning.
- **Verb først på knapper.** «Se prosjekter», «Book en prat», «Spill av showreel».
- **Ingen tomme superlativer.** La kundelistene og arbeidet tale for seg.

## Logo

Logoen brukes som den er, og den tegnes ikke om. Den finnes i to versjoner: full logo (Ø-merke over ØSTMOEN VISUALS) og logomerke (bare Ø-merket). Begge finnes i svart (Blekk) og hvitt. Filene ligger i `public/logo/`.

- Svart logo på Papir, Leire og Sand. Hvit logo på Torv og på mørke bilder.
- Full logo i toppen av nettsida, på visittkort og der merket presenteres for første gang. Logomerket der det er trangt, for eksempel som profilbilde, i hjørnet av et Instagram-innlegg og som favicon.
- Fritt rom rundt logoen tilsvarer minst høyden av Ø-en i ØSTMOEN.
- Minste bredde er 96px for full logo og 20px for logomerket.
- Logoen farges aldri i Brent, Sand eller andre farger, og legges ikke på urolige deler av et bilde.

## Farger

Paletten er hentet fra varmt dagslys og film burns. Papir er grunnen, Torv er det mørke pustet, og Brent oransje er gnisten.

| Farge | Kode | Andel | Bruk |
| --- | --- | --- | --- |
| Papir | `#F5F1EA` | ~55 % | Grunnen i nesten alt |
| Leire | `#E7DED0` | ~15 % | Kort, bildefelt, rolige flater |
| Sand | `#C9B9A3` | ~6 % | Linjer, plassholdere, dempet tekst på Torv |
| Valnøtt | `#6E5F55` | ~6 % | Dempet tekst på lyse flater |
| Torv | `#2B211C` | ~10 % | Én mørk flate per side |
| Blekk | `#1A1A1A` | ~6 % | Tekst og logo |
| Brent | `#B8461F` | ~2 % | Hovedknapp, markering |

Grensesnittet bruker de semantiske tokenene (`surface`, `ink`, `accent` og så videre), ikke merkefargene direkte. Temaet **Dagslys** er standard. Temaet **Torv** brukes inne i den mørke seksjonen. Sett `data-theme="torv"` på seksjonen, så bytter alle tokens.

Kontrast: All tekst holder minst 4,5:1 mot sin bakgrunn i begge temaer. Sand brukes aldri som tekst på Papir. Brent oransje lysner til `#E58A5F` på Torv.

## Typografi

Én familie: **Manrope** (Google Fonts), i vektene 400, 500 og 600.

- Overskrifter i Medium (500) med stram sperring (−0,035 em til −0,015 em). Det gir et moderne og rolig uttrykk.
- Brødtekst i Regular (400), 16–18px med god linjeavstand. Linjene holdes rundt 65 tegn.
- Etiketter, knapper og overlinjer i SemiBold (600), 13–15px.
- Logoen er den eneste teksten med bred sperring og versaler. Ingen andre tekster etterligner den.

Stilene `display`, `h1`, `h2`, `h3`, `body-lg`, `body`, `label` og `caption` er klasser i `design/tokens.css`. På mobil krymper `display` til omtrent 40px og `h1` til omtrent 34px.

## Bildestil

Bildene og videoene er hovedinnholdet. Profilen rundt er rolig, slik at de får plassen.

Bildestilen finnes allerede i arbeidet deres, og profilen er bygget rundt den. Se bildene i `src/assets/bilder/`.

- **Lys:** naturlig dagslys, varmt verkstedlys eller gyllen time. Gjerne motlys og litt glød i høylysene, som i videoene.
- **Farge:** varm hvitbalanse, dempet metning og myke svarttoner. Unngå kjølige, blå toner.
- **Dybde:** kort dybdeskarphet, med motivet skarpt og bakgrunnen myk.
- **Innhold:** ekte mennesker i arbeid, bak kamera og hos kunden. Portretter mot varme, rolige bakgrunner. Ikke stockbilder.
- **Form:** bilder har avrundede hjørner (`radius-md` for små og kort, `radius-lg` for store) og står i 16:10, 16:9 eller 4:5.
- **Film burns** hører hjemme i videoene og showreelen, ikke som pynt i design eller på nettsida.

Paletten er valgt for å ligge ved siden av disse bildene: Papir, Leire og Sand tar opp de varme tonene, og Torv de myke skyggene.

## Form, luft og layout

- **Myke hjørner** hentet fra den avrundede sekskanten i logomerket: 8px, 14px, 24px og 28px, og helt runde knapper.
- **Mye luft.** 96px mellom seksjoner på desktop. Sidemarg 56px på desktop og 16px på mobil.
- **Skill med farge og luft**, ikke med skygger og rammer. `shadow-lift` er bare for mockups av trykksaker.
- **Hårfine linjer** (`line`) skiller seksjoner der det trengs, for eksempel over kundelisten.
- **Asymmetrisk og rolig.** Tekst til venstre og bilde til høyre i hero, og store bilder som får stå alene.

## Bevegelse

Bevegelse skal føles som en scene som tones inn.

- Elementer fader inn (opasitet og 8–12px forskyvning) over 400–600 ms, med en myk easing.
- Hover på knapper og kort: endring i farge over 200 ms. Ingen zoom, sprett eller parallakse.
- Respekter `prefers-reduced-motion`: da vises alt uten animasjon.

## Komponenter

Komponentene er klasser i `components/bundle.css` som bygger på tokenene: `ov-btn` (Button), `ov-chip` (Chip), `ov-card` (ProjectCard) og `ov-section-torv` (TorvSection). Legg `ov-root` på body. Klassene ligger i `design/components.css`.

## Det vi ikke gjør

- Endrer, farger eller strekker logoen.
- Bruker versaler eller bred sperring i overskrifter.
- Bruker mer enn én Torv-seksjon eller én hovedknapp per skjermbilde.
- Bruker gradienter, tunge skygger eller effekter som film burns og korn i grensesnittet.
- Bruker Brent oransje på store flater.
