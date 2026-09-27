**Find compute you can actually use.**

Egrit helps you find GPU cloud, NeoCloud and managed inference capacity that
fits what you need, and shows the evidence behind every answer.

```mermaid
%%{init: {"theme": "base", "themeVariables": {"fontSize": "20px", "fontFamily": "Inter, Helvetica, Arial, sans-serif", "lineColor": "#096FFE"}}}%%
flowchart LR
    R["<b>Your requirement</b><br/>64 H200s, EU, 30 days"]:::ask --> E(["<b>Egrit</b><br/>checks every provider,<br/>service and region"]):::egrit
    E --> Y["<b>yes, it fits</b><br/>with its source and date"]:::yes
    E --> N["<b>no, it does not</b><br/>with its source and date"]:::no
    E --> U["<b>unknown</b><br/>nothing on record yet"]:::unknown

    classDef ask fill:#FFFFFF,stroke:#061835,stroke-width:2px,color:#061835,font-size:20px
    classDef egrit fill:#061835,stroke:#096FFE,stroke-width:4px,color:#FFFFFF,font-size:22px
    classDef yes fill:#096FFE,stroke:#061835,stroke-width:2px,color:#FFFFFF,font-size:20px
    classDef no fill:#CFE2FF,stroke:#061835,stroke-width:2px,color:#061835,font-size:20px
    classDef unknown fill:#FFFFFF,stroke:#096FFE,stroke-width:2px,stroke-dasharray:6 4,color:#061835,font-size:20px
    linkStyle default stroke:#096FFE,stroke-width:3px
```

For each provider and region, Egrit compiles what is on public record, from
the provider's own documentation and from independent sources, and keeps it
current. Every statement carries its source, the date it was read and a grade
that says how far it goes:

- what the provider declares;
- what independent sources establish;
- what nobody can prove yet.

Egrit keeps those apart, and it filters rather than ranks. No provider pays
for a grade.

Egrit never holds your workloads, prompts, data, models, results or
credentials.

## Working in a regulated organisation

In a bank, an insurer, a health service or another regulated organisation,
finding capacity is only half the job: your risk and procurement teams have
to accept a provider before you can use it. Egrit shows where each service
runs and what is on record about it, with the source and date of every
statement, so you can see early which options are worth taking to them, and
give them the reasons.

Egrit does not decide whether a provider suits your organisation. Your own
teams do.

## Status

Early development. Search is not open yet. To hear when it is, get early
access at [www.egrit.ai](https://www.egrit.ai).

Public repositories will appear here when they are ready.

## About

Egrit is a product of Neul Space Ltd, registered in England and Wales.
