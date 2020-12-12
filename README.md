# react-reading-sources

## Desc

闲暇之时, 精心沉淀, 品一口82年拉菲, 啵一口陈年老酿, 读一首`react`源码, 不失为一大乐事~

这是闲时阅读`react`源码过程中的心得、笔记, 只是单纯的个人理解~

直到读源码之前, 我一直对`react`保持好奇、憧憬的态度.

**何为好奇?** 仅仅一个`setState`, 就能引发整个`react`应用的更新, 仅仅一个`state`, 就能随心所欲的切换状态.

**何为憧憬?** `react@16.8`的`hooks`着实很舒服, 我的毕设当中也大量使用, 那么诸如`useState`、`useEffect`是如何实现的? 又让我对`react`内部机理产生强烈憧憬.

所以, 在期末考之余创建了本仓库, 旨在将自己阅读源码过程中的`心得`、`体会`记录下来. 由于`react`源码着实太过庞大和难以理解, 所以仓库笔记可能跳跃度很高, 要完成可能还要很长很长时间吧.

## Toc

> **images**

| Name                            | Link                                                 |
| ------------------------------- | ---------------------------------------------------- |
| 1-FiberRoot&RootFiber&FiberTree | [链接](./images/1-FiberRoot&RootFiber&FiberTree.png) |
| 2-渲染帧                        | [链接](./images/2-渲染帧.png)                        |
| 3-concurrent                    | [链接](./images/3-concurrent.png)                    |
| 4-ReactDOM.render流程           | [链接](./images/4-ReactDOM.render流程.png)           |
| 5-react的几大更新阶段           | [链接](./images/5-react的几大更新阶段.png)           |
| 6-hooks是如何存储的             | [链接](./images/6-hooks是如何存储的.png)             |
| 7-react16生命周期               | [链接](./images/7-react16生命周期.png)               |
| 8-react组件通信方式             | [链接](./images/8-react组件通信方式.png)             |
| 9-setState是同步还是异步        | [链接](./images/9-setState是同步还是异步.png)        |

> **visio**

| Name                            | Link                                                 |
| ------------------------------- | ---------------------------------------------------- |
| 1-ReactDOM.render流程           | [链接](./visio/1-ReactDOM.render流程.vsdx)           |
| 2-scheduleCallback回调队列      | [链接](./visio/2-scheduleCallback回调队列.vsdx)      |
| 3-react_scheduler调度的主要流程 | [链接](./visio/3-react_scheduler调度的主要流程.vsdx) |
| 4-schedule三大步骤              | [链接](./visio/4-schedule三大步骤.vsdx)              |
| 5-react的三大工作状态           | [链接](./visio/5-react的三大工作状态.vsdx)           |
| 6-expirationTime的五种类型      | [链接](./visio/6-expirationTime的五种类型.vsdx)      |
| 7-react的几大更新阶段           | [链接](./visio/7-react的几大更新阶段.vsdx)           |
| 8-hooks时如何存储的             | [链接](./visio/8-hooks是如何存储的.vsdx)             |
| 9-一句话总结更新流程            | [链接](./visio/9-一句话总结更新流程.vsdx)            |
| 10-单链表树状结构               | [链接](./visio/10-单链表树状结构.vsdx)               |
| 11-react16生命周期              | [链接](./visio/11-react16生命周期.vsdx)              |
| 12-react组件通信方式            | [链接](./visio/12-react组件通信方式.vsdx)            |
| 13-setState是同步还是异步       | [链接](./visio/13-setState是同步还是异步.vsdx)       |

> **xmind**

| Name                       | Link                                             |
| -------------------------- | ------------------------------------------------ |
| 1-react各大节点之间的关系  | [链接](./xmind/1-react各大节点之间的关系.xmind)  |
| 2-react_render的update过程 | [链接](./xmind/2-react_render的update过程.xmind) |
| 3-expirationTime计算流程   | [链接](./xmind/3-expirationTime计算流程.xmind)   |
| 4-setState流程             | [链接](./xmind/4-setState流程.xmind)             |
| 5-react任务优先级&任务分片 | [链接](./xmind/5-react任务优先级&任务分片.xmind) |
| 6-expirationTime三种模式   | [链接](./xmind/6-expirationTime三种模式.xmind)   |

> **issue**

| Name                                        | Link                                                                |
| ------------------------------------------- | ------------------------------------------------------------------- |
| `ReactDOM.render`简略过程                   | [issue#1](https://github.com/ddzy/react-reading-sources/issues/1)   |
| `react`从调度到更新的简单流程               | [issue#2](https://github.com/ddzy/react-reading-sources/issues/2)   |
| `react`的几大更新阶段                       | [issue#3](https://github.com/ddzy/react-reading-sources/issues/3)   |
| `Fiber`对象的几个重要属性                   | [issue#4](https://github.com/ddzy/react-reading-sources/issues/4)   |
| `ReactDOM.render`流程再梳理                 | [issue#5](https://github.com/ddzy/react-reading-sources/issues/5)   |
| fiber的`updateQueue`的基本结构              | [issue#6](https://github.com/ddzy/react-reading-sources/issues/6)   |
| `fiber.tag`重要类型汇总                     | [issue#7](https://github.com/ddzy/react-reading-sources/issues/7)   |
| 函数组件(`FunctionComponent`)的更新         | [issue#8](https://github.com/ddzy/react-reading-sources/issues/8)   |
| `hooks`存储结构                             | [issue#10](https://github.com/ddzy/react-reading-sources/issues/10) |
| `hooks`运行机制                             | [issue#11](https://github.com/ddzy/react-reading-sources/issues/10) |
| 渲染时的优化策略                            | [issue#12](https://github.com/ddzy/react-reading-sources/issues/12) |
| 关于 `React` 的一些疑点思考                 | [issue#15](https://github.com/ddzy/react-reading-sources/issues/15) |
| \[译] `React` 为何要使用链表遍历 `Fiber` 树 | [issue#18](https://github.com/ddzy/react-reading-sources/issues/18) |
| \[译] 使用 requestIdleCallback              | [issue#20](https://github.com/ddzy/react-reading-sources/issues/20) |
| \[译] 深度探索 styled-components 工作原理   | [issue#22](https://github.com/ddzy/react-reading-sources/issues/22) |

## History

@see: [CHANGELOG.md](./CHANGELOG.md)

## LICENSE

@see: [MIT](./LICENSE)