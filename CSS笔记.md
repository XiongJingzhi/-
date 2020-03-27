## 自适应方案

>《使用Flexible实现手淘H5页面的终端适配》2015-12
>
>《再聊移动端页面的适配》2017-08
>
>《如何在Vue项目中使用vw实现移动端适配》2018-01

### flexible 方案

- 根据dpr的值来修改viewport实现1px的线
- 根据dpr的值来修改html的font-size，从而使用rem实现等比缩放
- 使用Hack手段用rem模拟vw特性


### vm 方案
postcss-aspect-ratio-mini:
构建固定长宽比容器, 父容器相对定位，伪元素aspect-ratio(padding-top)撑起高

postcss-px-to-viewport
通过配置postcss插件设置, 可排除hairlines

postcss-write-svg
解决1px border

postcss-preset-env
postcss-cssnext其实就是cssnext。该插件可以让我们使用CSS未来的特性，其会对这些特性做相关的兼容性处理。其包含的特性主要有:
继承、嵌套写法、全局变量、计算颜色

```
<!-- variable -->
:root {
  --mainColor: #12345678;
}
<!-- mixin define --; use @apply -->
:root {
  --flex-basic: {
    display: flex;
    flex-wrap: no-wrap;
  }
  --flex-horizontal-btw: {
    @apply --flex-basic;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
}
```
postcss-viewport-units
hack不支持vw的Android的4.0，可以放弃

cssnano
cssnano主要用来压缩和清理CSS代码

#### react 使用


#### vue 使用
