# Política de banco descartável para integração

## Ciclo obrigatório

1. Criar banco/container temporário isolado, com nome/ID único por execução.
2. Confirmar que o endpoint e banco identificam explicitamente ambiente de teste descartável.
3. Criar estruturas aplicando migrations/scripts de teste da versão sob validação.
4. Popular somente dados sintéticos e mínimos.
5. Executar todos os testes de integração aplicáveis e coletar resultados.
6. Descartar banco, container, volume temporário, rede e dados de teste (fixtures), mesmo quando testes falham.
7. Verificar que nenhum recurso temporário permaneceu.

Preferir Testcontainers para dependências provisionadas pelo próprio teste. Escopo de uso e versões devem ser fixados no futuro projeto e compatíveis com CI.

## Proteções obrigatórias

- Exigir ambiente identificado como `Test` e marcador explícito de recurso descartável.
- Rejeitar conexões com hosts, contas, nomes ou perfis configurados como dev compartilhado, homologação ou produção.
- Usar allowlist local/container, credencial efêmera e database name com sufixo único.
- Não aceitar connection string herdada do ambiente sem validação.
- Proibir operação destrutiva se não puder provar que o recurso é descartável.
- Não imprimir connection strings, senhas, tokens ou payloads em log.
- Não reutilizar esquema/banco de desenvolvedor pessoal como fallback.

## Falhas e cancelamento abrupto

Implementação futura deve usar encerramento e limpeza/finally/disposal e limites de tempo. Adicionar labels e identificação de execução para localizar órfãos; rotina de limpeza deve atuar somente em recursos com label de teste e idade/TTL definidos. Se a limpeza falhar, reportar explicitamente. Nunca remover por nome genérico, wildcard ou em volume compartilhado.

## Limite da política

Esta política descreve requisitos; não cria comandos, containers, banco ou código de teste nesta fase.
