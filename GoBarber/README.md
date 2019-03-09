# GoBarber

Aplicação que efetua agendamentos de serviço baseado no cadastro do usuário e prestador de serviço.

Aplicação utilizando **ExpressJS, Nunjucks, EditorConfig, Postgres, Sequelize e ESLint**.

## Rotas

- `/`: Rota inicial que renderiza uma página com um formulário com os campos: `Email` e `Senha` responsável por logar o usuário, e os botões `Entrar` e `Conta grátis` para direcionar o usuário para dashboard ou criar a conta;
- `/signin`: Rota chamada pelo formulário da página inicial via método POST que verifica se os dados do usuário estão corretos para direcioná-lo para a dashboard
- `/signup`: Rota que renderiza uma página com um formulário com os campos: `Imagem`, `Nome`, `E-mail`, `Senha`, `Check: Cabeleireiro(Boolean)`, responsável pela criação de um novo usuário;
- `/app`: Rota responsável pela chamada de um middleware que efetua as verificações da sessão do usuário;
- `/app/logout`: Rota responsável pelo logout do usuário e a limpeza do cache da rota;
- `/app/dashboard`: Rota que renderiza a página dashboard, com todos os cabeleireiros disponíveis para agendamento;
- `/app/appointments/new/:provider`: Rota que renderiza uma página com os dados do cabeleireiro selecionado, um campo `Data` para selecionar a data do agendamento e horário, rota responsável pela criação do agendamento;- `/app/available/:provider`: Rota responsável pela verificação e organização dos horários disponíveis para cada cabeleireiro;
- `/app/schedule`: Rota que renderiza uma página com todos os agendamento do cabeleireiro;

## Middlewares

Middleware chamado nas rotas:
`/auth`: Responsável pelas verificações da sessão do usuário;
`/guest`: Responsável por verificar se a sessão exite ou não para não deixa-lo ir direto para rotas `/app`;
