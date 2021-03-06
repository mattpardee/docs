---
title: 如何在组件中使用异步数据
description: 如何在组件中使用异步数据？
---

# 如何在组件中使用异步数据？

如果组件不是和路由绑定的页面组件，原则上是不可以使用异步数据的。因为 Nuxt.js 仅仅扩展增强了页面组件的 `data` 方法，似的其可以支持异步数据处理。

对于非页面组件，有两种方式可以实现数据的异步获取：

1. 在组件的 `mounted` 方法里面实现异步获取数据的逻辑，之后设置组件的数据，限制是：不支持服务端渲染。
2. 在页面组件的 `data` 方法中把子组件的数据一并获取，并通过设置子组件的属性将数据传递给子组件。这种方法支持服务端渲染，但是在父组件中获取子组件的异步数据，一方面影响代码的可读性，另一方面破坏了组件之间的独立性。

总之，使用哪种方法取决于你的应用是否需要支持子组件的服务端渲染。
