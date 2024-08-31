# GodHook
**一切皆可API：HOOK并通过WebApi请求目标APP的函数。**

待办：

- [ ] 留一个帖子让大家留言bug或者大家点击本APP右上角进入[群聊](https://t.me/god_hook_nnbs)
- [ ] 发布一篇帖子：如何使用magisk-frp模块，通过公网请求内网API？（即任何地方都可以通过公网请求API，从而控制机器人发送消息）
- [ ] 当前仅适配wx8.0.49(2681)，后续适配wx更多版本
- [ ] 有时间再整作用域更多APP

## 1.关于目标APP：WX的简要说明

> **抛个砖：通过请求API发送消息给指定的聊天窗口**
>
> > API：[http://IP:5888/?wxIds=['聊天室ID_1','聊天室ID_2']&amp;msg=消息](http://IP:5888/?wxIds=['聊天室ID_1','聊天室ID_2']&amp;msg=消息)
> >
> > | 参数    | 说明                             |                                        |
> > | ------- | -------------------------------- | -------------------------------------- |
> > | IP:5888 | 手机局域网IP+端口                | 如果不懂手机的本地IP，不建议往下折腾。 |
> > | wxIds   | 这是一个集合，聊天室ID的集合列表 | 聊天室是什么，下面有说明               |
> > | msg     | 文字消息                         | 推送到指定聊天室的消息，当前仅支持文字 |
>
> **聊天室是什么？**
>
> > 即：私聊窗口、群聊窗口、文件传输助手
> > 比如本APP登录的WX作为机器人，该WX的好友或者群聊在聊天时候的窗口，就是聊天室。
> >
> > 聊天室ID：私聊窗口(wxid_xxxxxxx)、群聊窗口(xxxxx@chatroom)、文件传输助手(filexxxxx)
> > 聊天室ID本质就是用户的wxid或者群聊的id...
>
> **需要使用本机器人，就一定要进行绑定聊天室**
>
> > 在聊天室发送指令`#绑定聊天室`既可绑定该聊天室ID=>wxIds
>
> **取消机器人服务**
>
> > 在聊天室发送`#解绑聊天室`既可删除该聊天室ID=>wxIds
>

## 指令大全

| 功能描述                                | 发送指令                                      | 备注                                               |
| --------------------------------------- | --------------------------------------------- | -------------------------------------------------- |
| 机器人绑定聊天室                        | #绑定聊天室                                   |                                                    |
| 机器人解绑聊天室                        | #解绑聊天室                                   |                                                    |
| 查询本聊天室ID                          | #聊天室ID                                     | 对于开发者使用api：用于发送消息到指定聊天室        |
| 查询已绑定的聊天室（管理员）            | #当前聊天室                                   |                                                    |
| 解绑全部机器人（管理员）                | #解绑全部聊天室                               | 相当于清空业务，重新开始                           |
| 查询API使用方法（管理员）               | #API说明                                      | 返回简单的使用说明                                 |
|                                         |                                               |                                                    |
| 进群欢迎（管理员）                      | #进群欢迎语:\n欢迎进群，群内规则：1.xx; 2xxx; | \n是换行符，不要打出来                             |
| 查询本群欢迎语（管理员）                | #查询本群欢迎语                               |                                                    |
| 取消群组欢迎语（管理员）                | #取消本群欢迎语                               |                                                    |
|                                         |                                               |                                                    |
| 订阅定时器启动(已弃用，已自动每天10:15) | \#订阅:启动                                   | 每次重启WX，都需要手动启动，后期配置成自动         |
| 订阅业务1                               | #订阅:每日60s                                 | 如需取消：#取消订阅:每日60s                        |
| 订阅业务2                               | #订阅:历史上的今天                            | 如需取消：#取消订阅:历史上的今天                   |
| 订阅业务......                          | ......                                        | ......                                             |
|                                         |                                               |                                                    |
| 群成员需要被@                           | #需求:xxx \| #艾特我:xxx                      | 如果推送的消息内容中存在xxx，则@发出该指令的群成员 |
| 群成员查询自己的@                       | #我的需求 \| #我的艾特                        | 群成员查询自己设置过的关键字                       |
|                                         |                                               |                                                    |
|                                         |                                               |                                                    |

