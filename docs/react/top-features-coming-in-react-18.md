# 第 18 反应区的顶级功能

> 原文:[https://www . geeksforgeeks . org/top-features-in-react-18/](https://www.geeksforgeeks.org/top-features-coming-in-react-18/)

你是网络开发者吗？如果是，那么你一定知道 React 是一个非常流行的 JavaScript 库。有大量的公司正在为此努力。每一项网络技术都在逐渐更新。React 团队已经开始开发 React 18，这将是主要版本之一。这个版本叫做 React 18 Alpha。

![](img/fd3e6d22150adf630b30e74a1320ba1e.png)

现在你在想这个新版本可能会有重大变化，你必须学习很多新东西，所以这不是真的。React 团队成立了一个工作组，通过接收多种反馈并实施它们，逐渐形成一个采用 React 18 新功能的社区。因此，让我们从 React 18 Alpha 中添加的功能开始。

现在让我们了解一下 React 18 中的一些新功能。

**1。并发性:**并发性是同时执行多个任务的能力。让我们考虑用户正在点击或输入一个反应组件，同时一个动画正在另一个反应组件的一个组件中播放。这里，当用户键入或单击按钮时，动画在“反应”上下文中呈现。

在以前的版本中，React 负责管理所有这些钩子调用、函数调用等。同时，用户感觉应用程序正在备货。为了解决这个问题，那里有一个调度程序，它的主要任务是调用这些回调并确定其优先级。但是现在 React 团队提供了 Transition API，通过它 React 可以让用户控制这个事件循环

**2。过渡应用编程接口:**如上所述，过渡应用编程接口提供了对并发性的控制。startTransition API 允许开发人员指出 React 哪些操作可能会阻塞线程并导致屏幕延迟。类似地，React 提供了一个新的钩子，称为 useTransition。这将非常有助于在转换挂起时显示加载程序。因此，如果您想知道什么时候应该转换应用编程接口，那么答案是无论您在哪里发现渲染阻塞进程或网络调用，都尝试使用这些。

**3。悬疑 API:** 为了提高服务器端渲染上下文中的 React Performance，React 团队做了很多改动。那么现在，您可能会有一个问题，什么是服务器端呈现的上下文？因此，这是一种在服务器上将 JavaScript 数据呈现为 HTML 的方式。所有这些都是为了节省前端的计算时间，并且有助于更快地加载起始页。

在这里，为了将你的应用分解成更小的独立单元，你可以使用悬疑应用编程接口。服务器端渲染包括 4 个步骤，悬疑应用编程接口将独立执行这 4 个步骤，不会阻塞剩余的应用程序。

*   为服务器上的每个组件提取数据。
*   在发送到服务器上的客户端之前，整个应用程序呈现为 HTML。
*   在客户端获取整个应用程序的 JavaScript 代码
*   水合作用——JavaScript 连接到客户机上服务器生成的 HTML

**4。自动批处理:**批处理简单地意味着将所有状态更新组合到一个渲染中。在 React 17 及更早版本中，在浏览器事件期间，通过单击批量重新渲染更新进行响应。React 17 不会收集再分发，如果你需要下载数据和更新他们的状态。对于 reaction 18，如果您使用新的根 API，所有状态更新都会在发生时自动更新。此外，承诺、超时或其他事件处理程序也将利用这一点。无论发生在哪里，它都会进行状态更新。这肯定会提高我们应用程序的性能。

**5。** **新的根 API:** 在 reactDOM.render 方法中的 React 18 之前，我们使用传递主 App 组件，然后使用 document.getElementById 我们使用的是存在于 index.html 内部的根元素。所以我们实际上在做的是将应用程序组件呈现到页面的根元素中。但是现在我们首先必须使用 createRoot 方法创建根，该方法在根元素中传递，然后我们调用 root.render 来传递应用程序组件。