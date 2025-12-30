## Backup PostgreSQL – ERP

### Visão Geral
- Banco: ERP
- Tipo: Backup lógico (pg_dump)
- Formato: .bk
- Nomeação: erp_loja_DDMMAAAA.bk
- Tamanho médio: ~12–13 GB

### Local do Backup
- Origem local: /erp/backup
- Destino remoto: /home/erpDB (Backup Server)

### Transferência
- Método: rsync via SSH
- Servidor de backup: 192.168.100.193
- Usuário: root
- Comunicação interna (LAN)

### Automação
- A execução não ocorre via crontab local
- A sincronização é iniciada pelo servidor de backup (pull)
- Horário observado: diariamente às 22:00

### Observações
- Script syncbkp.sh foi utilizado historicamente para testes e sincronização
- Atualmente não há cron ou timer ativo neste servidor
- Backup continua sendo copiado automaticamente pelo servidor de backup
