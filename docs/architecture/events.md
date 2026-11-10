# Eventos e mensageria

## Tipos e localizações

| Conceito | Significado | Localização futura |
|---|---|---|
| Domain Event | Algo relevante aconteceu dentro de um domínio/aggregate. Não representa por si só um contrato externo. | Tipo específico em Domain; tratamento/orquestração em Application. |
| Integration Event | Contrato publicado para outros processos/sistemas. Deve ser versionado e compatível. | Contratos genéricos/envelope em Core; contrato específico no módulo de integração ou pacote compartilhado deliberado. |
| Event Manipulador | Reage a evento e coordena um caso de uso ou efeito. | Application. |
| Produtor/Consumidor | Adaptadores de transporte e serialização. | Infrastructure. |
| Hosted processing | Ciclo de vida do processo e composição do consumo. | Worker. |

Não usar o mesmo tipo como evento de domínio e contrato Kafka/HTTP. Domain não conhece broker, envelope, headers, SDKs ou política de nova tentativa (retry).

## Outbox e Inbox

Quando gravar estado e publicar evento precisam ser consistentes, persistir a mensagem de outbox na mesma transação do estado. Um dispatcher em Infrastructure publica e marca a mensagem com nova tentativa (retry) e métricas. Inbox ou chave idempotente persistida deduplica recebimentos. Cache em memória não substitui deduplicação durável.

O desenho concreto depende do banco, broker, volume e garantias exigidas. Registrar ADR e estratégia de retenção antes da implementação.

## Nova tentativa (retry) e DLQ

Definir erros transitórios/permanentes, limites com espera exponencial (backoff) e jitter, tempo limite (timeout), ordenação, política de poison message, DLQ e replay controlado. Não confirmar offset como sucesso se o processamento falhou. Não ocultar falha de publicação ou consumo.

## Responsabilidade

Infrastructure implementa transporte, outbox/inbox e conectores; Application executa manipuladores/casos de uso; Worker hospeda e instrumenta o processamento. Evitar duplicar consumidores/producers no Worker e em Infrastructure.
