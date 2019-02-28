# computed

默认只有getter， 也可以在需要的时候提供setter

# computed vs methods

methods 方法需要调用： {{ reversedMessage() }}

computed 计算属性基于他们的依赖进行缓存的，只有相关依赖发生改变时才会重新求值。

methods 每当触发重新渲染是，调用methods

总会再次执行函数

# computed vs watch

当你有一些数据需要随着其它数据变动而变动时，最好用计算属性；

当需要在数据变化时执行异步或开销较大的操作时，watch是最有用的。

除 watch：外，也可以使用`vm.$watch`



