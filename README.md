# text2sql_rl

用 GRPO 训练一个**多轮执行反馈**的 Text-to-SQL agent：模型生成 SQL → 在 SQLite 沙箱中执行 → 读取结果或报错 → 修正 → 提交，以执行结果匹配作为可验证奖励（RLVR）。

项目仍在进行中。当前已完成的是理论部分。

## 笔记

📐 **[Agentic RL 理论笔记](https://yuecao365.github.io/text2sql_rl/theory.html)** — 从策略梯度到多轮 agent 训练的系统整理

- Part 0 · 问题设定：token-level MDP 与 sequence-level bandit 两种视角
- Part 1 · 策略梯度基础：REINFORCE、baseline 定理、advantage、GAE
- Part 2 · 从 PPO 到 GRPO：重要性采样、信任域与 clip、group baseline、DAPO 四改、Dr. GRPO、KL 取舍
- Part 3 · 多轮 Agentic RL：observation masking 的严格推导、credit assignment、异常轨迹、多轮特有指标
- Part 4 · RLVR 与 reward 设计：验证器设计的三个维度、Goodhart 定律、reward hacking 的形态
- Part 5 · 训练基础设施：训推分离、权重同步、显存构成、LoRA in RL、序列长度预算
- Part 6 · 方法族的边界

笔记索引：<https://yuecao365.github.io/text2sql_rl/>

## 计划中的内容

- [ ] SQLite 沙箱工具环境（只读、超时、结果截断）
- [ ] 多轮驱动循环与轨迹 dump
- [ ] 快速验证器 + 官方评测套件的一致性校验
- [ ] 基于 verl 的 GRPO 训练配置
- [ ] Reward 设计与 credit assignment 的消融
- [ ] 训练曲线与评测结果

## 参考

主要依据 DeepSeekMath (GRPO)、DAPO、Dr. GRPO 三篇，以及 verl 的实现。完整文献列表见理论笔记末尾。
