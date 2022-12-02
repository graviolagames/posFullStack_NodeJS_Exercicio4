
Pontifícia Universidade Católica de Minas Gerais
Curso: Desenvolvimento web Full Stack
Disciplina: Programação web com Node.js
Professor: Samuel Martins
Valor: 20pts

Exercício 4
Neste exercício iremos estudar sobre as formas de autenticação de usuários baseada no OAuth com o
Passportjs. Para o exemplo do exercício, iremos utilizar a strategy do Github.

Passo 1
Iremos implementar a estratégia de autenticação no Github. Se você ainda não possui uma conta, crie
aqui. Em seguida, siga o tutorial do próprio github para criar uma aplicação e ter acesso a um CLIENT_ID
e um CLIENT_SECRET, necessários para autenticação.
https://developer.github.com/apps/building-github-apps/creating-a-github-app/
Em Homepage URL e User authorization callback URL substitua por http://localhost:3000 e
http://localhost:3000/auth/login/github/callback, respectivamente.

Passo 2
Clonar o repositório abaixo:
https://github.com/samwx/nodejs-passport-v2

Passo 3
Iremos desenvolver uma aplicação com autenticação no github e uma página protegida. Para isso, após
clonar o repositório do Passo 2, certifique que a aplicação funciona normalmente rodando o comando
npm install e em seguida npm start.

Passo 4
Copie o CLIENT_ID e CLIENT_SECRET gerados no passo 1 e substitua-os no arquivo passport.js dentro da
pasta “auth”.

Passo 5
Iremos implementar o nosso botão de login no github. Para isso, no arquivo login.hbs dentro da pasta
views, crie um link para a rota /auth/login/github (iremos implementá-la nos passos seguintes).

Passo 6
Implemente uma rota /admin, com verificação de sessão ativa conforme o exemplo abaixo:
router.get('/admin', ensureAuthenticated, function(req, res) {
res.render('admin', { user: req.session.passport.user })
});
O objeto “user” possui as propriedades “displayName” e “provider”. Crie um arquivo admin.hbs na pasta
views e exiba uma mensagem de boas-vindas ao usuário logado, juntamente com a informação
“provider”.

Passo 7
Por último, faça o seguinte teste: abra o link http://localhost:3000/admin em uma janela anônima e
certifique de que o usuário não terá acesso a área logada. Caso esteja tudo ok, no arquivo admin.hbs,
coloque um link para a rota /logout para deslogar o usuário do sistema.
