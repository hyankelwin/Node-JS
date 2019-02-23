# Ages

Aplicação que aceita a entrada de um campo do usuário por um formulário e o redireciona para a página baseado em sua idade.

Aplicação utilizando **ExpressJS, Nunjucks, EditorConfig e ESLint**.

## Rotas

- `/`: Rota inicial que renderiza uma página com um formulário com um único campo `age` que representa a idade do usuário;
- `/check`: Rota chamada pelo formulário da página inicial via método POST que checa se a idade do usuário é maior que 18 e o redireciona para a rota `/major`, caso contrário o redireciona para a rota `/minor`
- `/major`: Rota que renderiza uma página com o texto: `Você é maior de idade e possui x anos`, onde `x` é o valor informado no input do formulário;
- `/minor`: Rota que renderiza uma página com o texto: `Você é menor de idade e possui x anos`, onde `x` é o valor informado no input do formulário;

## Middlewares

Middleware chamado nas rotas `/major` e `/minor` que checa se a informação de idade não está presente nos Query Params.
