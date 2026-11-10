# Front-end

Selecione somente os módulos solicitados na SPEC e aprovados no plano. Admin, Site, Landing Page e Mobile são cenários oficiais independentes; não precisam coexistir no mesmo projeto.

| Módulo | Stack preferencial | Quando selecionar |
|---|---|---|
| [Admin](web/admin/README.md) | React + TypeScript + Vite | Interfaces administrativas autenticadas e orientadas a operações. |
| [Site](web/site/README.md) | React + TypeScript + Vite | Aplicação Web interativa; considerar Next.js se SSR/SEO ou outra capacidade específica for requisito. |
| [Landing Page](web/landing-page/README.md) | Next.js + TypeScript | Presença pública com SEO, renderização e publicação independentes. |
| [Mobile](mobile/react-native-expo/README.md) | React Native + TypeScript + Expo | Aplicativo móvel nativo multiplataforma. |
| [Shared](shared/README.md) | Dependente da compatibilidade | Contratos/tipos/utilitários comprovadamente compartilháveis, sem acoplamento circular. |

Verificar versões suportadas e compatibilidade entre framework, router, ferramentas de teste e SDKs antes de selecionar dependências. Autenticação, dados, APIs e decisões de implantação devem seguir requisitos aprovados e documentação de segurança/DevOps.

Nenhum módulo, pacote, arquivo de configuração ou código executável é criado nesta fase.
