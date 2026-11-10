# Operações de banco

Documentar responsabilidade de esquema, migrations, backup/restauração, compatibilidade, implantação gradual/reversão (rollback), retenção, acesso e procedimento de incidente.

Migrações futuras são revisadas e aplicadas por pipeline/procedimento controlado. Scripts operacionais nunca devem embutir credenciais nem apontar implicitamente para ambiente compartilhado.
