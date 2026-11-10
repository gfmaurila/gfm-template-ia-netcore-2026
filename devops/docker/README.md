# Docker

Padrões futuros para containers. Não há Dockerfile nesta fase.

Imagens futuras devem ser mínimas, reproduzíveis, executadas sem privilégios de root, com sinais e encerramento corretos, verificações de integridade, versão imutável e segredos fora da imagem. API/Worker/Batch só recebem imagens separadas se a implantação independente tiver valor.
