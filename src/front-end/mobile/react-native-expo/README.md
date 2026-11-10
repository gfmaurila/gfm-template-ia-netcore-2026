# Mobile React Native + Expo

## Stack e organização

Stack preferencial: React Native + TypeScript + Expo. Expo Router é a escolha inicial para navegação baseada em rotas, após confirmar compatibilidade da versão selecionada. Estrutura futura a adaptar:

```text
app/                   # rotas/layouts do Expo Router
src/
  features/<feature>/  # screens, components, hooks, services, schemas, types
  services/            # API clients e integrações
  theme/               # tokens e tema
  assets/              # assets locais revisados
```

## Dispositivo e segurança

Screens e navegação ficam na apresentação; regras autoritativas permanecem no back-end. API Clients tratam tempo limite (timeout), conectividade, erros e validação de respostas. Armazenar tokens somente em mecanismo seguro adequado à plataforma; nunca em AsyncStorage/plaintext, logs, screenshots ou analytics. Pedir permissões de dispositivo no momento e contexto necessários, com alternativa quando negadas. Minimizar dados offline e definir criptografia/expiração/remoção.

## Experiência e releases

Garantir acessibilidade (labels, foco, contraste, leitor de tela, tamanho de toque) e tratar estados offline, loading, erro e nova tentativa (retry). Planejar compilações Android/iOS, signing, canais e distribuição segundo processo aprovado; não guardar certificados/keystores/segredos no repositório. Docker pode apoiar serviços e testes auxiliares, mas não substitui SDKs, simuladores, emuladores nem compilações nativos.

## Testes e aceite

Usar Jest e React Native Testing Library quando compatíveis; cobrir navegação, telas, permissões e integração API. Definir E2E Mobile e execução em dispositivo/emulador como parte do plano. Aceite inclui armazenamento seguro, permissões justificadas, acessibilidade, testes e compilações/distribuição documentados.

Usar `blueprints/mobile-react-native/README.md`. O cenário é independente e opcional; não criar app nesta fase.
