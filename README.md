# Book Circle 书圈

一个完整的学习交流社区平台，包含后端服务、Web 前端和微信小程序三个子项目。

## 项目结构

```
book-circle/
├── book-circle-backend/     # Spring Boot 后端服务
├── book-circle-frontend/    # Vue 3 Web 前端
└── book-circle-miniapp/     # 微信小程序
```

## 技术栈

### 后端 (book-circle-backend)

| 技术 | 说明 |
|------|------|
| Spring Boot 3.x | Web 框架 |
| Maven | 项目构建 |
| MyBatis | ORM 框架 |
| Redis | 缓存与在线用户 |
| JWT | 用户认证 |
| WebSocket | 实时通信 |
| 阿里云 OSS | 文件上传 |

### 前端 (book-circle-frontend)

| 技术 | 说明 |
|------|------|
| Vue 3 | 渐进式框架 |
| Vite | 构建工具 |
| Element Plus | UI 组件库 |
| Pinia | 状态管理 |
| Vue Router | 路由管理 |
| Axios | HTTP 客户端 |
| STOMP.js | WebSocket 客户端 |

### 小程序 (book-circle-miniapp)

| 技术 | 说明 |
|------|------|
| uni-app | 跨平台框架 |
| Vite | 构建工具 |
| Vue 3 | 框架 |

## 功能模块

### 核心功能
- **用户系统**: 注册、登录、用户中心、个人资料编辑
- **书圈管理**: 创建书圈、加入书圈、书圈详情
- **图书管理**: 图书列表、图书详情、图书推荐
- **话题讨论**: 发布话题、评论、回复
- **私信功能**: 用户间一对一聊天
- **推荐系统**: 个性化图书推荐
- **管理员后台**: 用户管理、内容审核、公告发布

### 后端 API

| 模块 | 路径 | 说明 |
|------|------|------|
| 认证 | `/api/auth/*` | 登录、注册 |
| 用户 | `/api/user/*` | 用户信息管理 |
| 书圈 | `/api/circle/*` | 书圈 CRUD |
| 图书 | `/api/book/*` | 图书管理 |
| 话题 | `/api/topic/*` | 话题讨论 |
| 评论 | `/api/comment/*` | 评论功能 |
| 私信 | `/api/message/*` | 私信聊天 |
| 推荐 | `/api/recommendation/*` | 推荐服务 |
| 上传 | `/api/upload/*` | 文件上传 |
| 在线状态 | `/api/online/*` | 在线用户管理 |

## 快速开始

### 环境要求

- JDK 17+
- Maven 3.8+
- Node.js 18+
- Redis 6+
- MySQL 8+ (如需)

### 后端启动

```bash
cd book-circle-backend

# 安装依赖
mvn clean install

# 运行项目
mvn spring-boot:run
```

配置文件位于 `src/main/resources/application.yml`

### 前端启动

```bash
cd book-circle-frontend

# 安装依赖
npm install

# 启动���发服务器
npm run dev
```

### 小程序启动

```bash
cd book-circle-miniapp

# 安装依赖
npm install

# 运行微信小程序
npm run dev:mp-weixin

# 使用微信开发者工具打开 dist/build/mp-weixin 目录
```

## 目录结构

### 后端

```
book-circle-backend/
├── src/main/java/top/qhgong/bookcirclebackend/
│   ├── controller/     # 控制器层
│   ├── service/       # 服务层
│   ├── mapper/        # 数据访问层
│   ├── entity/        # 实体类
│   ├── dto/           # 数据传输对象
│   ├── config/        # 配置类
│   └── util/          # 工具类
├── src/main/resources/
│   ├── application.yml
│   └── logback-spring.xml
├── pom.xml
└── logs/              # 日志目录
```

### 前端

```
book-circle-frontend/
├── src/
│   ├── views/         # 页面组件
│   ├── components/    # 公共组件
│   ├── router/        # 路由配置
│   ├── store/         # 状态管理
│   ├── utils/         # 工具函数
│   └── style.css      # 全局样式
├── vite.config.js
├── package.json
└── index.html
```

### 小程序

```
book-circle-miniapp/
├── src/
│   ├── pages/         # 页面
│   │   ├── index/     # 首页
│   │   ├── login/     # 登录
│   │   ├── register/  # 注册
│   │   ├── books/     # 图书
│   │   ├── book-circles/  # 书圈
│   │   ├── book-detail/   # 图书详情
│   │   ├── circle-detail/ # 书圈详情
│   │   ├── recommendations/ # 推荐
│   │   ├── messages/  # 消息
│   │   ├── chat/      # 聊天
│   │   ├── user-center/  # 用户中心
│   │   ├── topic-detail/ # 话题详情
│   │   └── profile-edit/  # 编辑资料
│   ├── static/        # 静态资源
│   ├── utils/         # 工具函数
│   ├── App.vue
│   ├── main.js
│   └── manifest.json
├── vite.config.js
├── package.json
└── dist/              # 构建输出
```

## 数据库表

| 表名 | 说明 |
|------|------|
| user | 用户信息 |
| book | 图书信息 |
| book_circle | 书圈 |
| topic | 话题 |
| comment | 评论 |
| tag | 标签 |
| recommendation | 推荐记录 |
| circle_join_request | 入圈申请 |
| audit_log | 审计日志 |

## 注意事项

1. **子项目 Git 独立性**: 本仓库作为整体展示，三个子项目各自保留独立的 Git 仓库与 Gitee 远程关联
2. **敏感信息**: 请勿提交包含敏感信息（密码、密钥等）的配置文件到仓库
3. **环境变量**: 后端和前端可能需要配置环境变量或 `.env` 文件

## License

MIT