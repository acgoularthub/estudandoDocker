# Dockerfile em uma build com argumentos

Foi feito praticamente a mesma coisa que foi dita no arquivo de controle "Dockerfile-curso-build1", o que mudou foi apenas o nome da imagem e o arquivo dockerfile, que será descrito a seguir:

```
FROM debian
LABEL maintainer 'Anderson'

ARG S3_BUCKET=files
ENV S3_BUCKET=${S3_BUCKET}
```

Para acessar o argumento, na hora da construção do container foi usado o comando:
```
# docker container run nome-da-tag bash -c 'echo $S#_BUCKET'
```
que retornou
```
files
```

alterar o argumento é possivel utilizando-se do seguinte comando, no momento da build:
```
# docker image build --build-arg S3_BUCKET=myapp -t nome-da-tag-arg .
```
Assim, quando for repetir o comando que pede o conteúdo do argumento novamente, o resultado será `myapp`.