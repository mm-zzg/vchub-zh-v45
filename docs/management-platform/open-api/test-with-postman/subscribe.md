# 订阅实时数据

Open API 提供了用于实时数据访问的 WebSocket API。

通过使用 WebSocket API，您可以订阅实时数据，包括变量值、变量属性和报警。

1. 打开postman主页，点击按钮 **+**, 然后点击 **View more templates**。

    ![alt text](13.png)

2. 点击左侧 **API protoco 101**,然后在右侧选择 **WebSocket basics**。

    ![alt text](14.png)

3. 在 **WebSocket基础** 下创建一个新文件夹。点击新文件夹的下拉菜单以打开菜单，如下图所示，然后点击 **WebSocket** 选项。

    ![alt text](15.png)

4. 在地址栏中输入地址 wss://localhost:8043/ws/v1/realtimeData

    ![alt text](16.png)

5. 在 **Params** 中输入 access_token, 注意 websocket 的 access_token 前面不需要添加   Brear

    ![alt text](17.png)

6. 点击 **Connect** 按钮，Postman 将显示 WebSocket 连接已建立。

    ![alt text](18.png)

7. 成功连接后，在Message Tab下发送以下的报文, 注意报文结尾处的特殊字符![alt text](22.png)不能遗漏，第三行报文中的 `[["Default:m1","Default:m2","Default:m3"]]` 需要替换成工程中实际上存在的变量

    {"protocol":"json","version":1}![alt text](22.png)

    {"type":6}![alt text](22.png)

    {"arguments":`[[Default:m1","Default:m2","Default:m3]]`,"invocationId":"0","target":"TagValues","type":4}![alt text](22.png)

    ![alt text](19.png)

8. 成功发送上述的三个报文之后会接收到变量的推送

    ![alt text](20.png)

9. 上述示例演示了标签值的订阅方法。对于其他 WebSocket API，请参考 [实时数据接口定义](../realtime-data-api-definitions.md) 章节。下述示例请求体中的 target 字段，对应实时数据 API 的方法名。只需将 target 字段的值替换为 **实时数据接口定义** 文档中指定的方法名，即可调用其他 WebSocket API。

    ![alt text](21.png)
