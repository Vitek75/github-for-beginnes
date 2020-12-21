HttpPort_T: 8092 прослушка, ждет запросы от топана
HttpPort: 8090 прослушка запросов карточек от АПК
app.js line 530. var webSocketServer = new WebSocketServer.Server({ port: Cg.cnf.HttpPort + 1 }); (8091) прослушка АПК и передача информации о статусе и количестве