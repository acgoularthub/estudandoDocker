# Pratica mais complexa
Nesta prática, vamos criar um pequeno servidor usando a linguagem python, montar um container para hospedar o servidor, expondo a porta 8000 do container.

o dockerfile ficou assim:

```
FROM python:3.6
LABEL maintainer 'Anderson <acgoulart>'

RUN useradd www && \
    mkdir /app && \
    mkdir /log && \
    chown www /log

USER www
VOLUME /log
WORKDIR /app
EXPOSE 8000
ENTRYPOINT [ "/usr/local/bin/python" ]
CMD [ "run.py" ]
```
No dockerfile a gente utilisou como base a imagem do python, usamos comando de concatenação para não gerar muitas camadas no nosso container, o que é uma boa prática, segundo a documentação oficial do docker. Definimos usuário, expomos a porta e rodamos nosso servidor.

Fizemos, também, um pequenos script HTML apenas para ser espelhado no nosso servidor.

No momento de execução do nosso container, utilizamos o seguinte comando:

```
# docker container run -it -v $(pwd):/app -p 80:8000 --name python-server exemplo-build-dev
```

Como é possível observar no comando acima, criamos um "path" para o nosso html ser apresentado pelo servidor. O mesmo funcionou como deveria e mais um exemplo foi concuido com sucesso.