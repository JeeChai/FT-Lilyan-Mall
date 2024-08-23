# Liljan商城前端

## 启动项目

```shell
npm run dev
```

## 构建项目

```shell
npm run build
```

## 构建

### 安装脚手架（已完成）

```shell
npm create vue@latest
```

### 安装依赖（已完成）

```shell
npm install
```

### 安装elementUI-plus（已完成)

```shell
npm install element-plus --save
```

### 导入依赖（已完成）

在./src/main.ts中替换

```ts
import { createApp } from 'vue'
import ElementPlus from 'element-plus'
import 'element-plus/dist/index.css'
import App from './App.vue'

const app = createApp(App)

app.use(ElementPlus)
app.mount('#app')
```

## 登录页面

### 管理员登录页面（TODO）

### 卖家登录页面（TODO）

### 买家登录页面(TODO)