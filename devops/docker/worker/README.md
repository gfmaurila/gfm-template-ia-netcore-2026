# Container do Worker

Futuro container deve suportar cancelamento gracioso, prontidão (readiness) ligada à capacidade de processar, encerramento com drain quando aplicável e identidade de broker de menor privilégio.

Não duplicar consumidor em API e Worker inadvertidamente. Logs não podem conter carga útil (payload) sensível.
