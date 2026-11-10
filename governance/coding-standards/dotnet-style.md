# Convenções C#/.NET

- Usar nomes em inglês para código e APIs internas, salvo decisão de domínio documentada; documentação do projeto pode ser em português.
- Preferir tipos explícitos no domínio, imutabilidade de value objects e encapsulamento de invariantes.
- Evitar classes estáticas de mapeamento com responsabilidades múltiplas; escolher mapeamento explícito ou biblioteca após justificar.
- Usar `async`/`await` de ponta a ponta para I/O e propagar `CancellationToken`.
- Não usar `.Result`, `.Wait()` ou `GetAwaiter().GetResult()` em fluxo assíncrono de aplicação.
- Não capturar exceção sem tratamento, contexto ou rethrow; não converter falha em `null`, resposta de sucesso ou dado padrão sem contrato.
- Usar registro de logs estruturado; nunca registrar segredos, tokens, credenciais, payloads pessoais completos ou parâmetros sensíveis.
- Validar entradas na fronteira e preservar invariantes no domínio.
- Evitar abstrações genéricas sem mais de um caso real de uso.
- Habilitar nullable reference types de forma consistente em novos projetos e tratar warnings relevantes.
- Manter dependências e linguagem .NET compatíveis e centralizadas no futuro compilação.

Estilo/formatação deve ser automatizado quando houver código. Não afirmar conformidade sem executar o formatter e os analisadores configurados.
