+++
schema_version = 3
id = "01a211a1-50f6-76db-a854-0d4164d0ad32"
kind = "note"
state = "open"
created_at = "2026-11-25T07:35:14Z"
updated_at = "2026-11-25T07:37:41Z"
title = "Arkitektur - lånesøknad (mermaid)"
tags = ["note"]
log_seq = 2
+++

# Arkitektur - lånesøknad (mermaid)

```mermaid
flowchart LR
    Radgiver([Rådgiver]) --> Radgiverportal[Rådgiverportal]
    Kunde([Kunde]) --> Digital[Digital lånesøknad]
    Radgiverportal --> API[corporate-loan-application-api]
    Digital --> API
    API --- Workers[corporate-loan-workers]

    Workers --> Camunda[camunda]
    Workers -->|Prekvalifisering| Decision[loan-decision-api<br/>beslutningsmotor]
    Workers -->|Salgsmulighet| CRM[crm-api<br/>dynamics]
    Workers -->|Vedlegg| Doc[document-api]
    Workers -->|Engasjement| Account[account-api]
    Workers -->|Engasjement| Customer[customer-api]
    Workers -->|Kredittsjekk| Credit[credit-information-api]
    Workers -->|Engasjement| LoanInfo[loan-information-api]
    Workers -->|Matrikkel / Eiendomsverdi| RE[realestate-api]

    API --> Soknad[(Søknad / Historikk)]
    Workers --> Soknad
    Soknad --> DVH[(Datavarehus / Databricks)]

    Forretning([Forretning]) -->|Innsikt| PowerBI[PowerBI]
    Forretning -->|Innsikt| AIchat[AI chat]
    PowerBI --> DVH
    AIchat --> DVH
    DVH -->|Overføring av engasjement til API| LoanInfo

    subgraph Stacc
        BM[BM analyse] --> Logg[(Innsynslogg / Case)]
        BM --> DB[Dun & Bradstreet<br/>Kredittsjekk - Bisnode]
    end

    subgraph Tieto
        KG[Kundegruppe API]
        LP[LP API - ECPS]
        Kjerne[(Kjerne)]
    end

    subgraph SimCorp
        Swap[Swap-avtaler]
    end

    API -->|Opprett sak / Hent sak| BM
    API -->|Hent kredittsjekk| DB
    API -->|Hent kundegruppe| KG
    Swap --> DVH

    classDef internal fill:#e51400,color:#fff,stroke:#a00;
    classDef stacc fill:#60a917,color:#fff,stroke:#2d7600;
    classDef tieto fill:#b1ddf0,stroke:#10739e;
    class Radgiverportal,Digital,API,Workers,Camunda,Decision,CRM,Doc,Account,Customer,Credit,LoanInfo,RE,Soknad,DVH,PowerBI,AIchat internal;
    class BM,Logg stacc;
    class KG,LP,Kjerne tieto;
```

Generert av claude, fra Joakim sin skisse
