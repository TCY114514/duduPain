🛠️ 项目：肚肚痛监测站（Scallion 协议）
项目描述：
一个基于 Serverless 架构的全栈应用程序，专门用于实时追踪我们的受试者 —— 大葱 (Scallion) 因大笑而导致的生理性腹痛。

技术栈 (Tech Stack)：

前端 (Frontend)：HTML5, CSS3 (移动端优先响应式设计), Vanilla JS。

数据库 (Database)：Supabase (PostgreSQL 驱动，已禁用 RLS 权限以实现最大程度的同步响应)。

托管 (Hosting)：Vercel (通过 GitHub 触发的持续部署 CD)。

数据可视化 (Analytics)：Chart.js，用于生成实时时间序列数据波动图。

地理定位 (Geolocation)：基于 ipapi.co 接口，实现受试者点击时的地理坐标捕捉。

用户故事 (User Story)：
当 大葱 (Scallion) 笑到腹部肌肉产生痉挛（即“肚肚痛”）时，他会触发 btn-main 交互元素。系统随后会抓取其当前地理位置，生成 UTC 时间戳，并将新纪录插入 Supabase 的 records 数据表中。前端每 60 秒自动轮询更新，实时呈现累计数值与最新的痛感分布曲线。
