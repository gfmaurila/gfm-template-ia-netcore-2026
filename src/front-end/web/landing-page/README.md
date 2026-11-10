# Landing Page

## Stack e publicação

Stack preferencial: Next.js + TypeScript. O módulo deve poder ser construído e publicado independentemente dos módulos Admin, Site, Mobile ou API, com domínio, configuração e pipeline próprios quando necessário.

## Estrutura e conteúdo

Organização futura a adaptar: `app/` ou `pages/` conforme versão/router selecionado, layouts, componentes por seção e módulos de conteúdo. Incluir apenas se requisitos aprovados:

- Hero Section com proposta e chamada para ação.
- Apresentação do produto, benefícios e funcionalidades.
- Formulários públicos com validação, limites e proteção contra abuso.
- Metadados por rota, títulos/descrições, Open Graph e canonical URLs.
- Sitemap e robots conforme política de indexação.
- Acessibilidade semântica, navegação por teclado e foco.
- Responsividade e otimização de imagens usando recursos compatíveis com a implantação escolhida.

## Performance, privacidade e segurança

Definir metas e medir Core Web Vitals no contexto real. Preferir renderização e cache coerentes com atualização/privacidade do conteúdo. Analytics somente com autorização, transparência, minimização e política de retenção aplicável. Não inserir chaves privadas no cliente; proteger formulários contra abuso, validar no servidor, aplicar rate limit e evitar exposição de PII. Rever headers/CSP conforme recursos usados.

## Testes e aceite

Cobrir renderização/metadata, componentes e formulários; E2E para CTA/jornadas principais; acessibilidade e performance conforme metas. Aceite inclui publicação independente comprovada no plano, SEO/metadados corretos, formulário protegido, acessibilidade/responsividade e validações aprovadas.

Usar `blueprints/landing-page-nextjs/README.md`. Nenhum projeto ou conteúdo de cliente é criado nesta fase.
