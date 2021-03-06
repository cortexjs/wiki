# 在线调试

对于调试，cortex 的设计思路，是希望将在线服务中的所有静态文件都引流到本地，并且能够轻易地启动整套测试服务。

如果你的项目使用了 neocortex，请直接看 [这个文档](./debug-neocortex.md)

## 有哪些武器可以使用？

可以用到那些命令或者工具。

### cortex 本地静态服务

```
cortex server
```

cortex server 除了能够启动静态服务之外，而且当某一个资源在本地不存在的时候，cortex 能够根据当前 profile 的配置，从 registry 源自动下载缺失的模块到本地 —— 也就是说，**只要一条命令，cortex 就能够启动完整的测试环境**。

之所以能实现这一点，得益于 cortex 的设计理念希望将发布和部署阶段完全交给工具来解决，因此 cortex 能够统一的管理路径信息。


### 下载任意指定模块到本地

大家是否还在为不知道某个静态文件属于哪个项目而苦恼吗？使用 cortex，基本上不用为这个问题而担心。

默认情况下，基于 cortex 的项目会发布到 `<server_root>/<package-name>/<version>/` 目录，因此仅从文件路径上就可以判断出该项目的名称。

而开发者不需要知道项目的 git 地址（是的，我们目前只支持 git 项目，什么，你们还用 svn 么？），只需要使用如下命令：

```
cortex install <package-name>@<version> --clone
```

之后该 git 项目就会被安装到 `workspace` 目录中。如果想更改 `workspace` 的地址，可以使用 `cortex config workspace` 命令。


### 调试具体模块

做这件事，需要在当前项目中使用到 `cortex build` 命令。也可以使用 `cortex watch` 来监视当前项目的变化，当项目中的代码发生变化时，代码会自动发布到本地服务中。

### 断点

断点不是 cortex 考虑的事情，可以使用浏览器的开发者工具来打断点。

### 代理静态文件

可以使用 [fiddler2](http://fiddler2.com/)（windows）或者 [charles](http://www.charlesproxy.com/)（mac）来将静态文件代理到本地。

如果使用了 neocortex，则可以直接用 cortex 来完成这些事情，而告别 fiddler 和 charles。