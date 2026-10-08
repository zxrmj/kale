# Kale / 卡了

**English:** An agent skill that interprets `kale`, Chinese lag complaints, or
standalone meaningless keyboard mashing as a request to diagnose a stuck system
or application, carry out a targeted recovery, and verify responsiveness.

**中文：** 当你输入 `kale`、`卡了`、`卡住了` 或独立的无意义乱敲字符时，
将其理解为“系统卡顿，请帮我确定问题并恢复”，随后定位故障、执行针对性恢复并验证结果。

## Examples / 使用示例

```text
kale
卡了
asdfghjkl
。。。。。。
$kale 浏览器一直转圈，帮我恢复刚才的任务
```

Context matters: quoted text, code, random test data, unfamiliar languages, and
questions about the vegetable are not distress signals.

会结合上下文判断；引用内容、代码、随机测试数据、不熟悉的语言以及羽衣甘蓝相关问题不会被当作卡顿求助。

## What happens / 工作流程

1. Identify the affected app or workflow and inspect current evidence.
   确定受影响的应用或任务，检查实际状态与故障证据。
2. Distinguish ongoing work, pending input, UI hangs, resource pressure, and
   connection failures. 区分正常处理、等待输入、界面卡死、资源压力与连接故障。
3. Perform an evidence-based, minimally disruptive recovery.
   根据证据执行影响范围最小的恢复，保留未保存内容和进行中的任务。
4. Verify the previously failing operation and resume authorized work.
   验证原先卡住的操作，再继续已获授权的任务。

The skill does not treat a keyboard mash as blanket permission to kill apps,
reboot, erase data, or repeat paid jobs. It asks only when the next action needs
missing information or specific authorization. If the agent lacks system access,
it reports that limitation instead of claiming a repair.

乱敲字符不代表允许强杀程序、重启电脑、删除数据或重复付费任务。只有缺少必要信息或具体操作授权时才询问；
无法访问系统时会明确说明，不会声称已经修复。

## Install for Codex / 安装到 Codex

Clone this repository as a `kale` folder inside your Codex skills directory.
The default directory is `~/.codex/skills`; if `CODEX_HOME` is configured, use
its `skills` subdirectory instead. Do not overwrite an existing `kale` folder.

将仓库克隆到 Codex 技能目录下的 `kale` 文件夹。默认目录为 `~/.codex/skills`；
若设置了 `CODEX_HOME`，请使用该目录下的 `skills`。不要覆盖已有的 `kale` 文件夹。

Default-location examples / 默认路径示例：

PowerShell:

```powershell
git clone https://github.com/zxrmj/kale.git "$env:USERPROFILE/.codex/skills/kale"
```

macOS / Linux:

```sh
git clone https://github.com/zxrmj/kale.git ~/.codex/skills/kale
```

Use a new chat if the current one has not discovered the skill. Explicitly invoke
`$kale`, or send a distress signal and let the host select it automatically.
Implicit selection depends on the host; this is an instruction skill, not a
background monitor or a guaranteed keyword interception service.

若当前对话未发现技能，请在新对话中使用。可显式输入 `$kale`，也可输入卡顿信号由宿主自动选择。
自动触发取决于宿主；这是指令型技能，并非后台监控程序或保证拦截所有关键词的服务。

## Files and scope / 文件与适用范围

- [SKILL.md](SKILL.md): bilingual discovery description and the recovery workflow.
  中英文技能描述及恢复流程。
- [agents/openai.yaml](agents/openai.yaml): Codex UI metadata and implicit invocation.
  Codex 界面信息与自动调用设置。

No executable payload, credentials, private logs, or machine-specific settings
are included. Available inspection and recovery actions depend on the agent's
tools, operating system, and permissions. The package can be structurally
validated without demonstrating a real system recovery.

不包含可执行载荷、凭据、私人日志或本机专属配置。实际可执行的诊断与恢复取决于代理工具、操作系统及权限。
通过技能格式校验不等于已证明真实系统故障能够恢复。
