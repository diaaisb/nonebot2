---ip安装nonebot2nonebot-adapter-cqhttpnonebot-plugin-apscheduler
侧栏位置：0
身份标识：索引
段塞：/
---

#概览

NoneBot2是一个现代、跨平台、可扩展的python聊天机器人框架（下称NoneBot)，它基于python的类型注解和异步优先特性（兼容同步），能够为你的需求实现提供便捷灵活的支持。同时，NoneBot拥有大量的开发者为其开发插件，用户无需编写任何代码，仅需完成环境配置及插件安装，就可以正常使用NoneBot.

需要注意的是，NoneBot仅支持**Python3.9以上版本**

##特色

###异步优先

NoneBot基于python[异步](https://docs.python.org/zh-cn/3/library/asyncio.html) / [三重唱](https://trio.readthedocs.io/en/stable/)编写，并在异步机制的基础上进行了一定程度的同步函数兼容。

###完整的类型注解

NoneBot参考[PEP484](https://www.python.org/dev/peps/pep-0484/)等PEP完整实现了类型注解，通过Pyright(Pylance)检查。配合编辑器的类型推导功能，能将绝大多数的Bug杜绝在编辑器中([编辑器支持](./editor-support)）。

###开箱即用

NoneBot提供了使用便捷、具有交互式功能的命令行工具--`nb-cli`，使得用户初次接触NoneBot时更容易上手。使用方法请阅读本文档[指南](./quick-start.mdx)以及[CLI文档](https://cli.nonebot.dev/)。

###插件系统

插件系统是NoneBot的核心，通过它可以实现机器人的模块化以及功能扩展，便于维护和管理。

###依赖注入系统

NoneBot采用了一套自行定义的依赖注入系统，可以让事件的处理过程更加的简洁、清晰，增加代码的可读性，减少代码冗余。

####什么是依赖注入

[**『依赖注入』**](https://zh.wikipedia.org/wiki/%E6%8E%A7%E5%88%B6%E5%8F%8D%E8%BD%AC)意思是，在编程中，有一种方法可以让你的代码声明它工作和使用所需要的东西，即**『依赖』**。

系统（在这里是指NoneBot)将负责做任何需要的事情，为你的代码提供这些必要依赖（即**‘注入’**依赖性）

这在你有以下情形的需求时非常有用：

-这部分代码拥有共享的逻辑（同样的代码逻辑多次重复）
-共享数据库以及网络请求连接会话
-比如`httpx.AsyncClient`、`aiohttp.ClientSession`和`sqlalchemy.Session`
-机器人用户权限检查以及认证
-还有更多...

它在完成上述工作的同时，还能尽量减少代码的耦合和重复
