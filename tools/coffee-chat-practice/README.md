# Coffee Chat 练习室

和 AI 扮演的各种性格的从业者练英文 coffee chat。对方会对你的语气、停顿和小动作作出反应，旁注实时解释，结束后给中文点评，练习记录自动保存。

- 在线版本（claude.ai 私有 Artifact）：https://claude.ai/artifact/BVHH7XJkGfKwhyfsUc3Be6
- 源文件：`coffee-chat-practice.html`

## 这个文件能做什么、不能做什么

页面依赖 claude.ai Artifact 提供的三项能力：

| 能力 | 用途 |
|---|---|
| `sample` | 调用 Claude 扮演对方、生成点评（用打开页面的人自己的 Claude 额度） |
| `db` | 保存练习记录（存在 claude.ai 上，每人私有） |
| `user` | 区分是谁在用，记录只给本人看 |

所以：

- **直接用浏览器打开这个 HTML 文件，AI 对话和记录都不能用**，只能看到界面、角色设定和问题库。
- 续费后，在 Claude Code 里把这个文件重新发布成 Artifact（发布时声明 `capabilities: {"sample": {}, "db": {}, "user": {}}`），或者直接继续用上面的在线链接。
- 练习记录不在这个仓库里，存在 claude.ai 上。

## 内容在哪里改

都在 `coffee-chat-practice.html` 的 `<script>` 开头：

- `PERSONAS`：角色（名字、职位、背景、开场白）
- `PROFILES`：固定角色的 LinkedIn 式资料（经历、教育、技能、一条动态）
- `ROLES`、`ORIGINS`、`STYLES`、`LIFE`、`CONCERNS`：随机生成器用的素材（职位、出身背景、说话风格、生活、最近的烦恼）
- `CHANNELS`：认识方式（线上 / 线下，约好的 / 当场偶遇），以及对应的联系消息模板
- `activityFor()`：生成和工作相关的 LinkedIn 动态
- `DIFFICULTY`：性格（很热心、友好、很忙、慢热、冷淡、话多爱跑题）
- `FOCUS`：练习重点
- `QBANK`：问题库
- `replyPrompt()`：对方怎么说话、怎么反应的规则
- `feedbackPrompt()`：点评标准

## 出处

聊天结构和部分原则改编自 [Coffee Chat Playbook](https://github.com/cwlin0131/coffee-chat-prep)（CW Lin，CC BY 4.0），已改为求职场景。
