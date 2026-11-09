# Sidekart

Fem punkter i menyen: **Video, Foto, Prosjekter, Om oss, Kontakt** (Kontakt som mørk pill-knapp til høyre). Logoen (full, svart) til venstre lenker til forsiden.

| Side | URL | Innhold |
| --- | --- | --- |
| Forside | `/` | Se seksjoner under |
| Video | `/video` | Merkevarefilm, kursvideo, internfilm, annonsefilm. Utvalgte videoprosjekter. |
| AI-dubbing og teksting | `/video/ai-teksting` | Undersiden for AI-oversetting, teksting og dubbing av video |
| Foto | `/foto` | Portrett og profil, miljø og arbeid, interiør og produkt, event. Utvalgte fotoprosjekter. |
| Prosjekter | `/prosjekter` | Oversikt over alle prosjekter, filter Video / Foto |
| Case | `/prosjekter/<slug>` | Én side per prosjekt fra samme mal (28 prosjekter, se innhold.md) |
| Om oss | `/om-oss` | Tobias og historien, godkjent lærlingbedrift, bak kamera-bilder |
| Kontakt og priser | `/kontakt` | Prisnivåer, kontaktskjema, telefon, e-post, adresse |
| Personvern | `/personvern` | Personvern og rettigheter (lenke i bunnteksten) |

## Forsiden, fra topp til bunn

1. **Header:** logo, meny.
2. **Hero:** overlinje «Foto og video · Drammen» (accent), `display`-overskrift «Effektive foto- og videoproduksjoner.», ingress, knappene «Se prosjekter» (primær) og «Priser og kontakt» (kontur). Til høyre et stort bilde (`bts-kyst`, `--radius-lg`) med chip «Bak kamera». Senere: kort, lydløs loop fra showreel.
3. **Kundeliste:** «Noen av våre kunder» + navn, mellom to hårfine linjer.
4. **Tjenester:** overskrift «Innhold i alle formater, til alle kanaler.» og tre kort i Leire: Video, Foto, AI-dubbing og teksting.
5. **Utvalgte prosjekter:** 2 × 2 prosjektkort (Troll Trevarefabrikk, Magnat Kaffehus, Eske interiør, Fredensborg Fritid) + «Se alle prosjekter».
6. **Showreel:** den ene Torv-seksjonen. «Se hva vi har laget for andre.», knapp «Spill av showreel», stillbilde med play-knapp (`drone-solnedgang`).
7. **Om oss:** portrett av Tobias (4:5) og kort tekst, lenke «Mer om oss».
8. **Det kundene sier:** tre sitater med hårfin linje over.
9. **Kontakt-CTA:** Leire-flate, «Har du et prosjekt på gang?», knapp «Book en prat», telefon og e-post.
10. **Bunntekst:** logomerke, adresse og org.nr., kontakt, sosiale medier, personvern, «Godkjent lærlingbedrift».

## Case-siden, fra topp til bunn

1. Header (Prosjekter markert med `aria-current="page"`).
2. Brødsmule «Prosjekter / <navn>», overlinje (tjeneste · bransje), `display`-tittel, ingress. Til høyre en faktaliste (`<dl>`): Kunde, Tjeneste, År, Leveranse.
3. Stort bilde i 21:9.
4. To kolonner: «Oppdraget» og «Slik løste vi det».
5. Bildegalleri i rutenett, ett høyt bilde + fire.
6. Video (hvis prosjektet har film).
7. Kundesitat (hvis det finnes).
8. «Neste prosjekt» i Torv-seksjonen.
9. Kontakt-CTA «Vil du ha noe lignende?» og bunntekst.

## Redirects fra Squarespace (301, i vercel.json)

| Gammel | Ny |
| --- | --- |
| `/hjem` | `/` |
| `/videoproduksjon` | `/video` |
| `/fotografering` | `/foto` |
| `/ai-oversetting-teksting-dubbing-videoinnhold` | `/video/ai-teksting` |
| `/omoss` | `/om-oss` |
| `/kontakt` | `/kontakt` (uendret) |
| `/personvern-og-rettigheter` | `/personvern` |
| `/<prosjekt-slug>` (f.eks. `/nordnet`, `/kron`) | `/prosjekter/<prosjekt-slug>` |

Prosjekt-slugene er de samme som mappenavnene i `../ostmoen visuals bilder/` (se innhold.md). Sjekk de gamle URL-ene mot Squarespace før lansering.
