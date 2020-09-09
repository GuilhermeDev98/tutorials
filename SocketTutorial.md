O adonis Js Oferece um poderoso e robusto Socket Provider para ser utilizado em aplicações Real-time.

Pra começar é necessário instalar própria biblioteca pois ela não vem instalada no boilerplate padrão,
Para efetuar essa instalação digite o comando 'adonis install @adonisjs/websocket', epós execultar o comando, serão criados 3 novos arquivos :

config/socket.js - Contém toda a configuração do servidor Ws
start/socket.js: Starta o servidor Ws e registra canais.
start/wsKernel.js: Registra Middlewares para serem execultados quando usuários se conectarem nos canais.

Em seguida, é necessário registrar o provider dentro do arquivo start/app.js :

const providers = [
'@adonisjs/websocket/providers/WsProvider'
]

e para finalizar a instalação, insira a função .wsServer() na Classe Ignitor :

const { Ignitor } = require('@adonisjs/ignitor')

new Ignitor(require('@adonisjs/fold'))
.appRoot(\_\_dirname)
.wsServer() // boot the WebSocket server
.fireHttpServer()
.catch(console.error)
