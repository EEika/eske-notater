+++
schema_version = 3
id = "01a11b12-cc12-706a-967d-5f11a07dd44f"
kind = "note"
state = "open"
created_at = "2026-10-08T10:32:59Z"
updated_at = "2026-11-16T12:57:11Z"
title = "Møte om Tilsagnsbrev"
tags = ["bml", "depot-tieto", "møte", "note", "tilsagnsbrev"]
log_seq = 7

[husk]
defer_count = 0
interval_days = 3
review_count = 0
+++

# Møte om Tilsagnsbrev

## Møte - 08.10.26

- Annca
- Espen
- Reidar Larsen
- Marianne Alvetun

## Agent for å validere tilsagsbrev

Problemstilling: Høy feilprosent i tilsagnsbrev

- Øker tid
- Ping-Pong med Depot

Tilbudsbrev må stemme mot hva som er besluttet i kreditt.
Tomme felter er fjernet. Skal se proffesjonelt ut
(Formatering og visning)

Rådgiver er tenkt å bruke agenten.
Eksisterer i dag som en et kontrollverktøy

Depot trenger bekreftelse på at rådgiver faktisk har rydder opp / fikset mangler som er belyst

Sterkt kobling mellom hva som krevers, og hva som finnes i LP, uten at det er noen direkte integrasjon.

Tilsagnsbrevet er produsert fra alt de har lagt inn i LP.

LP -> Tilsagnsbrev

De skriver (Formål, ballong, ) i tilsagsbrev, selv om en del alt er utfylt.
(Mulig å gjøre en validering / regex-sjekk for oversendelse?)

## Foundry versjon

- Behov for å lese / tolke PDF

## Møte - 14.10.26

- Annca
- Espen
- Reidar Larsen
- Marianne Alvetun

Reidar og Marianne har hatt begrenset med tid til å se videre på dette.

Tilbudsbrevet er et produkt av hva som ligger i LP.

Burde være en agent som kun sjekket tilbudsbrevet, uten å bli for ordrik

Problemer med å finne tinglysningsgebyr, oppdatert liste. Høre med kundetjenester om noe kan gjøres / tilgjengeligjøre.

Det fantes ikke egentlig noen api-tjeneste for dette, men var oppdatert så sjeldent at det kunne vært gjort manuelt
