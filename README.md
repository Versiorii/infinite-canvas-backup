# 灵感事务所 🎨

> 开心 AI — 无限画布，灵感无界

**灵感事务所** 是一款面向 AI 创作者的 Web 应用，提供灵感的无限画布来生成图像、视频和创意内容。前端基于 Next.js 16 + React 19 + TypeScript，后端为 Go 编译二进制。

---

## ✨ 功能特性

### 🎯 无限画布
- 自由拖拽、缩放、连接的节点式画布
- 支持多项目管理和节点编排
- 迷你地图导航 + 手势缩放控制
- 节点级图像/视频设置面板

### 🤖 AI 生成
- **图像生成** — 支持多种模型（GPT-Image-2、Grok、DeepSeek 等）
- **视频生成** — Grok Imagine Video 等模型
- **参考图** — 上传/拖入参考图片辅助生成
- **生图历史** — 完整的生成记录和云端恢复

### 👤 用户系统
- 注册/登录 + JWT 鉴权
- 算力点（Credits）管理系统
- 素材库管理
- 多级角色（用户/管理员）

### 🔧 后台管理
- 用户管理（搜索、编辑、封禁、算力调整）
- 生成日志监控（状态、模型分布、成功率）
- 提示词库管理（分类、同步、标签）
- 模型渠道管理（多 provider、权重、测试）
- 素材库管理
- 公告弹窗配置
- 算力扣费记录

---

## 🏗 项目结构

```
infinite-canvas/
├── server                  # Go 编译后端 (43MB 二进制)
├── web/                    # Next.js 16 前端
│   ├── package.json
│   ├── next.config.ts
│   ├── tsconfig.json
│   ├── postcss.config.mjs
│   └── src/
│       ├── app/
│       │   ├── (user)/          # 用户端页面
│       │   │   ├── canvas/      # 无限画布核心
│       │   │   ├── image/       # 图像生成 & 历史
│       │   │   ├── video/       # 视频生成
│       │   │   ├── assets/      # 素材库
│       │   │   └── prompts/     # 提示词库
│       │   ├── (admin)/         # 管理后台
│       │   │   └── admin/
│       │   │       ├── users/           # 用户管理
│       │   │       ├── generation-logs/ # 生成日志
│       │   │       ├── credit-logs/     # 算力记录
│       │   │       ├── prompts/         # 提示词管理
│       │   │       ├── assets/          # 素材管理
│       │   │       └── settings/        # 系统设置
│       │   └── api/              # API 代理路由
│       ├── components/           # 通用 UI 组件
│       ├── services/api/         # API 请求层
│       ├── stores/               # Zustand 状态管理
│       ├── hooks/                # 自定义 Hooks
│       ├── lib/                  # 工具库
│       ├── types/                # TypeScript 类型
│       └── constant/             # 常量
├── CHANGELOG.md
├── VERSION
└── README.md
```

---

## 🧰 技术栈

| 层 | 技术 |
|------|------|
| **前端框架** | Next.js 16 + React 19 |
| **语言** | TypeScript 5 |
| **UI 组件** | Ant Design 6 + Radix UI + shadcn |
| **状态管理** | Zustand 5 + TanStack React Query 5 |
| **动画** | Motion + Tailwind CSS 4 |
| **后端** | Go 编译二进制 |
| **数据库** | SQLite |
| **容器化** | Docker (ghcr.io) |

---

## 🚀 快速启动

```bash
# 启动后端
./server

# 启动前端（开发模式）
cd web
npm install  # 或 bun install
npm run dev  # 或 bun dev

# 构建前端
npm run build
npm start
```

环境变量：
- `API_BASE_URL` — 后端 API 地址（默认 `http://127.0.0.1:8080`）
- `JWT_SECRET` — JWT 签名密钥
- `ADMIN_PASSWORD` — 管理员初始密码

---

> ⚠️ **注意**：本仓库为生产环境备份，敏感信息（服务器 IP、密钥等）已清理。生产数据库和用户上传图片未包含在此仓库中。`server` 二进制文件可在 Release 中下载。
