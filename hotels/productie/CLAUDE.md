# Production Pipeline — Hotel Business (Valentijn)

## Context

Deze rulebook stuurt de productie-agent voor de **hotel-tak** van mijn AI-videoproductiebedrijf. Zelfde onderliggende workflow als mijn villa/jacht-productie (Higgsfield AI / Kling 3.0 + ffmpeg, gegenereerd vanuit bestaande foto's, geen shoot), maar met eigen output-structuur en QC-aandachtspunten specifiek voor hotels. Draait naast de bestaande productie-CLAUDE.md, vervangt niets.

## Twee soorten output per hotel

1. **Homepage-video** — één doorlopend bestand: gevel/entree → lobby/receptie → optioneel elke faciliteit (restaurant, pool, spa, gym, rooftop bar) als losse scène binnen datzelfde bestand, aan elkaar gemonteerd met ffmpeg xfade. Dit is **niet** meerdere losse leverbare bestanden — controleer bij export dat het één file per hotel is.
2. **Kamertype-video's** — apart bestand per kamer**type** (Standard, Deluxe, Suite, Family Room, etc.), nooit per fysieke kamer. Vraag bij twijfel welke kamers hetzelfde type zijn i.p.v. zelf te gokken op basis van foto's alleen.

## Workflow (stap voor stap)

1. **Foto's ontvangen en sorteren** — Sorteer aangeleverde foto's per scène-categorie: gevel, entree, lobby, per kamertype, per faciliteit. Vraag om aanvulling als een categorie geen foto's heeft in plaats van een scène over te slaan zonder het te melden.
2. **Clips genereren** — Kling 3.0, 16:9 landscape, standaard 3s clips (4,5 credits) of 5s (7,5 credits) waar meer beweging nodig is, geluid uit. Camera zo stabiel mogelijk — geen handheld-achtige schok of drift, prompt hier altijd expliciet op sturen. Altijd een start- en eindframe zoeken/opgeven voor de interpolatie, voor elke scène (niet alleen interieur) — nooit clips genereren zonder eindframe tenzij er écht geen geschikt eindframe te vinden of te maken is.
3. **Dubbele QC per clip, vóór montage:**
   - Geometrische vervorming / JERK-score via OpenCV optical flow
   - Hallucinatie-detectie (extra objecten, vervormde meubels/personen)

   **Hotel-specifieke aandachtspunten** die vaker fout gaan dan bij villa's/jachten:
   - Rechte lijnen in lobby's (kolommen, plafondranden, vloertegels) zijn extra gevoelig voor vervorming — visueel controleren, niet alleen op JERK-score vertrouwen
   - Spiegels en glaswanden (veel in lobby's) veroorzaken vaker false positives/negatives bij hallucinatie-detectie — handmatig nachecken bij twijfel
   - Zwembadwater/reflecties geven vaak vervorming — extra kritisch beoordelen bij poolscènes
   - Symmetrische meubelopstellingen (rijen loungestoelen, identieke kamers) — check dat de AI geen extra of ontbrekende items toevoegt
4. **Falende clips** — Regenereren, nooit doorlaten "omdat het er in de miniatuur oké uitziet."
5. **Montage** — ffmpeg xfade, in de vaste scène-volgorde voor de homepage-video (gevel → entree → lobby → faciliteiten). Kamertype-video's blijven losse bestanden.
6. **Levering** — Standaard 16:9. Op verzoek (of standaard meesturen als optie) ook 9:16 verticaal per video, voor TikTok/Instagram Reels.

## Bestandsnaamgeving

- Homepage: `[Hotelnaam]_Homepage.mp4`
- Kamertype: `[Hotelnaam]_Room_[Type].mp4` (bv. `[Hotelnaam]_Room_Deluxe.mp4`)
- Verticale variant: voeg `_9x16` toe vóór de extensie

## Tools die nodig zijn

- Higgsfield MCP (generatie)
- ffmpeg (montage, xfade)
- OpenCV-gebaseerde QC-scripts (JERK-score, hallucinatie-detectie)

## Wat de agent NOOIT mag doen

- Clips samenvoegen tot een homepage-video vóórdat elke clip individueel de dubbele QC heeft doorstaan
- Een kamertype-video maken voor een kamer die al gedekt is door een bestaand kamertype, zonder dit expliciet te melden
- Faciliteitsscènes als apart leverbaar bestand exporteren — deze horen altijd in de homepage-video
- Een duidelijk vervormde clip doorlaten omdat regenereren tijd kost
- Een clip genereren zonder eerst een eindframe te zoeken/proberen — alleen overslaan als er echt geen bruikbaar eindframe voorhanden is, en dan expliciet melden
- Camerabeweging in de prompt laten die niet zo stabiel mogelijk is (schokkerig, drift, handheld-gevoel)
