<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2024/04/logo_github.png" width="240" />
<p align="center">Seja bem-vindo ao Guia de Update API Quepasa 🚀</p>
</p>
  
<p align="center"> 
<a href="https://hubconnect.top" target="_blank">👉 Participe da Comunidade HubConnect 👈</a>
</p>

<hr />
<hr />



**ATUALIZAÇÃO WORKFLOWS e APIQUEPASA**

Faça Backup dos Worflows que não do quepasa para restaurar depois
 
Acesse Terminal SSH

```bash
rm -fR /root/.n8n
```

```bash
pm2 stop n8n
```

#### Para seu Chatwoot funcionar corretamente com API Quepasa, instale a versão abaixo compativél

Migração de banco de dados sqlite para Postgres

### Criando Banco de dados Usuario e Senha

```bash
sudo -i -u postgres psql
```

```bash
CREATE ROLE n8n_user WITH LOGIN PASSWORD 'SenhaAqui';
```

```bash
CREATE DATABASE n8n_db;
```

```bash
GRANT ALL PRIVILEGES ON DATABASE n8n_db TO n8n_user;
```

```bash
GRANT CONNECT ON DATABASE n8n_db TO n8n_user;
```

```bash
\q
```

### Instale a última versão do n8n


```bash
sudo npm install -g n8n
```

```bash
npm install pm2 -g
```

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

```bash
sudo apt install ./google-chrome-stable_current_amd64.deb
```

```bash
pm2 start n8n --cron-restart="0 0 * * *" -- start
```

### Execute esse comando abaixo para não cair seu n8n quando você reiniciar sua VPS

```bash
sudo pm2 startup ubuntu -u root && sudo pm2 startup ubuntu -u root --hp /root && sudo pm2 save
```

```bash
nano /root/.n8n/.env
```

Altere as seguintes variaveis baixo no arquivo `.env`

DB_POSTGRESDB_PASSWORD=SenhaAqui

C8Q_QP_DEFAULT_USER=coloque email do Quepasa

C8Q_QP_BOTTITLE=Nome do seu site

C8Q_CW_PUBLIC_URL=domniochatwoot

C8Q_QP_CONTACT=Seu email

C8Q_QP_DEFAULT_USER=Seu email

WEBHOOK_URL=https://conector.dominio.com.br

N8N_EDITOR_BASE_URL=https://conector.dominio.com.br

```
DB_TYPE=postgresdb
DB_POSTGRESDB_HOST=localhost
DB_POSTGRESDB_PORT=5432
DB_POSTGRESDB_USER=n8n_user
DB_POSTGRESDB_PASSWORD=SenhaAqui
DB_POSTGRESDB_DATABASE=n8n_db
C8Q_SINGLETHREAD=false
C8Q_QUEPASAINBOXCONTROL=1001
C8Q_GETCHATWOOTCONTACTS=1002
C8Q_QUEPASACHATCONTROL=1003
C8Q_CHATWOOTPROFILEUPDATE=1004
C8Q_POSTTOWEBCALLBACK=1005
C8Q_POSTTOCHATWOOT=1006
C8Q_CHATWOOTTOQUEPASAGREETINGS=1007
C8Q_CW_PUBLIC_URL="chatwoot.seudominio.com.br"
C8Q_QP_DEFAULT_USER="contato@seudominio.com.br"
C8Q_QP_BOTTITLE="Chatwoot"
C8Q_QP_CONTACT="contato@seudominio.com.br"
N8N_EDITOR_BASE_URL="https://conector.dominio.com.br"
WEBHOOK_URL="https://conector.dominio.com.br"
EXECUTIONS_DATA_PRUNE=true
EXECUTIONS_DATA_MAX_AGE=168
EXECUTIONS_DATA_PRUNE_MAX_COUNT=5000
GENERIC_TIMEZONE="America/Sao_Paulo"
```

### Cria um link simbólico chamado ".env" que aponta para o arquivo "./.n8n/.env" no sistema de arquivos.

```bash
ln -s ./.n8n/.env .env
pm2 restart all --update-env
```

OBS: Não crie sua conta agora, antes de instalar API Quepasa!


**Atualizando API Quepasa e Colocando novos Worflows**


su - quepasa

git pull

exit

bash /opt/quepasa-source/helpers/update-workflows.sh


### update Finalizado ✅

Configue os Worflows no N8N

Adicione os community nodes ao seu N8N

```bash
n8n-nodes-chatwoot
```

```bash
n8n-nodes-quepasa
```

Acesse opção Credenciais, adicione suas credenciais Postgres, salve.

