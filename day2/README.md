## vue实例简介
一个vue实例创建的时候，会把data对象中的属性添加到vue的响应系统中去。当那些属性变化时，view将更新。

### 不会触发响应的两种情况
+ 在对象中添加属性
+ 调用了Object.freeze()

## vue生命周期简介
每个vue的实例在创建时都会有一些列的初始化步骤，比如设置数据监听，模版编译，将实例绑定到DOM中，在数据变更时更新DOM。
并且在每个生命周期阶段都会执行钩子行数，并且给开发人员在每个步骤添加自己的方法

### vue的生命周期
+ 创建一个vue实例（new Vue()）
+ 初始化事件和生命周期
    + beforeCreate
+ 初始化injection和reactivity
    + created
+ 如果有template选项，则编译template为渲染函数；否则，将el的外层outerhtml作为template
    + beforeMount
+ 创建$el并将el替换为$el
    + mounted
        + 当数据发生变化
            + beforeUpdate
        + 虚拟DOM重新渲染
        + updated
+ mounted
+ 调用vm.$destory()
    + beforeDestory
+ 拆除watchers，子组件和事件监听
+ destoryed
+ destoryed

### vue生命周期中的钩子方法可以做哪些事情？

## 模版语法
vue使用了以html为基础的模版语法，用于以声明式的方式将渲染的DOM与底层vue实例中的数据进行绑定。

+ {{}}
将data中对应的数据转换为纯文本

+ v-html
将html渲染为html而非纯文本

+ 指令v-bind

{{}}不能用于html属性，可以使用v-bind

+ JavaScript表达式

```javascript

{{ number + 1 }}

{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

```
每个绑定只能包含一个表达式

+ 指令参数
v-bind:href;v-on:click 冒号后面的是指令的参数，表示bind的属性值或者事件的类型

+ 动态指令参数
v-bind:[attributeName] 这里的attributeName可以通过JavaScript表达式计算得出
attributeName只能是字符串类型，如果attributeName值为null则表示删除bind，如果attributeName为非字符串值则会报警




