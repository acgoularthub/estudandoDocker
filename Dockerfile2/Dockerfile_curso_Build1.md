# Primeira tentativa de criar um dockerfile

Esse dockerfile está sendo feito com base no que está sendo passado pelo curso de Docker, apresentado no README deste repositório.

# Passos:

No repositório escolhido/criado para esta prática, foi criado um documento com o exato nome **Dockerfile** e com auxílio do `nano` foi alterado:

```
# nano Dockerfile
```

Com o arquivo aberto, foram inseridas as Seguintes informações:
```
FROM nginx:latest
RUN echo '<h1>Hello World!</h1>' > /usr/share/nginx/html/index.html

```
Salvei o arquivo e fechei o nano.

No mesmo diretório, iniciei a imagem que "criamos":

```
# docker image build -t nome-da-tag ,
```

Ao verificar com o comando `docker image ls`, ja foi possivel ver a imagem montada. Logo iniciei a imagen para construir nosso container:

```
# docker container run -p 80:80 nome-da-tag
```

Após subir o container, bastou acessar o `localhost:80` ou simplesmente `localhost` que foi possível ver a mensagem que gravamos sendo executada no navegador.

Mais uma prática simples que foi executada com êxito.