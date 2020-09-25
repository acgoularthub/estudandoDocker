# Exemplo Usado:
Usando uma imagem do nginx, foi carregado um arquico HTML local para subir junto a imagem. A vantagem desse procedimento é que a página gerada muda em tempo real 
conforme o arquivo base é alterado.
Para usar o arquivo, a flag `-v` do docker é chamada, após ela o path da pasta de origem do arquivo`:`o path de destino na imagem.

A flag `-d` permite que o container rode em segundo plano

`--name` seguido de um nome, nomeia a maquina, para que fique mais facil manuseá-la

`-p` expõe as portas e define as portas pela qual o host vai acessar o servico, por exemplo `-p 8080:80`, onde o host vai ler a partir da porta 8080 as informações da porta 80
 da imagem. Para acessar o host pode usar o endereço: `localhost:8080`



```
docker container run -d --name exemplo -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx
```
