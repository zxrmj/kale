---
name: kale
description: >-
  Diagnose and recover from system or application lag when the user sends kale,
  卡了, 卡住了, or standalone meaningless keyboard mashing as a distress signal.
  当用户输入 kale、卡了、卡住了或独立的无意义乱敲字符时，将其识别为系统或应用卡顿求助，
  确定故障并执行恢复。Do not trigger on quoted text, code, identifiers, passwords,
  or a meaningful request about the vegetable kale.
---

# Kale / 卡了

Interpret a distress signal as: **“Something is stuck. Find the problem and help
it recover.” / “系统卡顿了，请确定问题并恢复。”** This is a troubleshooting request,
not evidence that the whole operating system has frozen.

## Recognize the signal

- Activate for `$kale`, a standalone `kale` (case-insensitive, surrounding
  whitespace or punctuation allowed), `卡了`, `卡住了`, or an explicit lag report.
- Activate for an otherwise contextless keyboard mash such as `asdfghjkl`,
  `。。。。。。`, or `啊啊啊啊啊` when it functions as a distress signal. Start with
  inspection; the signal alone does not establish a fault or authorize disruption.
- Interpret the complete user message and recent context. Quoted examples,
  logs, source code, random test data, unfamiliar languages, and meaningful
  requests retain their original intent. Do not treat arbitrary unfamiliar text
  as gibberish. Creating or discussing this skill is not invoking recovery.
- Do not ask what `kale` means. Briefly acknowledge the inferred intent in the
  user's language, then begin available diagnostics. For example:
  “我按‘卡顿了’处理，先定位卡住的环节，再尝试恢复。”

## Determine what is stuck

Use the current task and the most recent failing action to select the target.
Inspect the relevant application's state, job status, or available tools first.
Do not start with a broad scan of the user's files or all running applications.
If the affected application remains ambiguous, ask one narrow question while
continuing useful read-only checks; do not modify a guessed target.

Collect a small, timestamped baseline and distinguish:

| Suspected layer | Evidence to seek | First response |
| --- | --- | --- |
| Work still progressing | Advancing job progress, recent output, changing counters | Explain the current stage and observe bounded progress; leave the job running |
| Waiting for input | Permission prompt, login, modal, queued input | Surface the exact pending interaction; complete it only within existing authorization |
| UI or single app | Unresponsive UI with otherwise healthy services | Preserve editable work, inspect the app's own status, try its recovery/reconnect control |
| Local resources | Memory pressure, low free disk, sustained CPU/GPU or I/O contention | Identify the responsible workload and act only on a known in-scope cause |
| Tool or local service | Failed health check, stale connection, exited child process | Reconnect or restart only the affected disposable component when safe |
| Network or remote service | Timestamped timeouts, retry/reset events, service status | Separate reachability, authentication, and sustained request/stream health |

Use native tools appropriate to the detected OS. A cumulative CPU-time value
or a single busy sample does not prove a hang; compare two bounded observations
when needed. A successful connection or HTTP error response proves neither a
healthy authenticated request nor a stable stream. Long reasoning, large
contexts, rendering, and queued service work can all produce perceived delay.
Report uncertainty instead of inventing a single root cause.

Use bounded requests and small log tails. If a check hangs, cancel only that
diagnostic check and switch to an independent source of evidence. Do not create
an unbounded polling loop. During extended work, give concise progress updates.

## Recover the affected workflow

Act on the evidence; do not stop at generic troubleshooting suggestions when
tools can safely complete the repair. Reuse authorization already given in the
conversation. Choose the least disruptive operation that addresses the observed
failure, and change one thing at a time.

1. Preserve available unsaved work, the active job identifier, and the current
   task/checkpoint before any action that could interrupt them. If saving is not
   possible, state that limitation before proposing a disruptive action.
2. Try a targeted reconnect, recovery control, or retry of a failed read-only
   operation. Before retrying a write, submission, generation, or payment, query
   its status so a delayed success does not become a duplicate operation.
3. Restart an isolated agent-owned disposable helper if its failure is confirmed
   and no user work depends on it. Reload a page only after checking for unsaved
   input and active jobs. Do not stop shared services based on their process name.
4. If a configuration change is warranted, inspect the installed version and
   relevant current documentation, back up the specific file, make the smallest
   change, and keep a concrete rollback. Do not blindly reuse an old transport,
   proxy, model, or performance workaround. Persisted sessions may retain old
   settings; verify the configuration actually used by the affected session.
5. Before force-killing an app, restarting a shared service or the OS, interrupting
   user-owned compute jobs, or discarding unsaved data, explain the affected work
   and obtain specific authorization if it has not already been given. A bare
   distress signal is insufficient for those actions. Never disable security
   controls, delete credentials, or purge user data as a generic lag remedy.

Try a recovery action once and verify it. At most one additional attempt is
reasonable when fresh evidence supports it. If two distinct targeted remedies
fail, stop escalating automatically, preserve the evidence, and state the next
specific decision or access needed. Never automatically repeat paid work.

## Verify and resume

Re-run the smallest representative operation that previously stalled, checking
for duplicate side effects first. Confirm the affected UI, job, or request now
responds and, where relevant, continues making progress. A process restarting
or a health endpoint returning success alone does not establish recovery.

Report the observed problem (or unresolved hypothesis), the action taken, and
the concrete verification result. Distinguish **recovered**, **partially
recovered**, **still blocked**, and **no fault observed**. Never claim to have
inspected or fixed a system when tools cannot access it; request only the missing
access or symptom information needed to continue.

Resume the user's interrupted task when recovery is verified and its existing
authorization still applies. Preserve explicit stop instructions. Do not replay
a mutation or billable job just to resume progress.

Keep diagnostic evidence local by default. Redact tokens, cookies, private URLs,
personal file paths, and unrelated content from any report intended for sharing.
