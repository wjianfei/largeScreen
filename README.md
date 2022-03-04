# 项目描述 
## 武钢大屏
### node版本v12.16.0
### 项目运行：推荐yarn
```
yarn

npm start

http://localhost:8080/

```
```
文档结构：

src   --- 主体工程目录
|
---assets  ---静态资源目录(图片、字体文件等)
|
---common  ---公用js方法
|
---components   ---子组件
|     |
|     |------commons (自定义组件)
|     |
|     |------echart (框架自带组件)
|
---router  ---路由配置(暂时不用管只有一个单页面)
|
---store   ---状态值(暂时不用)
|
---views  ---视图(对应路由)
|     |
|     |------index.vue (首页)
|     |
|     |------leftBox.vue (左侧图表)
|
---App.vue   ---入口文件
|
========================================
```