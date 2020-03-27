## vue 基础
1. 选项： 
## vue-router 基础
- beforeEach beforeResolve(在组件内守望之后) afterEach
- beforeEnter(routes配置) beforeRouteEnter beforeRouteUpdate beforeRouteLeave

## vue 工程优化规范
1. 建立服务层，处理接口数据
2. 组件无状态化，逻辑处理放在vuex action里
3. 请求若非实时，则需要缓存
4. 交互未保存修改, 使用beforeRouteLeave提示



## 代码规范
1. 命名驼峰，后端数据若是下划线，则在服务层对象解耦

## 代码实现例子
``` javascript
// 3.缓存
const a = []; const b = {}; const c = ''; const d = 0; const e = undefined; const f = null;
if (a.length === 0 || Object.keys(b).length === 0 || !c) {
  // todo
} 
```

### 面试题
描述下vue-router的生命周期？
触发导航->组件内beforeRouteLeave->全局beforeEach->重用组件内beforeRouteUpdate->路由配置beforeEnter->激活组件内beforeRouteEnter->全局beforeResolve->导航确认->全局afterEach->dom更新
