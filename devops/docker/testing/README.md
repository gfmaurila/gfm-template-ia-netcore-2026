# Containers de teste

Preferir Testcontainers para dependências provisionadas por testes. Usar imagens versionadas, portas aleatórias, redes/volumes únicos e labels por execução. Não reutilizar dados nem volumes compartilhados.

Garantir encerramento e limpeza em sucesso, falha e cancelamento; validar órfãos por labels e TTL sem remover containers alheios.
