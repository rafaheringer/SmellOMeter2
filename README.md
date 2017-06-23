# SmellOMeter2



## Testando localmente

Por ser uma aplicação Node, primeiramente instale todas as dependências:

```
npm install
``` 

O slash command do slack realiza uma requisição para o servidor e aguarda uma resposta ok. Para testar localmente, é necessário expor seu servidor local. Utilizei o [**localtunnel**](https://github.com/localtunnel/localtunnel) para isso, instale via npm:

```
npm install -g localtunnel
```

Inicie o serviço:

```
lt --port 8765 --subdomain smellometer
```

Pronto, a porta 8765 de sua máquina estará disponível na url retornada. Agora basta iniciarmos a aplicação:

```
npm start
```

Note que no arquivo `package.json` start script possui algumas configurações de exemplo sobre autenticação do seu app no slack. Remova essas configurações e as adicione como variável de ambiente ao colocar em produção.

Não se esqueça que é necessário resgatar o CLIENT_ID e CLIENT_SECRET, para isso você deverá registrar o app no [site da API do Slack](https://api.slack.com/apps/).

## Colocando no ar

A solução escolhida foi o NOW da [Zeit.co](https://zeit.co) para hospedar rapidamente a aplicação Node e o [Firebase](https://firebase.google.com) como solução para guardar os dados resgatados dos sensores.

Para criar um Firebase Database, você poderá seguir [tutorial](https://firebase.google.com/docs/server/setup).

