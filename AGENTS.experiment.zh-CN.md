# AGENTS.experiment.zh-CN.md

本文件适用于：

* 模型复现
* 训练实验
* Benchmark
* Ablation
* 超参数搜索
* 科研项目

本文件补充 `AGENTS.md`。

---

# 核心原则

不要为了执行便利性而损害结论可信度。

任何正式结论都应尽量满足：

* 可解释
* 可追溯
* 可审查
* 可复现

当证据不足、配置偏离、数据边界不清或实验记录缺失时，不得将结果写成正式结论。

---

## 1. 保持实验定义完整

未经明确批准，不得修改：

* 数据集
* Train / Validation / Test Split
* Metric 或评估协议
* Loss 或优化目标
* 模型结构
* Checkpoint 或 Pretrained Weights
* 训练预算
* Model Selection Rule
* Random Seed

上述任意修改都意味着新的实验。

任何偏离都必须明确记录。

---

## 2. 忠实复现优先于跑通

不得将以下内容描述为 Faithful Reproduction：

* Simplified Version
* Partial Implementation
* Toy Version
* Debug Version
* Smoke Test
* 使用 Mock 或 Dummy 数据的实现

复现论文或研究方法前，应建立实现 Mapping，并明确：

* 已实现部分
* 未实现部分
* 不确定部分
* 与论文或计划的偏离

不确定内容必须标记为 Uncertainty。

---

## 3. 实验必须有决策价值

每个实验都应回答一个明确假设，或支持一个明确决策。

实验前应说明：

* 要验证什么假设
* 支持什么决策
* 预期获得什么信息
* 不同结果对应什么行动

避免：

* 为了填表而跑实验
* 为了补齐 Ablation Matrix 而跑实验
* 没有新假设时持续扫超参
* 在低信息增益方向持续优化

如果连续实验无法改变决策，应重新审视方向。

---

## 4. 区分实验层级

明确区分：

### Smoke Test

确认代码能够运行。

### Sanity Check

确认数据流、Shape、Loss、Gradient 和 Metric 正常。

### Formal Experiment

用于结论、比较、复现判断或项目决策。

Smoke Test 与 Sanity Check 不得作为正式证据。

---

## 5. 保护评估边界

禁止使用 Test Set 进行：

* 调参
* Early Stopping
* Checkpoint Selection
* Seed Selection
* Model Selection
* 预处理统计量构建

Train、Validation、Test 必须保持明确边界。

任何数据泄漏都会削弱结论可信度。

---

## 6. 保持实验资产可追溯

实验名称、配置、日志、Checkpoint、输出目录和结果文件应反映实验含义。

记录：

* 代码版本
* 配置
* 数据版本
* Split
* Seed
* 命令
* 日志
* 指标
* Checkpoint
* 输出目录

记录外部资产来源：

* Pretrained Model
* Checkpoint
* Cache
* Processed Dataset
* Third-party Implementation

不要覆盖已有正式实验结果，除非明确要求。

失败实验也应记录。

---

## 7. 错误必须暴露

不要通过以下方式掩盖问题：

* Mock Data
* Dummy Module
* Silent Fallback
* Broad Exception Handling
* 隐式随机初始化
* 跳过失败样本
* 未解释的 NaN 修复

如果使用 Fallback，应说明：

* 发生了什么
* 为什么允许
* 行为发生了什么变化
* 结果是否仍然有效

实验失败也是结果的一部分。

---

## 8. 证据与结论必须绑定

不要仅写：

* 复现成功
* 效果提升
* 模型有效
* 结果接近论文

应明确说明：

* 哪个实验
* 哪个配置
* 哪个数据版本
* 哪个 Seed
* 哪个 Metric
* 哪个 Baseline
* 是否属于 Formal Experiment
* 存在哪些 Caveat 或 Deviation

不要混淆：

* Observation
* Measurement
* Inference
* Hypothesis
* Recommendation

证据不足时，应明确说明证据不足。

---

## 9. Plan-vs-Actual 审查

任务结束时应说明：

* 原计划是什么
* 实际完成了什么
* 哪些地方发生偏离
* 获得了哪些证据
* 还有哪些不确定性
* 结果是否足以支持结论

未完成原计划时，不得描述为任务完成。
