# Padrão de diagramas Draw.io

## Fonte e armazenamento

Draw.io/diagramas.net é a ferramenta principal. Armazenar arquivos editáveis em `docs/architecture/diagrams/drawio/`; exportações são derivadas e não substituem a fonte editável. Mermaid pode complementar diagramas que se beneficiem de revisão textual.

## Tipos previstos

- C4 Context, Container e Component: níveis coerentes, sem misturar implementação e contexto.
- Sequência HTTP e fluxo assíncrono: indicar ordem, respostas, falhas e limites de confiança.
- Banco de dados: mostrar propriedade dos dados, persistência e limites transacionais.
- Segurança: identidades, zonas de confiança, autenticação/autorização e fluxos de segredo sem incluir valores.
- Docker e implantação: ambientes, artefatos e fronteiras de runtime.
- CI/CD: validações, artefatos, aprovações e ambientes protegidos.

## Convenções visuais

- Um diagrama por propósito; título, legenda, escopo e limites claros.
- Separar pessoas, sistemas externos, containers, processos, filas e bancos por forma/estilo consistente.
- Usar setas direcionais rotuladas com protocolo/propósito, sem excesso de detalhe.
- Marcar elementos opcionais, futuros ou não verificados de forma explícita.
- Preferir nomes lógicos e fictícios; nunca incluir URLs internas, IPs, credenciais ou dados de clientes.

## Critérios de revisão

Confirmar que o diagrama corresponde à especificação/ADR, que o status atual está indicado, que as setas têm origem/destino inequívocos e que nenhum segredo ou dado sensível foi incorporado.
