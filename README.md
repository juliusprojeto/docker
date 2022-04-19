# docker
Ambiente docker


<p><span style="font-weight: 400;">DOCKER E DOCKER-COMPOSE -- ESTUDOS</span></p>
<hr />
<p>&nbsp;</p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">Verificando o docker instalado</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker --version</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker info</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Executando um docker com Ubuntu</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker run --rm -ti ubuntu:latest /bin/bash</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Criando um Dockerfile</span></p>
</td>
<td>
<p><span style="font-weight: 400;">FROM ubuntu:latest</span></p>
<p><span style="font-weight: 400;">LABEL "mantainer"="Lucio"</span></p>
<br />
<p><span style="font-weight: 400;">ENV UBU /home/lucio/docker/ubuntu</span></p>
<br />
<p><span style="font-weight: 400;">RUN apt-get -y update</span></p>
<br />
<p><span style="font-weight: 400;">WORKDIR $UBU</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">FROM</span></p>
</td>
<td>
<p><span style="font-weight: 400;">indica qual das imagens ser&aacute; usada pelo dockerfile</span></p>
<p><span style="font-weight: 400;">ex: FROM ubuntu:20.04</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Label</span></p>
</td>
<td>
<p><span style="font-weight: 400;">Label s&atilde;o os metados adicionados via chave-valor</span></p>
<p><span style="font-weight: 400;">exe: LABEL &ldquo;maintanainer&rdquo;=&rdquo;lucio@gmail.com&rdquo;</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">ADD</span></p>
</td>
<td>
<p><span style="font-weight: 400;">A instru&ccedil;&atilde;o ADD &eacute; usada pra copiar arquivos de file system local ou url remotas</span></p>
<p><span style="font-weight: 400;">Ex: ADD *.js* $AP/</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">ENV</span></p>
</td>
<td>
<p><span style="font-weight: 400;">A instru&ccedil;&atilde;o ENV determina um caminho como variavel de ambiente ex: ENV AP /data/app</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">WORKDIR</span></p>
</td>
<td>
<p><span style="font-weight: 400;">O WORKDIR&nbsp; usamos para mudar do diretorio corrente para um outro diretorio</span></p>
<p><span style="font-weight: 400;">ex: WORKDIR $AP</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">RUN</span></p>
</td>
<td>
<p><span style="font-weight: 400;">A instru&ccedil;&atilde;o RUN deve ser utilizada para pr&eacute; instalar aplica&ccedil;&otilde;es ou criar pastas na imagem.</span></p>
<p><span style="font-weight: 400;">Ex: RUN apt-get -y update</span></p>
<p><span style="font-weight: 400;">ex: RUN mkdir -p /var/log/supervisor</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">CMD</span></p>
</td>
<td>
<p><span style="font-weight: 400;">Similar ao run, com a instru&ccedil;&atilde;o CMD iremos executar comandos internos do sistema operacional</span></p>
<p><span style="font-weight: 400;">Ex: CMD [&ldquo;ls -ltr&rdquo;]</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Buildando um docker</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker build -t unix:1.0 .</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Executando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker run --rm -ti unix:1.0 /bin/bash</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker run --rm -it ubuntu:20.04 bash</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">Nesse modo com &ldquo;it&rdquo; os dados n&atilde;o s&atilde;o persistentes</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">Nomeando um container</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker container run --rm ---name ubuntu -it ubuntu\;20.04</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Re-utilizando o container</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker container start -ai ubuntu</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Removendo todos os containers ativos</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker rm -f $(docker ps -aq)</span><span style="font-weight: 400;">&nbsp;</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
</tbody>
</table>
<p><br /><br /><br /><br /><br /><br /><br /></p>
<p><strong>DOCKER COMPOSE</strong></p>
<p><br /><br /></p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">mysql docker compose</span></p>
</td>
<td>
<p><span style="font-weight: 400;">version</span><span style="font-weight: 400;">: </span><span style="font-weight: 400;">'3.3'</span></p>
<p>&nbsp;</p>
<p><span style="font-weight: 400;">services</span><span style="font-weight: 400;">:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;</span><span style="font-weight: 400;">db</span><span style="font-weight: 400;">:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;</span><span style="font-weight: 400;">image</span><span style="font-weight: 400;">: </span><span style="font-weight: 400;">mysql</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;</span><span style="font-weight: 400;">restart</span><span style="font-weight: 400;">: </span><span style="font-weight: 400;">always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;</span><span style="font-weight: 400;">environment</span><span style="font-weight: 400;">:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span style="font-weight: 400;">MYSQL_DATABASE</span><span style="font-weight: 400;">: </span><span style="font-weight: 400;">"store"</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span style="font-weight: 400;">MYSQL_ROOT_PASSWORD</span><span style="font-weight: 400;">: </span><span style="font-weight: 400;">"senha"</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;</span><span style="font-weight: 400;">ports</span><span style="font-weight: 400;">:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- </span><span style="font-weight: 400;">'3306:3306'</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;</span><span style="font-weight: 400;">volumes</span><span style="font-weight: 400;">:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- </span><span style="font-weight: 400;">dbvolume:/var/lib/mysql</span></p>
<p><span style="font-weight: 400;">volumes</span><span style="font-weight: 400;">:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;</span><span style="font-weight: 400;">dbvolume</span><span style="font-weight: 400;">:</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Inicializando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">arquivo &rArr; docke-compose.yaml</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker-compose up &rArr; nesse caso n&atilde;o fica em background</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker-compose up -d</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Acessando o Mysql</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker exec -it mysql_db_1 bash</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">mysql -u root -p</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Parando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker-compose down</span></p>
</td>
</tr>
</tbody>
</table>
<p><br /><br /><br /><br /><br /></p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">PHPADMIN</span></p>
</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">docker-compose.yaml</span></p>
</td>
<td>
<p><span style="font-weight: 400;">version: '3.1'</span></p>
<br /><br />
<p><span style="font-weight: 400;">services:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;phpmyadmin:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;image: phpmyadmin</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;restart: always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ports:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 8080:80</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;environment:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- PMA_ARBITRARY=1</span></p>
<br /><br /></td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Inicializando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker-compose up -d</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Parando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker-compose down</span></p>
</td>
</tr>
</tbody>
</table>
<p><br /><br /><br /><br /><br /><br /></p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">MONGODB</span></p>
</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">docker-compose.yaml</span></p>
</td>
<td>
<p><span style="font-weight: 400;">version: '3.1'</span></p>
<br />
<p><span style="font-weight: 400;">services:</span></p>
<br />
<p><span style="font-weight: 400;">&nbsp;&nbsp;mongo:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;image: mongo</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;restart: always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;environment:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MONGO_INITDB_ROOT_USERNAME: root</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MONGO_INITDB_ROOT_PASSWORD: senha</span></p>
<br />
<p><span style="font-weight: 400;">&nbsp;&nbsp;mongo-express:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;image: mongo-express</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;restart: always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;ports:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 8081:8081</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;environment:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ME_CONFIG_MONGODB_ADMINUSERNAME: root</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ME_CONFIG_MONGODB_ADMINPASSWORD: senha</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ME_CONFIG_MONGODB_URL: mongodb://root:example@mongo:27017/</span></p>
<br /><br /></td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Acessando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker exec -it mongo_mongo_1 bash</span></p>
</td>
</tr>
</tbody>
</table>
<p><br /><br /><br /><br /><br /><br /><br /></p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">DOCKERFILE MYSQL</span></p>
</td>
<td>
<p><span style="font-weight: 400;">FROM mysql:8.0-oracle</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">arquivo Dockerfile</span></p>
</td>
<td>
<p><span style="font-weight: 400;">EXPOSE 3306:3306</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Buildando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker build -t lucio80 .</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker build -t lucio80:v1 .</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
</tbody>
</table>
<p><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /></p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">SWARM (inicializando)</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker swarm init --advertise-addr </span><span style="font-weight: 400;">52.5.84.14</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">listando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker node ls</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">subindo servi&ccedil;o no swarm com composer</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker swarm init --advertise-addr </span><span style="font-weight: 400;">100.24.20.43</span><span style="font-weight: 400;">1</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker stack deploy -c docker-compose.yaml mysql_swar</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">adicionando nodes</span></p>
</td>
<td>
<p><span style="font-weight: 400;">adiciona o token gerado no passo anterior</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">adicionando o servi&ccedil;o</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker service ls (para pegar o nome do servi&ccedil;o)</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker service scale mysql_swar_db=2</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">checando</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker service ls</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker node ls</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">recuperando o token</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker swarm join-token manager</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">removendo o node</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker rm &lt;ID&gt;</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">para achar o ID</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker node ls</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Conectando no docker</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker exec -it &lt;name&gt; bash</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">docker exec -it $(docker ps -f name=&lt;name&gt;&nbsp; -q) mysql -u root -p</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">Identificando o &lt;name&gt;</span></p>
</td>
<td>
<p><span style="font-weight: 400;">docker service ls</span></p>
</td>
</tr>
</tbody>
</table>
<p><br /><br /><br /><br /><br /></p>
<p><strong>UNINSTALL DOCKER</strong></p>
<p><br /><br /></p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">dpkg -l | grep -i docker</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo apt-get purge -y docker-engine docker docker.io docker-ce docker-ce-cli</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo apt-get autoremove -y --purge docker-engine docker docker.io docker-ce</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo rm -rf /var/lib/docker /etc/docker</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo rm /etc/apparmor.d/docker</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo groupdel docker</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo rm -rf /var/run/docker.sock</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo rm -rf /var/lib/docker</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">sudo rm -rf /var/lib/containerd</span></p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">ls -ltr sources.list.d</span></p>
</td>
<td>
<p><span style="font-weight: 400;">sudo rm -r /etc/apt/sources.list.d/docker.list</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">rm -r /etc/apt/sources.list.d/mongodb-enterprise.list</span></p>
</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<p><span style="font-weight: 400;">rm -r /etc/apt/sources.list.d/download_docker_com_linux_ubuntu.list</span></p>
</td>
</tr>
</tbody>
</table>
<p><br /><br /><strong>WORDPRESS</strong></p>
<p><br /><br /></p>
<table>
<tbody>
<tr>
<td>
<p><span style="font-weight: 400;">version: '3.3'</span></p>
<br />
<p><span style="font-weight: 400;">services:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;mysql_db:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;container_name: mysql_container</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;image: mysql:8.0</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;restart: always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;environment:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_ROOT_PASSWORD: senha</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_DATABASE: wordpress_database</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_USER: wordpress_user</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_PASSWORD: Olaf4ever</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;volumes:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- mysql_vol:/var/lib/mysql</span></p>
<br /><br /><br />
<p><span style="font-weight: 400;">&nbsp;&nbsp;wordpress:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;depends_on:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- mysql_db</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;image: wordpress:latest</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;restart: always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;ports:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- "8080:80"</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;environment:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_HOST: mysql_db:3306</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_USER: wordpress_user</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_PASSWORD: senha</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_NAME: wordpress_database</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;volumes:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;["./:/var/www/html"]</span></p>
<br /><br /><br />
<p><span style="font-weight: 400;">volumes:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;mysql_vol: {}</span></p>
<br /><br /></td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">docker-compose up -d</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">docker-compose.yml</span></p>
</td>
</tr>
<tr>
<td>
<p><span style="font-weight: 400;">version: "3.5"</span></p>
<br />
<p><span style="font-weight: 400;">services:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;db:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;image: mysql:8.0</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;volumes:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- db_data:/var/lib/mysql</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;restart: always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;environment:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_ROOT_PASSWORD: senha</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_DATABASE: wordpress</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_USER: wordpress</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MYSQL_PASSWORD: senha</span></p>
<br />
<p><span style="font-weight: 400;">&nbsp;&nbsp;wordpress:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;depends_on:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- db</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;image: wordpress:latest</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;volumes:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- wordpress_data:/var/www/html</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;ports:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- "8000:80"</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;restart: always</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;environment:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_HOST: db</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_USER: wordpress</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_PASSWORD: senha</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;WORDPRESS_DB_NAME: wordpress</span></p>
<p><span style="font-weight: 400;">volumes:</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;db_data: {}</span></p>
<p><span style="font-weight: 400;">&nbsp;&nbsp;wordpress_data: {}</span></p>
<br /><br /></td>
</tr>
</tbody>
</table>
<p><br /><br /></p>


