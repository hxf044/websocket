# websocket
springboot+websocket
## 利用websocket实现向前端实时推送数据，个人简单demo

websocket分别有  @OnOpen(链接)， @OnMessage(接受消息)， @OnClose(关闭)，@OnError(错误)几个方法，另外发送方法为:

public static void sendMessage(String message,String name){
    Session s = sessions.get(name);
    if(s!=null){
        try {
            s.getBasicRemote().sendText(message);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
 }