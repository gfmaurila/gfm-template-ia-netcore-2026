# Docker Compose local

Compose futuro poderá orquestrar dependências locais fictícias para desenvolvimento/testes. Não criar arquivo YAML nesta fase.

Separar perfil de teste descartável de ambiente de desenvolvimento; volumes nomeados somente quando intencionais. `down`/remoção de volume deve ser direcionado a projeto de teste identificado, nunca a recursos compartilhados.

Comandos planejados a documentar quando houver Compose autorizado: iniciar ambiente, executar testes, gerar relatórios, encerrar e remover somente recursos temporários identificados.
