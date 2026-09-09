# Outreach Pipeline — Hotel Business (Valentijn)

## Context

Ik run een AI-videoproductiebedrijf (cinematic walkthrough video's voor luxe villaverhuur, jachtcharters en e-commerce merken, gemaakt met Higgsfield AI / Kling 3.0 vanuit bestaande listingfoto's). Dit is de rulebook voor de **hotel-tak** van mijn outreach: onafhankelijke boetiekhotels en kleine hotelketens (niet de grote internationale ketens — die hebben eigen marketingbureaus). Dezelfde regio's als mijn villa/jacht-outreach: Zuid-Frankrijk, Amalfikust, Ibiza, Kroatië, Mallorca, Griekenland, Algarve, Costa Brava, plus uitbreidbaar naar andere Mediterrane regio's.

Dit is een aparte rulebook naast mijn bestaande villa/jacht-outreach — beide lopen naast elkaar, dit vervangt niets.

## Aanbod (voor context bij het schrijven van e-mails — niet 1-op-1 in de eerste cold e-mail dumpen)

- **Homepage-video**: één doorlopende video met gevel, entree en lobby/receptie, plus optioneel elke faciliteit (restaurant, pool, spa, gym, rooftop bar) als extra scène in dezelfde video
- **Kamertype-video's**: aparte video per kamer**type** (niet per fysieke kamer)
- Ook leverbaar in 9:16 verticaal voor TikTok, Instagram Reels en andere social kanalen
- Prijzen NIET in de cold e-mail zelf noemen — pas op verzoek delen (zie villa-outreach: leiden met portfolio, niet met prijs)

## Workflow (stap voor stap)

1. **Domeinlijst maken** — Ik geef een lijst hotels/regio (bv. "boetiekhotels Provence" of "kleine hotelketens Algarve"). Zoek per hotel het domein op en genereer:
   - een .txt bestand met alleen de domeinen (één per regel)
   - een .csv bestand met metadata per hotel: hotelnaam, land, aantal kamers (indien vindbaar), korte beschrijving (van hun website), domein

2. **Hunter.io stap** (handmatig door mij) — Ik upload de .txt in Hunter.io, doe de bulk search, en exporteer de CSV terug. Wacht op dat bestand voordat je verdergaat.

3. **Contact selecteren** — Lees de Hunter-CSV in. Kies per domein één contactpersoon (bij voorkeur richting marketing/general manager/eigenaar, anders de eerste beschikbare).

4. **E-mail genereren per hotel** — Gebruik het vaste hotel-sjabloon (zie hieronder). Vul in:
   - Hotelnaam
   - Korte beschrijving (uit stap 1)
   - Taal van de e-mail = taal van het land waar het hotel gevestigd is — vaste regel, nooit afwijken.

   Vaste elementen die NOOIT veranderen:
   - Self-filter regel: "als jullie al zelf videocontent produceren, is dit waarschijnlijk niet relevant" (vertaald naar de juiste taal)
   - Vermelding dat de video's gemaakt worden vanuit bestaande foto's — geen on-site shoot of filmploeg nodig (nooit AI noemen)
   - Eén gratis samplevideo aanbod (leidend met bestaand portfoliovoorbeeld — géén gratis custom video voor nieuwe prospects)
   - Contactgegevens: 06 57 24 96 07, sitedesignhaarlem@gmail.com
   - Onderwerpregel: "Video walkthroughs for your [HOTELNAAM]" (of vertaalde variant)
   - Nooit harde levertijden beloven — goedgekeurde formulering: "roughly 3 weeks"

   **Belangrijk:** gebruik voor het portfoliovoorbeeld een hotel-specifieke sample zodra die klaar is. Zolang die er nog niet is: vraag mij expliciet welk voorbeeld te gebruiken in plaats van zelf een villa/jacht-sample te kiezen — dat voelt niet relevant voor een hotel-prospect.

5. **Gmail-drafts aanmaken** — Maak per hotel een Gmail-draft (`Gmail:create_draft`). **Nooit** `Gmail:send_message` of directe reply-verzending gebruiken, ook niet als het "duidelijk" is wat er moet gebeuren. Sla NIET op als draft als het hotel al eerder is gecontacteerd (zie uitsluitingslijst hieronder — vraag mij om de actuele lijst te bevestigen/aan te vullen als die niet compleet is). Zet altijd expliciet het `to:` veld — nooit alleen op `replyToMessageId` vertrouwen. Verifieer na aanmaken altijd via `Gmail:list_drafts` dat de draft echt bestaat.

6. **Tracker-update** — Geef na afloop een overzicht in copy-paste-klare comma-separated rijen (hotel, contact gev., cold outreach, reactie, follow up?, dtm eerste outreach) zodat ik ze in mijn Google Sheet kan plakken. Gebruik een apart tabblad/kleur voor hotel-leads zodat ze niet vermengen met villa/jacht-leads.

## Verzend-discipline

- **Max. 100 e-mail-drafts per dag** klaarzetten. Dit is een aanzienlijk hoger volume dan mijn villa/jacht-outreach (45–55/dag) — spam-reputatie van Gmail blijft de harde grens, dus deze limiet niet overschrijden zonder mijn expliciete akkoord.
- Spreid de 100 drafts over meerdere sessies/momenten op de dag in plaats van alles in één keer te droppen, voor een natuurlijker verzendpatroon.
- Voor Amerikaanse hotels: draft-tijd richten op 15:00–17:00 Nederlandse tijd (= Amerikaanse business hours).
- Vraag altijd om bevestiging voordat je een grote batch (>25 hotels) in één keer draft, gezien het hoge dagelijkse volume.

## Uitsluitingen

- Ruis-afzenders bij het checken van reacties in Gmail negeren: <dm@danmartell.com>, <contact@mail.hunter.io>, <drive-shares-dm-noreply@google.com>, <noreply@clickup.com>, <team@mail.clickup.com>, <info@e.atlassian.com>, <no-reply@m.higgsfield.ai>, <no-reply@t.higgsfield.ai>, <contact@hunter.io>, <Info@updates.plus500.com>, <noreply@account.tiktok.com>
- Vraag mij altijd om de actuele "reeds gecontacteerd"-lijst te delen/updaten voor je een nieuwe batch start, zodat er geen dubbele outreach ontstaat — en check ook tegen mijn villa/jacht-lijst, voor het geval een hotelgroep ook een villa- of jachttak heeft.

## Tools die nodig zijn

- Higgsfield MCP (media/portfolio referenties indien nodig)
- Gmail MCP (create_draft, list_drafts, search_threads voor reply-monitoring)
- Google Drive MCP (tracker lezen/koppelen)

## Wat de agent NOOIT mag doen

- **Zelf e-mails versturen — nooit, onder geen enkele omstandigheid.** Alleen `Gmail:create_draft`. Geen `Gmail:send_message`, geen directe `Gmail:reply` zonder tussenstap als draft. Ik review en verstuur zelf, altijd.
- De self-filter regel, contactgegevens of het gratis-sample-aanbod wijzigen
- Prijzen (€150 basis, €40/faciliteit, €80-100/kamertype, +€20 voor 9:16) noemen in de eerste cold e-mail — alleen op verzoek delen
- Hotels opnieuw benaderen die al op de uitsluitingslijst staan (villa/jacht óf hotel)
- De dagelijkse verzendlimiet (100) overschrijden zonder expliciet akkoord
- Grote hotelketens benaderen — alleen onafhankelijke boetiekhotels en kleine ketens
