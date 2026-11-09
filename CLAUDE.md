# Østmoen Visuals – nettside

Ny nettside for Østmoen Visuals, et foto- og videoproduksjonsselskap i Drammen-området (Loe Bruk, Hokksund). Erstatter dagens Squarespace-side på ostmoenvisuals.com.

- **Eier:** Østmoen Visuals (Tobias Østmoen). Repo: https://github.com/Ostmoenvisuals/Ostmoenvisuals-web. Vercel-prosjektet ligger på deres konto.
- **Bygges av:** Torjus, eksternt, som collaborator på repoet.
- **Språk:** All tekst på sida er norsk bokmål. `<html lang="nb">`.

## Les dette først

| Fil | Hva |
| --- | --- |
| `design/README.md` | Den grafiske profilen: tone, logo, farger, typografi, bildestil, form og bevegelse. Følg den. |
| `design/tokens.css` | Alle farger, mellomrom, radier og tekststiler som CSS-variabler. Eneste kilde til verdier. |
| `design/components.css` | Ferdige klasser for knapp, chip, prosjektkort og Torv-seksjon. |
| `design/sidekart.md` | Sider, URL-er, seksjonene på hver side og redirects fra Squarespace. |
| `design/innhold.md` | Ekte tekster, kundeliste, tilbakemeldinger, kontaktinfo og prosjektlisten. |
| `src/assets/bilder/` | Utvalgte bilder, ferdig skalert (maks 1800 px, webp). |
| `public/logo/` | Logoen i SVG. Brukes som den er. |

Designskissene (forside, case-side, sidekart) og designsystemet ligger som artefakter på Torjus sin Claude-konto. Spør Torjus om skjermbilder hvis noe er uklart. Kilden for byggingen er filene i `design/`.

## Teknisk oppsett

- **Astro**, statisk output, deployes på Vercel. Ingen UI-rammeverk (React o.l.) med mindre det trengs for noe konkret.
- **Ren CSS.** Importer `design/tokens.css` og `design/components.css` globalt. Ikke Tailwind. Ingen hardkodede farger eller mål: bruk alltid variablene (`var(--surface)`, `var(--space-6)` osv.).
- **Font:** Manrope 400/500/600, self-hostet med `@fontsource/manrope` (ikke Google Fonts-lenke). Fjern `@import` av Google Fonts fra components.css når fontsource er på plass.
- **Bilder:** `astro:assets` (`<Image />` / `<Picture />`) med `src/assets/bilder/`. Alltid meningsfull `alt` på norsk.
- **Prosjekter:** Astro content collection i `src/content/prosjekter/*.md` (frontmatter: tittel, kunde, tjeneste, år, ingress, forsidebilde, galleri, sitat, utvalgt). Én case-side per prosjekt fra samme mal. Holdes slik at et CMS (f.eks. Sanity) kan kobles på senere uten å bygge om malene.
- **Sitemap og SEO:** `@astrojs/sitemap`. Forsidens `<title>` er «Videoproduksjon i Drammen – Østmoen Visuals». Meta description og Open Graph-bilde på alle sider.
- **Redirects:** 301 i `vercel.json`, se `design/sidekart.md`.
- **Ikke avklart ennå (bygg så det er lett å bytte):**
  - Video: showreel og case-filmer ligger trolig på YouTube. Lag en `Video`-komponent som laster spilleren først ved klikk (lite embed med stillbilde og play-knapp).
  - Kontaktskjema: mottaker og tjeneste er ikke valgt. Bygg skjemaet ferdig i UI, med handlingen samlet ett sted.
  - CMS: ikke valgt.

## Designregler i korte trekk

- Lyst og mykt: Papir (`--surface`) som grunn, tekst i Blekk (`--ink`), Brent oransje (`--accent`) bare som gnist: hovedknapp, overlinjer, lenker.
- **Én** mørk Torv-seksjon per side (`class="ov-section-torv" data-theme="torv"`), typisk showreel eller «neste prosjekt».
- Manrope, setningsbruk overalt. Versaler og bred sperring er forbeholdt logoen.
- Myke hjørner: `--radius-md` på kort og små bilder, `--radius-lg` på store bilder, `--radius-pill` på knapper og chips.
- Skill med farge og luft, ikke skygger. `--space-24` (96 px) mellom seksjoner på desktop.
- Bevegelse: rolige fade-ins (400–600 ms). Ingen zoom, parallakse eller film burn-effekter på sida. Respekter `prefers-reduced-motion`.
- Mobil først: alt skal fungere ned til 360 px bredde, minst 16 px sidemarg, ingen horisontal scroll.
- Tilgjengelighet: kontrastene i tokens.css er sjekket – ikke bytt farger på tekst uten å sjekke 4,5:1. Synlig fokusring (`--focus`), ekte `<a>`/`<button>`, `aria-current` i menyen.

## Innhold og fakta

- Ikke finn på fakta om kunder, prosjekter, år, tall eller sitater. Det som mangler skrives som `[plassholder]` og listes opp for Torjus.
- Kundesitater skal være ordrett fra `design/innhold.md` eller fra Tobias.
- Logoen tegnes aldri om, farges eller strekkes.

## Bilder fra den gamle sida

Alle bildene fra den gamle sida (1910 webp, 2500 px, sortert per side og prosjekt) ligger i `../ostmoen visuals bilder/`. Mappenavnene er de gamle URL-ene. Når en case-side bygges: velg 5–8 gode bilder fra prosjektets mappe, skaler til maks 1800 px og legg dem i `src/assets/bilder/prosjekter/<slug>/`. Ikke kopier hele mappa inn i repoet. `_kontaktark/` der inne er hjelpefiler og hører ikke til sida.

## Git og arbeidsflyt

- Repoet ble opprettet tomt på GitHub. Hvis mappa ikke er et git-repo ennå: `git init -b main`, `git remote add origin https://github.com/Ostmoenvisuals/Ostmoenvisuals-web.git`. Har remote allerede commits (f.eks. en README), hent dem først med `git pull origin main --allow-unrelated-histories`.
- Små, beskrivende commits. Etter at første versjon er på `main`: jobb i grener og lag pull requests, så Tobias kan se forhåndsvisningen fra Vercel før noe går live.
- Ikke commit `node_modules`, `.env` eller originalbilder.
