# 整体项目愿景

> 其中包括 cortex 及周边所有项目的未来目标。

## 解决方案

- 前端包管理
- 服务器端 bundle，包括混合应用方案
- 版本管理方案
- 模块仓库及搜索服务
- 持续集成、发布方案
- 测试框架相关


# Cortex 项目目标

Cortex 是一个开源的前端包管理器，与目前一些包管理器不同的是，cortex 周边还包含端到端，从前端到后端完整的解决方案，让前端与后端互相融合，无缝衔接。

Cortex 设计的很大目的，在于让开发工程师专注，专注在真正的需求上，而将周边的麻烦事情，交给系统来处理。我们希望做好信息架构，让各个系统间的结构变得透明，在系统层面减少约定，在用户层面减少配置。

## 领域范围

Cortex 核心的返回，仅仅作为包管理器，与 npm 类似，主要服务于两种场景：

#### 本地开发

作为包管理器，定义开发生命周期，及提供静态服务。

#### 持续集成环境

作为包管理器。

## 目标

#### 为 Web 而生

Cortex 的设计方案，都以 web 开发为优先考虑目标。

#### 模块化

Cortex 想要的模块化，不仅仅只是将文件拆分，或者项目拆分，而是提供一种标准的方式，从本质上将代码划分为相对独立的逻辑单元，并且让它们能够有效地组织在一起，协同工作。同时使模块间的依赖关系透明化，消除隐式依赖及插件式依赖（peerDependencies）。

我们还要求模块间能够完全独立，即使我需要合并多个模块，也不需要做额外的处理，而是直接合并多个文件。

#### 减少间接需求

Cortex 努力从信息架构设计上，从交互方案上，让开发者仅需要关注在自己的当前需求上，而不用为其他的事情担忧。保留在整个生命周期中信息的完整性，从而让更多的关注点能够交给工具和系统来完成。

#### 版本管理

为了满足分布式的多人开发，以及大型企业级对于稳定性的高要求，我们非常注重包的版本管理。我们要求 cortex 及周边的所有项目，都能够支持精确的版本控制，包括依赖的版本控制，开发阶段的版本控制，不同发布（测试）阶段的版本隔离，服务端的版本校验，持续集成有关服务的版本校验，并且让网页应用中也能够有效的管理这些版本。

同时，我们已经找到很好的方案能够让开发者在整个开发周期之中，能够尽量少地去关心这些问题，而尽量让系统来搞定它们。我们也在不断寻找更好的方案。

版本管理方案也是 cortex 与其他包管理器最大的不同点之一。

#### 线上调试 

我们非常在意在线应用的可调试性，我们希望所有的网页应用，我们都能够一键配置完成本地开发环境。在某些情况下，我们甚至能够让开发者告别 fiddler 或者 charles。


## 非目标

有一些内容，我们认为不是 cortex 的核心目标，或者明确认为不是 cortex 的职责范围。但也有可能会在另外的项目中实现他们，这些项目可能存在于 [cortexjs/ group](https://github.com/cortexjs) 中。

#### cortex 不是构建工具

Cortex 不关心项目中的文件，开发过程中如何构建，例如 less 如何编译为 CSS，CoffeeScript 如何编译为 JavaScript。

但是 Cortex 提供定义了项目开发过程中生命循环的关键帧，并提供了一种标准的方式，如何将这些过程串通和连贯起来。

#### Cortex 使用真枪实弹，而不是为了科学研究

我们更倾向于使用被证明可行的，能够在生产环境稳定运行的可靠的技术（无论技术的新旧），我们会展望未来，但也需要避免过于激进。

#### Cortex 可能并不适用于所有场景

**多人开发**、**工业化生产** 和 **维护性** 是 cortex 最优先考虑的，而对于类似那种 5 分钟开发完毕，存活时间如昙花一现的小项目，cortex 并不会过于关心。

#### 跨平台不是 Cortex 的要务

Cortex 专注于 web 前端开发，而对于其他场景，如嵌入式的 JavaScript 项目，运行在非常规引擎和环境下的用例，我们可能不会花太多精力在上面。

跨平台很多时候是一个伪命题，而模块化最不容易处理的就是基础依赖的问题。Cortex 不会过分的追求所谓服务端与前端使用相同的代码。

