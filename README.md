# Research-Agent-Governance
面向 AI Agent 的轻量级治理规范。

适用于：

* 软件开发
* 科研项目
* 模型复现
* 训练实验

目标是减少：

* 凭空执行
* 需求误解
* 静默偏离
* 伪复现
* 数据泄漏
* 不可追溯实验
* 缺乏证据的结论

---

# 文件说明

## AGENTS.md

英文版通用规范。

定义 Agent 的默认行为约束，包括：

* 先理解上下文再行动
* 关键歧义先确认
* 严格控制任务范围
* 保持修改可审查
* 错误必须暴露
* 使用已有概念
* 证据优先于结论
* 如实汇报结果

适用于所有项目。

---

## AGENTS.zh-CN.md

`AGENTS.md` 的中文版。

与英文版内容等价。

---

## AGENTS.experiment.md

英文版实验规范。

用于：

* 模型复现
* 训练实验
* 科研项目

该文件主要关注：

* 实验定义完整性
* 忠实复现
* 决策价值
* 实验层级
* 数据边界
* 实验资产管理
* 错误暴露
* 证据纪律
* Plan-vs-Actual 审查

---

## AGENTS.experiment.zh-CN.md

`AGENTS.experiment.md` 的中文版。

与英文版内容等价。


---

# 如何使用（Codex）

## 需要用到实验规范（项目级规范）

将

```text
AGENTS.experiment.md
```

改名为

```text
AGENTS.md
```

放置于仓库根目录：

```text
repo/
├── AGENTS.md
└── ...
```
---

## 需要用到全局规范

将

```text
AGENTS.md
```

放置于codex安装路径：

```text
home/user/workspace/.codex/
├── AGENTS.md
└── ...
```
---

即可在codex启动时自动加载，两种规范不冲突。

# 设计原则


> 让 Agent “正确地做事”，让最终结论更值得信任。
