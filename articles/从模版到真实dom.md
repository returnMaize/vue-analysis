平时使用 Vue 开发项目时，我们通常是创建一个 xxx.vue 文件，然后在文件中写下类似代码

```
<template>
  <div class="app">
    <h1>{{ title }}</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "hello vue",
    };
  },
};
</script>
```

假设该文件是 App.vue 文件，然后我们在 main.js 文件中引入该文件，并且完成实例化和挂在操作

```
import Vue from 'vue'
import App from './App.vue'

new Vue({
  render: (h) => h(App),
}).$mount('#app')
```

然后我们就可以在浏览器中渲染出我们期望的视图，Vue 究竟是如何把做到的，接下来就让我们来揭开 Vue 模版到视图的神秘面纱。

首先我们先分析 App.vue 和 main.js 做了那些事情

App.vue

- template: 存放了我们的模版
- script: 导出了一个对象，对象里面包含了模版中需要用到的数据

main.js

- 实例化 Vue，并且把引入的 App 作为 options 传给了 Vue，然后调用 Vue 实例的 \$mount 方法

可能有朋友至今都不知道 App 里面到底有什么，当然好奇心比较强的朋友可能已经知道了。好奇心不强的朋友我给你们打印出来了。

![app](https://github.com/returnMaize/vue-analysis/blob/main/images/app.png)
