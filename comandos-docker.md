### Repositório com objetivo de uso próprio, com os comando mais utilizados ao longo dos cursos.

## Comandos

`docker ps` 				--> Exibe todos os conteiners em execução.

(Os comandos similares para o `docker ps` são `docker container ls` ou `docker container ps` ou `docker container list`, acrescentando a FLAG -a em qualquer destes comandos, eles desempenham o mesmo papel que originalmente cabia ao `docker ps -a` )

`docker container [nome do container oi ID] logs` --> Exibe todos os logs desrte container.

`docker info` 				--> exibe informalções do docker host.

`docker version` 				--> exibe a versão do cliente docker utilizado.

`docker images` 				--> exibe as imagens baixadas pelo docker no host.

`docker search [parâmetro]`		--> usado para procurar imagens que podem ser usadas.

`docker pull [parâmetro]`			--> usado para fazer o download da imagem, puramente. 

`docker run [parâmetro]`			--> usado para executar a imagem, caso você não tenha a imagem, é possivel baixá-las por aqui, também.

`docker ps -a`				--> lista todos os conteiners, mesmo que não esteja em execução.

`docker status [nome container]`		--> exibe informações sobre o conteiner

`docker inspect [nome iamgem]`		--> Retorna um json com as informações do container

(Na nova forma de usar comandos, o `docker container inspect [nome do container/ID]` também se torna válido.)

`docker rmi [nome imagem]`		--> exclui a imagem do host

(A remoção de imagens também se dá por `docker image rm`)

`docker exec [id/nome container]`		--> usado para executar comando no container sem que precisemos estar no console dele

`docker run -it -d [imagem] /bin/bash`	--> inicia uma imagem e ja entra no bash do conteiner criado. Com o -d ele executa em segundo plano, sem o -d ele entra no bash

`[no bash do conteiner] ctrl+p+q`		--> Sai do bash do conteiner sem finalizar o conteiner

`docker attach [container id]`		--> volta para o bash do container
`docker container run -d --net none imagem_nome` --> cria um container isolado, sem acesso a nenhum tipo de rede externa ou interna.
`docker network inspect nome_da_rede(bridge, host ou qualquer rede criada no docker)` --> Exibe o trecho do json que é responsável pela rede



**com o objetivo de subir um container com o nginx rodando um arquivo que se encontra na maquina local, como proposto no curso, criei uma pasta local html e um arquivo intex.html, ao rodar o nginx através da linha de comando a seguir eu consegui realizar a interação do container com a maquina local.**

```
docker container run -p 8080:80 -v $(pwd)/html:/usr/nginx/html
```

Onde o `$(pwd)` indica o caminho do nosso diretório atual, o "`:`" faz a ligação do comando com o path para o qual o diretório selecionado vai ser copiado, seguido do caminho do diretório dentro do container nginx para o qual o nosso diretório será copiado.
