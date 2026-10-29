# DSH Grill-me Safety v0.1

面向 DSH 的安全变更决策与可验证交付协议。

## v0.1 做什么

- 用户显式说“拷问我这个方案”时，按 frontier 一次一问。
- 识别安装插件、修改 profile、配置 MCP、接入凭证等高风险动作时，自动进入 Safety Mode。
- 在副作用动作前强制检查备份、隔离验证、一次一改、回滚和核心包污染风险。
- 执行后生成机器验收清单；必需项未通过不得标记完成。
- 收尾时输出 CHECKPOINT / 复盘所需的证据。

## 使用

当前项目把源码放在本目录的 `.dsh/skills/grill-me-safety/`，便于审阅和版本管理。实际启用时，复制到用户级 `<dshHome>/skills/grill-me-safety/`（通常是 `~/.dsh/skills/grill-me-safety/`），或放到 DSH 能扫描到的项目根 `.dsh/skills/`。

显式触发示例：

- “拷问我这个方案”
- “先别动手，把这事问清楚”
- “帮我压力测试一下这个需求”

自动 Safety 示例：

- “把这个插件装到 desktop profile”
- “帮我改 cordis.patch.yml”
- “接入一个 MCP 服务”

## 当前边界

这是 v0.1 的 Skill 协议版，不含 Cordis 状态机、工具级阻断和跨会话持久化。验证协议有效后，再实现 v0.2 插件版。

## 目录

- `SKILL.md`：主协议
- `references/safety-checklist.md`：安装前体检和强制暂停条件
- `references/acceptance.md`：机器验收协议
