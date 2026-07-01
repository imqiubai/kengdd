# 坑多多

坑多多是一个轻量的办公室厕所空位预测工具。项目使用单文件 `index.html`，可直接在浏览器运行，并通过 Supabase 共享历史观测数据和用户反馈。

## 在线访问

- 正式环境：https://imqiubai.github.io/kengdd/
- 测试环境：https://imqiubai.github.io/kengdd/?env=test

正式链接默认使用 `production` 数据；只有带 `?env=test` 的链接使用 `test` 数据并显示“测试模式”。

## 当前能力

- 基于历史观测数据预测厕所空位和等待时间
- 多人共享最近反馈，并用于修正当前预测
- Supabase 数据源与 localStorage 异常兜底
- 正式/测试数据标签隔离
- 移动端和 Web 端响应式布局
- 单文件、无构建工具、无 React/Vue 依赖

## 数据说明

- `toilet_feedback`：保存用户提交的预测反馈
- `toilet_observations`：保存真实历史观测数据

两张表均通过 `environment + toilet_id` 隔离数据。普通页面用户只能读取历史观测数据，不能新增、修改或删除观测记录。

## 本地预览

下载仓库后直接双击 `index.html`，或使用任意静态文件服务器打开。测试模式可在地址后添加 `?env=test`。

## 安全说明

前端只允许使用 Supabase Project URL 和 anon public key / publishable key。不要在 `index.html` 中加入 secret key、`service_role` key、数据库密码或其他高权限凭据。

## GitHub Pages

仓库使用 `main` 分支根目录发布 GitHub Pages。合并到 `main` 后，GitHub Pages 会自动重新部署，`index.html` 将作为首页加载。
