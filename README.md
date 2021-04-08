# hello-mine

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn workspace 模块名 run serve
例子: yarn workspace hello-k8s run serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### 模块管理大概流程

1.外层 package.json  加

"private": true,
"workspaces": [
"packages/*"
],

2.被调用模块 package.json  加

"module": "src/index.js",

3. 被调用模块(A) src下边新建文件  index.js 导出需要的

4. (可能不需要)在需要调用的模块(B)下执行
   yarn workspace 模块B add 模块A

例子:
当前目录yarn-workspace-demo
cd /packages/hello-k8s
yarn workspace hello-k8s add hello-docker

5.(可能不需要) 在需要调用的模块(B) 的 dependencies 下边加 模块A

6.在 需要调用的模块(B) 里边 import 被调用模块(A) 导出的
