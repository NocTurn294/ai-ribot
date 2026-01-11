# ai-ribot

“老板，那个 AI 客服又在教客户怎么修电脑了，虽然我们是卖水果的。”

这是一个基于 SpringAI + Vue  构建的智能客服 Agent。它不只是一个复读机，而是一个拥有“记忆”和“逻辑”的实习管理辅助专家（或者你可以自定义它的业务背景）。

🌟 核心技能 (Features)
🧠 记忆力超群：底层挂载 Cassandra 分布式数据库，海量聊天日志随存随取，它甚至记得你三年前问过的问题。

⚖️ 逻辑严密：通过 PostgreSQL 管理核心业务逻辑，确保每一笔申请和审批都稳如泰山。

🐳 容器化生存：全线支持 Docker 部署。D 盘太大想搬家？没问题，它支持丝滑迁移。

🛠️ 开发者友好：我们已经帮你踩过了 IDEA 驱动下载失败、端口映射消失、C 盘爆满等 99 个坑。

🏗️ 技术架构 (Architecture)
前端：Vue 3 + Element Plus (响应式设计，手机也能调戏 Agent)。

后端：SpringBoot 3.x (处理那些让机器人头疼的业务逻辑)。

存储层：

PostgreSQL: 负责“正经”数据（用户、角色、权限）。

Cassandra: 负责“不正经”数据（海量对话、系统日志）。

🚀 快速启动 (Quick Start)
如果你想在本地跑起来，请确保你不是在用 C 盘硬抗：

克隆仓库

Bash

git clone https://github.com/你的用户名/项目名.git
启动环境 (Docker)

Bash

docker-compose up -d
注：如果驱动下载失败，请参考本项目的 docs/troubleshooting.md（手动挂载 JDBC 驱动指南）。

连接数据库 在 IDEA 中打开控制台，别忘了先创建你的 Keyspace：

SQL

CREATE KEYSPACE IF NOT EXISTS agent_db 
WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
🛠️ 常见问题 (FAQ)
Q: 为什么我的 IDEA 连不上数据库？ A: 因为网络在和你捉迷藏。请手动下载 .jar 驱动并像投喂零食一样喂给 IDEA。

Q: C 盘红了怎么办？ A: 别慌，执行 wsl --export 大法，把数据搬到 D 盘去。

🤝 贡献 (Contributing)
如果你发现了 Bug，或者想教这个 Agent 学点新方言，欢迎提 PR！
