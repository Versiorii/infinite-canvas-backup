# Infinite Canvas (Kaixin AI)

开心 AI — 灵感无限画布

基于 Next.js 的前端 + Go 后端，提供 AI 图像/视频生成画布工具。

## 项目结构

```
├── server          # Go 编译后端 (43MB)
├── web/            # Next.js 前端
│   ├── src/
│   │   ├── app/    # 页面路由
│   │   ├── components/  # UI 组件
│   │   ├── services/    # API 服务
│   │   ├── stores/      # 状态管理
│   │   ├── hooks/       # 自定义 Hooks
│   │   ├── lib/         # 工具库
│   │   ├── types/       # 类型定义
│   │   └── constant/    # 常量
│   └── public/     # 静态资源
├── CHANGELOG.md
├── VERSION
└── .gitignore
```

> 注意：敏感信息已清理（服务器 IP 等）。
> 生产数据库 (`infinite-canvas.db`) 和用户上传图片未包含在此仓库中。
