# Diagramas

Use Draw.io como fonte editável principal e Mermaid como complemento textual quando facilitar revisão por diff.

- `drawio/`: fontes editáveis `.drawio`; ver o [inventário de fontes](drawio/README.md).
- `mermaid/`: diagramas em texto `.mmd` futuros.

## Diagramas do GFM.Template

Os PNGs são exportações das fontes Draw.io correspondentes e servem para visualização no GitHub. Alterações devem ser feitas na fonte editável e exportadas novamente; não editar o PNG como fonte.

| Nome | PNG | Fonte editável |
|---|---|---|
| Visão geral | [PNG](gfm-template-overview.png) | [Draw.io](drawio/gfm-template-overview.drawio) |
| Full Stack | [PNG](gfm-template-fullstack.png) | [Draw.io](drawio/gfm-template-fullstack.drawio) |
| Back-end | [PNG](gfm-template-backend.png) | [Draw.io](drawio/gfm-template-backend.drawio) |
| Front-end | [PNG](gfm-template-frontend.png) | [Draw.io](drawio/gfm-template-frontend.drawio) |
| Agentes de IA | [PNG](gfm-template-ai-agents.png) | [Draw.io](drawio/gfm-template-ai-agents.drawio) |
| Bootstrap | [PNG](gfm-template-bootstrap.png) | [Draw.io](drawio/gfm-template-bootstrap.drawio) |
| Quality Gates | [PNG](gfm-template-quality-gates.png) | [Draw.io](drawio/gfm-template-quality-gates.drawio) |
| Versionamento e CI/CD | [PNG](gfm-template-gitflow.png) | [Draw.io](drawio/gfm-template-gitflow.drawio) |

Todo diagrama deve ter título, propósito, escopo, legenda, data/versão quando aplicável e ligação à especificação ou ADR. Não incluir topologia, nomes ou dados de clientes.
