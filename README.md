<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2023/08/logo-github-cwmkt.svg" alt="DispZap Whats Marketing" width="240" />
<p align="center">Seja bem-vindo ao Guia de Update API Quepasa 🚀</p>
</p>
  
<p align="center">
<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
<span>Grupo WhatsaAPP: </span>
<a href="https://link.cwmkt.com.br/grupo-whats" target="_blank">Grupo</a>
</p>

<hr />
<hr />



**ATUALIZAÇÃO WORKFLOWS e APIQUEPASA**

</p>
apague todos os Worflows em seu N8N
</p>
Acesse Terminal SSH
</p>
nano .env
</p>
Altere as seguintes variaveis baixo no arquivo .env
</p>
C8Q_QP_DEFAULT_USER=coloque email do Quepasa
</p>
C8Q_CW_PUBLIC_URL=dominiochatwoot
</p>
C8Q_QP_CONTACT=Seu email
</p>

```
C8Q_SINGLETHREAD=false
C8Q_QUEPASAINBOXCONTROL=1001
C8Q_GETCHATWOOTCONTACTS=1002
C8Q_QUEPASACHATCONTROL=1003
C8Q_CHATWOOTPROFILEUPDATE=1004
C8Q_POSTTOWEBCALLBACK=1005
C8Q_POSTTOCHATWOOT=1006
C8Q_CHATWOOTTOQUEPASAGREETINGS=1007
C8Q_CW_PUBLIC_URL="chatwoot.seudominio.com.br"
C8Q_QP_DEFAULT_USER="contatoo@seudominio.com.br"
C8Q_QP_BOTTITLE="Chatwoot"
C8Q_QP_CONTACT="contato@seudominio.com.br"
```

</p>
cp .env /root
</p>
</p>
pm2 restart all --update-env
</p>


<hr />
<hr />

**Atualizando API Quepasa e Colocando novos Worflows**

</p>
su - quepasa
</p>
git pull
</p>
exit
</p>
bash /opt/quepasa-source/helpers/update-workflows.sh
</p>

<hr />
<hr />

**QUEM NÃO CONSEGUI GERAR O QRCODE COM O NOVO UPDATE**

</p>
Só fazer o seguinte|:
</p>
sudo apt update && apt upgrade -y
</p>
sudo add-apt-repository ppa:redislabs/redis
</p>
sudo apt update
</p>
sudo apt install redis
</p>
sudo apt-get install libvips
</p>