<table style="border-collapse: collapse; width: 100%;" border="1">
<tbody>
<tr>
<td style="width: 100%;">DOCKER WORDPRESS</td>
</tr>
<tr>
<td style="width: 100%;">
<p>version: '3.3'</p>
<p>services:<br />mysql_db:<br />container_name: mysql_container<br />image: mysql:8.0<br />restart: always<br />environment:<br />MYSQL_ROOT_PASSWORD: senha<br />MYSQL_DATABASE: wordpress_database<br />MYSQL_USER: wordpress_user<br />MYSQL_PASSWORD: Olaf4ever<br />volumes:<br />- mysql_vol:/var/lib/mysql</p>
<p>wordpress:<br />depends_on:<br />- mysql_db<br />ports:<br />- 80:80<br />image: wordpress:latest<br />restart: always<br />environment:<br />WORDPRESS_DB_HOST: mysql_db:3306<br />WORDPRESS_DB_USER: wordpress_user<br />WORDPRESS_DB_PASSWORD: senha<br />WORDPRESS_DB_NAME: wordpress_database<br />volumes:<br />["./:/var/www/html"]</p>
<p>nginx:<br />depends_on:<br />- wordpress<br />image: nginx<br />volumes:<br />- nginx:/etc/nginx/conf.d<br />- data:/var/www/html</p>
<p>volumes:<br />mysql_vol: {}<br />nginx: {}<br />data: {}</p>
</td>
</tr>
</tbody>
</table>
