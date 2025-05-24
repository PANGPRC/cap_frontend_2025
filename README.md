# 在线学习 门户页

## 项目简介

本项目是“在线学习”平台的门户前端，基于 Vue 3 + TypeScript 开发，面向学员和机构用户，提供课程浏览、学习、作业、资料、订单等全流程服务。项目采用模块化设计，支持多角色切换，界面美观，交互友好。

## 主要功能

- 课程浏览与搜索
- 课程详情与报名
- 个人中心（我的课程、订单、作业、资料等）
- 机构后台管理（课程、教师、资料、订单等）
- 文件上传与下载
- 角色权限管理
- 支持多种 API 环境配置

## 项目结构

```
cap_frontend_2025/
├── public/                  # 静态资源目录（如 favicon、index.html）
├── src/                     # 主源码目录
│   ├── api/                 # 所有后端接口请求封装
│   ├── assets/              # 图片、样式等静态资源
│   ├── components/          # 公共组件（如弹窗、表格、分页等）
│   ├── entity/              # TypeScript 类型定义
│   ├── module-personal/     # 个人中心相关页面
│   ├── module-organization/ # 机构后台管理页面
│   ├── module-entering/     # 入驻相关页面
│   ├── router/              # 路由配置
│   ├── store/               # Vuex 状态管理
│   ├── utils/               # 工具函数与混入
│   ├── App.vue              # 根组件
│   └── main.ts              # 应用入口文件
├── ci/                      # 持续集成相关配置与脚本
├── docker/                  # Docker 部署相关文件（如 Dockerfile、compose 配置等）
├── static/                  # 额外静态资源（如第三方库、无需 Webpack 处理的文件）
├── .env                     # 环境变量配置
├── package.json             # 项目依赖与脚本
└── README.md                # 项目说明文档
```

### 目录说明

- **public/**  
  存放静态资源和入口 HTML 文件。

- **src/api/**  
  封装所有与后端交互的接口方法，便于统一管理和调用。

- **src/assets/**  
  项目用到的图片、全局样式等静态资源。

- **src/components/**  
  可复用的 Vue 组件，如弹窗、表格、分页等。

- **src/entity/**  
  TypeScript 接口和类型定义，规范数据结构。

- **src/module-personal/**  
  个人中心相关页面和逻辑，如我的课程、订单、作业、资料、个人信息等。

- **src/module-organization/**  
  机构后台管理页面，包括课程管理、教师管理、资料管理、订单管理等。

- **src/module-entering/**  
  入驻相关页面和组件，供新机构申请入驻使用。

- **src/router/**  
  路由配置文件，定义页面跳转规则。

- **src/store/**  
  Vuex 状态管理，存放全局状态和模块状态。

- **src/utils/**  
  工具函数、混入（如上传工具、弹窗混入等）。

- **src/views/**  
  主要页面视图文件，按业务模块划分。

- **ci/**  
  持续集成（CI）相关配置和脚本，如自动化测试、构建、部署流程等。

- **docker/**  
  Docker 部署相关文件，包含 Dockerfile、docker-compose.yml 等，便于容器化部署和环境一致性。

- **static/**  
  额外静态资源目录，通常用于存放无需 Webpack 处理的第三方库、字体文件等。

- **App.vue**  
  应用根组件。

- **main.ts**  
  应用入口文件，初始化 Vue 实例、注册插件等。

- **.env**  
  环境变量配置文件（如 API 地址、Token 等）。

## 自定义 `AUTHORIZATION TOKEN` 和 `API URL`

修改 `.env` 文件：

```env
VUE_APP_SERVER_API_URL=（此处填写在线Mock平台url）
VUE_APP_SERVER_AUTHORIZATION=（此处填写你的授权 token）
```

## 本地开发与运行

1. **安装 Node.js**  
   [Node.js 官网](https://nodejs.org/en/)

2. **安装 cnpm 包管理**
   ```sh
   npm install -g cnpm --registry=https://registry.npmmirror.com
   ```

3. **拉取依赖**
   ```sh
   cnpm install
   ```

4. **配置 API 地址**  
   修改 `.env` 文件中的 `VUE_APP_SERVER_API_URL`

5. **运行项目**
   ```sh
   npm run serve
   ```
   浏览器访问 [http://localhost:8080/](http://localhost:8080/)

## Docker 方式（可选）

### 拉取镜像

```sh
docker pull registry.cn-beijing.aliyuncs.com/ducafe/xczx2-portal-java-dev:latest
```

### 推送镜像

```sh
docker login --username=xxx registry.cn-beijing.aliyuncs.com
docker build -t registry.cn-beijing.aliyuncs.com/ducafe/xczx2-portal-java-dev:latest .
docker push registry.cn-beijing.aliyuncs.com/ducafe/xczx2-portal-java-dev:latest
```

---

如需详细开发文档或有其他疑问，请联系项目维护者或查阅源码注释。