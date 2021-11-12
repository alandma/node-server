# Node Server

Criação de containers utilizando docker, com finalidade de utilizar o node como `server` nas apps.

## Criando/Adicionando o projeto
Adicione/crie seu projeto na raiz desse repositorio, ficando parecido com algo assim;

```
node-server
├── .env
├── .gitignore
├── src
├── docker-compose.yml
├── Dockerfile.dev
├── Dockerfile.prd
├── server.js
├── package.json
└── README.md
```
## Alterações e variaveis
As variaveis da app ficam na pasta `.env` e há duas criadas como exemplo, mas pode ser alteradas conforme desejado.

Outro arquivo que contem variaveis que dever ser alteradas de acordo com o projeto é o `docker-compose.yml`;

* **NODE_TAG**: Definirá a versão do _node_ que será utilizado, criando a _imagem docker_ para a subir o _container_.
  >Para verificar todas as versões disponiveis (`TAGs`), consultar [Tags Node](https://hub.docker.com/_/node/?tab=tags) no dockerhub oficial.

## Executando o projeto
Com tudo definido vamos executar o projeto.

No `docker-compose.yml` temos duas possibilidades de execução, `desenvolvimento` (**node-dev**) e para efetuar o _build_ de `produção` (**node**).

### Executar o ambiente de "**dev**";
```console
docker-compose up node-dev
```
sem o parametro "[-d](#Referencias)" a saida ficará "travada" no console, para observação dos logs.

>No `ambiente de dev` o codigo fica "espelhado" com o container, dessa forma,  pode-se trabalhar localmente e visualizar os resultados em tempo real.

### Compilando (_build_) o projeto para "**produção**";
```console
docker-compose up -d --build node
```

#### Referências:

- https://docs.docker.com/compose/compose-file/compose-file-v3/
- https://docs.docker.com/engine/reference/builder/
- https://hub.docker.com/_/node/
- https://docs.docker.com/compose/reference/up/
