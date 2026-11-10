# Compartilhamento Front-end

Esta área documenta candidatos a compartilhamento, não pressupõe um pacote comum. Avaliar responsabilidade, compatibilidade, ciclo de publicação e dependências antes de compartilhar.

Possíveis conteúdos:

- Design Tokens e primitivas neutras de tema.
- Tipos/contratos de API versionados e gerados/validados a partir de fonte aprovada.
- Esquemas runtime quando a biblioteca e o esquema forem compatíveis com cada plataforma.
- Utilitários sem dependência de DOM, React Native, APIs do navegador ou estado global.
- Componentes visuais somente quando o runtime e a experiência forem realmente compatíveis.

React DOM e React Native não são intercambiáveis; não compartilhar componentes assumindo compatibilidade. Evitar importações circulares entre Admin, Site, Landing Page, Mobile e back-end. Não compartilhar lógica de autorização como substituta de enforcement no servidor, nem incluir segredos. Testar consumidores e compatibilidade de versão.
