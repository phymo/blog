近在跟着官方文档学习vue.js的文章，当看到禁用继承特性这一点的时候不是很理解，后跟着官方的实例运行了一下，算是弄懂了一些，特此记录，仅供参考！

首先假设如今有一个组件`<base-input></base-input>`,创建改组件式的代码如下：

```
Vue.component("base-input", {
  inheritAttrs: false, //此处设置禁用继承特性
  props: ["label"],
  template: `
    <label>
      {{ label }}
      <input
        v-bind="$attrs"
      >
    </label>
  `,
  mounted: function() {
    console.log(this.$attrs);
  }
});
```


在app.vue中调用改组件时的代码如下：

```
<base-input
      label="姓名"
      class="username-input"
      placeholder="Enter your username"
      data-date-picker="activated"
    ></base-input>
```


运行后再chrome浏览器查看html结构时的结果如下：

```
<label class="username-input">
      姓名
      <input placeholder="Enter your username" data-date-picker="activated">

</label>
```

而当我们将inheritAttrs这行代码注释的时候其html文档又会如下所示：

```
<label placeholder="Enter your username" data-date-picker="activated" class="username-input">
      姓名
      <input placeholder="Enter your username" data-date-picker="activated">

</label>
```

我们发现现在label标签和input标签上此时都继承了父组件的属性。

label标签是默认会继承来自父组件的属性，而input标签能继承则是因为我们使用了`v-bind="$attrs"`。

假如我们将`v-bind="$attrs"`去掉则会发现如今的html的结构又会变成下面这样：

```
<label placeholder="Enter your username" data-date-picker="activated" class="username-input">
      姓名
      <input>

</label>
```

本着探索的精神现在我们再把inheritAttrs这一句话加上，将`v-bind="$attrs"`放到label标签上，结果相信大家都能知道了，在这里就不详细说了。

很多人有可能会对`v-bind="$attrs"`不太理解，这里我贴上官方的解释：

vm.$attrs

类型：{ [key: string]: string }

只读

详细：

包含了父作用域中不作为 prop 被识别 (且获取) 的特性绑定 (class 和 style 除外)。当一个组件没有声明任何 prop 时，这里会包含所有父作用域的绑定 (class 和 style除外)，并且可以通过 v-bind="$attrs" 传入内部组件——在创建高级别的组件时非常有用。

以我的理解就是用于获取标签中除class和style之外的标签上的属性。
--------------------- 
作者：不看山不看水 
来源：CSDN 
原文：https://blog.csdn.net/s_web_q/article/details/80239707 
版权声明：本文为博主原创文章，转载请附上博文链接！