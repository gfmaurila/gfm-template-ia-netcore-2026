# Blueprint: Full Stack API + Landing Page

## 1. Objetivo
Combinar API com presença pública/marketing Next.js, permitindo ciclo e publicação da Landing Page independentes.

## 2. Quando utilizar
Quando API suporta produto e existe necessidade explícita de divulgação/conversão. Não acoplar Landing Page ao ciclo de implantação da API sem motivo.

## 3. Stack recomendada
API conforme blueprint Back-end; Landing Page Next.js + TypeScript. Integrações server-side apenas quando necessárias.

## 4. Estrutura futura
Projetos/hosts Back-end e `src/front-end/web/landing-page/` como módulos isoláveis; contrato público restrito para formulários ou conteúdo quando necessário.

## 5. Dependências
Domínio/hosting/CDN e endpoint público de formulário opcionais; CMS e analytics requerem avaliação de privacidade/responsável.

## 6. Arquitetura
Renderização e conteúdo separados da lógica de API; formulário envia dados mínimos a endpoint validado; publicação desacoplada.

## 7. Segurança
Proteger formulário contra spam/abuso; validação e rate limit no servidor; não expor keys, não registrar PII; CSP/headers/consentimento conforme cenário.

## 8. Testes
Componentes/SEO/formulários; E2E de CTA/submissão; API contract/integration para formulário; acessibilidade e performance. Banco descartável somente se persistir dados.

## 9. Docker
Container de Landing Page/API opcional; compose somente para ambiente local reproduzível, com dependências efêmeras identificadas.

## 10. GitHub Actions
Pipelines e publicação separados; E2E integração por contrato; varreduras e aprovação de publicação; sem produção automática.

## 11. Diagramas Draw.io
C4 Context/Container, CTA→form→API e desenho de implantação/CDN/confiança.

## 12. Bootstrap
Definir copy/content responsabilidade, SEO, contrato do formulário, privacidade, hosting separado e tarefas Front-end autorizadas.

## 13. Critérios de aceite
Landing Page publicável independentemente; SEO/acessibilidade/Performance atendidos; formulário protegido; contrato testado; implantação aprovado.
