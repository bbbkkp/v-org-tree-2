# v-org-tree


v-org-tree是一个基于Vue.js2封装的组织结构树组件，支持自定义节点和收缩按钮，高自由度定制，有水平和垂直两种方向。

> 本插件在[lison16/v-org-tree](https://github.com/lison16/v-org-tree)的基础上修改了当data变化时不要自动展开或者关闭节点



## Install
```
npm install @bbbkkp/v-org-tree
```

## Use
```
import OrgTree from '@bbbkkpv-org-tree'
import '@bbbkkp/v-org-tree/dist/v-org-tree.css'
Vue.use(OrgTree)
```

## Develop
```
npm install
npm run serve
```

## Props
prop              | descripton                   | type                   | default
------------------|------------------------------|:----------------------:|---------------------
data              | 传入的树状数据                 | Object                 | -
horizontal        | 是否垂直                      | Boolean                | false
props             | 用来指明数据中几个重要字段的命名  | Object                 | `{ id: 'id', label: 'label', children: 'children', expand: 'expand' }`
label-width       | 节点的宽度，不设则随文字宽度自适应| String \| Number      | 'auto'
collapsable       | 是否可收缩                    | Boolean                | true
node-render       | 渲染节点的render函数           | Function               | -
button-render     | 渲染收缩按钮的render函数       | Function                | -
label-class-name  | 节点自定义类名，可以是函数，参数是当前节点数据对象| Function \| String | -
expandAll         | 是否展开所有节点               | Boolean                | false

## Events
event             | descripton                  | arguments
------------------|-----------------------------|------------------------------
on-expand         | 当任一节点收缩状态改变时触发     | data(当前节点数据), status(当前节点是否展开)
on-node-click     | 点击节点时触发                 | event(鼠标事件对象), data(当前节点数据), expand(是一个方法，如果点击该节点需要收缩，需要调用次方法)
