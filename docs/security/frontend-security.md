# Linha de base de segurança Front-end

Aplicar junto com `governance/security/security-baseline.md` e com o modelo de ameaças do projeto. Escolher controles segundo o fluxo de dados e a stack; não usar este documento como substituto de revisão de segurança.

## Navegador e autenticação

- Prevenir XSS por escaping/contextual output e evitando HTML não confiável; se HTML rico for requisito, definir sanitização revisada. Não usar `dangerouslySetInnerHTML` com dados não confiáveis.
- Avaliar CSRF conforme cookies, credenciais e arquitetura de sessão; usar cookies `Secure`, `HttpOnly`, `SameSite` e mitigação CSRF apropriada quando aplicável.
- Não armazenar bearer/refresh tokens em `localStorage`, `sessionStorage` ou logs como padrão. Preferir fluxo aprovado com cookies seguros/BFF ou mecanismo de plataforma; registrar tradeoffs.
- Autorização deve ser aplicada pela API. Guards, rotas privadas e ocultação de controles são somente UX, nunca enforcement.
- Nunca embutir segredo privado em bundle, variável `NEXT_PUBLIC_*`, `VITE_*`, source map ou arquivo estático.

## Entrada, APIs e privacidade

- Validar entradas no cliente para UX e sempre revalidar no servidor. Tratar respostas externas como dados não confiáveis.
- Aplicar autorização, limites, validação e proteção contra abuso na API; formularios públicos requerem rate limiting/anti-abuso proporcional e consentimento quando aplicável.
- Minimizar dados pessoais em estado, cache, analytics e telemetria; redactar logs e definir retenção.
- CORS, CSP e demais headers são definidos no host/edge conforme implantação; limitar origens/fontes, evitar políticas `unsafe-*` sem avaliação.
- Analytics só com autorização, transparência, consentimento e configuração de privacidade pertinentes.

## Dependências, ambientes e Mobile

- Revisar dependências, lockfiles, advisories, licença e cadeia de compilação antes de adotá-las.
- Validar configuração por ambiente; valores públicos não são segredos, mas devem ser revisados. Não incluir tokens, certificados, keystores ou arquivos de assinatura.
- Mobile: armazenar tokens no armazenamento seguro da plataforma; pedir permissões mínimas e no contexto; tratar deep links, backups, logs, screenshots e dados offline no modelo de ameaças.
- Nunca confiar na validação no cliente para proteger recursos; autenticar e autorizar no servidor e nas APIs correspondentes.

Achados devem ser tratados conforme o fluxo de revisão de segurança, com evidências sanitizadas e sem inserir segredos reais nos documentos.
