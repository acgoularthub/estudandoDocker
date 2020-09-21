Repositório com objetivo de uso próprio, com os comando mais utilizados ao longo dos cursos.

#Comandos

docker ps 				--> Exibe todos os conteiners em execução.
docker info 				--> exibe informalções do docker host.
docker version 				--> exibe a versão do cliente docker utilizado.
docker images 				--> exibe as imagens baixadas pelo docker no host.
docker search [parâmetro]		--> usado para procurar imagens que podem ser usadas.
docker pull [parâmetro]			--> usado para fazer o download da imagem, puramente. 
docker run [parâmetro]			--> usado para executar a imagem, caso você não tenha a imagem, é possivel baixá-las por aqui, também.
docker ps -a				--> lista todos os conteiners, mesmo que não esteja em execução.
docker status [nome container]		--> exibe informações sobre o conteiner
docker inspect [nome iamgem]		--> Retorna um json com as informações do container
docker rmi [nome imagem]		--> exclui a imagem do host
docker exec [id/nome container]		--> usado para executar comando no container sem que precisemos estar no console dele
docker run -it -d [imagem] /bin/bash	--> inicia uma imagem e ja entra no bash do conteiner criado. Com o -d ele executa em segundo plano, sem o -d ele entra no bash
[no bash do conteiner] ctrl+p+q		--> Sai do bash do conteiner sem finalizar o conteiner
docker attach [container id]		--> volta para o bash do container
