# ai-journey
ai应用开发学习
每日任务卡 · 168 天逐日版（v2.0）
制定日：2026-11-02 ｜ 起点：2026-11-02（周一，D01） ｜ 终点：2027-04-18（周日，D168）
目标：24 周内从 Java 后端转型到 AI 应用 / Agent 开发工程师，达到能面试、能上岗、能写简历的水准。
📌 这份文件是"每天干什么"的唯一权威。CURRICULUM.md 是总览和规则，本文件是逐日执行清单。
📌 配套：STAGE-PROJECTS.md（8 个阶段项目的体量标准）、FRONTIER.md（技术基线）、progress.md（打卡）。
零、使用说明（花 2 分钟看完，之后不用再翻）
每天的固定节奏
时段
时长
干什么
硬要求
早间 15 分钟
15 min
读当天的"输入"材料
只读当天那一份，不许囤教程
白天零碎
30 min
通勤/午休：回看昨天的笔记、跑一次昨天的代码
不学新东西，只保温
晚间主攻
90 min
敲代码，做当天的"交付物"
必须产出文件，光看不写不算
收尾 20 分钟
20 min
写笔记（3-5 条要点 + 1 个坑）
这就是你的面试素材库
打卡 5 分钟
5 min
更新 progress.md
断更 2 天 = 计划死亡
周末（D6 / D7）节奏不同：4h 项目攻坚 + 1.5h 复盘自测 + 0.5h 前沿扫描。
每天任务的读法
每天一张卡，四行信息：
**输入**（读什么）→ **敲代码**（造什么文件）→ **产出**（交什么文件）→ **验收**（怎么算过了）
- 验收标准是你自己的判卷标准，不是给别人看的。做完了自己对照一遍，不过就补，别糊弄。
- 每天卡片末尾的 「15 分钟保底」 是给你累的时候用的。再累也要做保底那一条——保住连续性比做完更重要。
- 每天有一行 「面试点」，是当天这块知识在面试里怎么问。不用背，但要能答。答不上来就标记下来，周日补。
三档投入 → 怎么换算
档位
工作日
周末
实际完成日
怎么用这份计划
🔴 冲刺
4.5h
8h
17 周
每天做 D1-D5 + 周末，砍掉 W14 缓冲周和"复习巩固日"
🟡 标准（本计划基准）
2.5h
6h
24 周 = 168 天
照着走，一 day 不落
🟢 稳健
1.5h
4h
36 周
每周做 5 天（跳过 D6 或 D7），D1-D5 拖到下周一
铁律：D1-D5（工作日核心）任何档位都不能跳过。周末的 D6/D7 在稳健档可以只做 D6。
每天的"最小胜利"文化
一天 2.5 小时，90 分钟在主攻。这 90 分钟会被打断、会走神、会因为一个 bug 卡半小时。
所以每张卡都写了「15 分钟保底」——它不是凑数，它是防止计划死亡的安全绳。
一、168 天全景表
阶段
天数
日期
主题
阶段项目交付
S1 地基
D01-D14
11-02 ~ 11-15
LLM 心智模型 + Python 突击
SP0 工单分诊服务
S2 RAG
D15-D35
11-16 ~ 12-06
文档处理 → 混合检索 → 评估闭环
SP1 知识中枢
S3 Agent 内核
D36-D56
12-07 ~ 12-27
手写 ReAct → LangGraph → 记忆规划
SP2 自主 Agent
S4 MCP / Skills
D57-D70
12-28 ~ 01-10
协议精读 → 写 Server → 安全加固
SP3 开源 MCP Server
S5 Java 工程化
D71-D91
01-11 ~ 01-31
Spring AI 2.0.2 → LangChain4j 1.23 → Java 版
SP4 Java 生产版
🧧 缓冲
D92-D98
02-01 ~ 02-07
春节：不掉链子就是胜利
—
S6 生产化
D99-D112
02-08 ~ 02-21
可观测 → 评估工程化 → 安全稳定
SP5 企业级平台
S7 Data Agent
D113-D126
02-22 ~ 03-07
NL2SQL → 语义层 → 产品化
SP6 NL2SQL Agent
S8 作品集
D127-D140
03-08 ~ 03-21
README → 视频 → 博客 → 简历 → 开始投递
SP7 作品集
S9 面试冲刺
D141-D154
03-22 ~ 04-04
八股 → 手撕 → 系统设计 → 模拟面
面试手册
S10 投递冲刺
D155-D168
04-05 ~ 04-18
密集投递 → 复盘补短板 → offer
—
S1 · 地基（D01-D14 · 11-02 ~ 11-15）
这两个周的目标：让你从"听说过 LLM"变成"能独立写出一个带流式、带结构化输出、带重试的 LLM 服务"。
产出物：bootcamp/ 里的一堆可运行脚本 + 一个能 docker compose up 的服务。
⚠️ 如果你已经跑过 bootcamp/d01_hello.py 和 d02_structured.py，D01-D03 可以压缩成半天，省出的时间往后挪。
W1 · LLM 心智模型 + 第一次调用（D01-D07 · 11-02 ~ 11-08）
D001 · 11-02 周一 · 环境验收 + 搞懂 LLM 在干什么
输入（早间 15 分钟）
- 3Blue1Brown《Attention/Transformer 可视化》前 20 分钟（YouTube/B 站）
- 读 Anthropic《Building effective agents》第 1-2 节（官方 engineering blog，重点是 "workflow vs agent" 的区分）
敲代码（90 分钟）→ bootcamp/d01_llm_intro.py
- 用 numpy 手写 softmax + 缩放点积注意力（不 import 任何框架）
- 输入 3 个词，打印注意力权重矩阵，打印 "模型在第 3 个词上最关注谁"
- 再手写一个"贪心 next-token 预测"的迷你版：给一句 "今天天气很"，输出最高概率的下一个词（可用一个假词表模拟）
产出
- notes/d01.md：5 条笔记。必须包含这 3 条：① LLM 是概率机器不是数据库 ② 为什么会有幻觉（下一个 token 的贪心/采样本质）③ attention 在算什么（一句话）
验收
[ ] python bootcamp/d01_llm_intro.py 能跑，输出注意力矩阵
[ ] 能不看笔记，用 90 秒讲清 "token 序列 → 预测下一个 token → 循环"
[ ] 知道 context window 是什么，满了会怎样
面试点：为什么 LLM 会幻觉？temperature 调高会怎样？context window 满了怎么办？
15 分钟保底：只读 3Blue1Brown 20 分钟，把 notes/d01.md 的 5 条笔记写出来（不写代码）。
D002 · 11-03 周二 · 算清 token 和钱
输入（早间 15 分钟）
- 读一遍目标模型的 token 计价页（DeepSeek 或百炼的定价文档），把单价抄进笔记
敲代码（90 分钟）→ bootcamp/d02_token_cost.py
- 用 tiktoken（或目标模型的 tokenizer）分别对：① 一段中文 ② 一段英文 ③ 一段 Java 代码 ④ 一段 JSON，算 token 数
- 打印一个对比表：同样的意思，中英文 token 数差几倍
- 写一个函数 estimate_cost(prompt, completion, model)，参数化单价
- 算三个真实场景：一天 1000 次调用、平均 2000 token 输入 + 500 token 输出，一个月多少钱
产出
- notes/d02.md：3 条笔记 + 一张成本表。必须回答："中文是不是比英文贵？差多少？"
验收
[ ] 脚本能跑，输出对比表
[ ] 算出你那个场景的月度成本，数字记在笔记里
[ ] 知道为什么"本地调试用 4B 小模型 + Ollama，不烧钱调 bug"
面试点：怎么给一个 LLM 功能估成本？token 成本和功能复杂度是什么关系？
15 分钟保底：只写 estimate_cost 函数和一张表，tokenizer 那部分明天补。
D003 · 11-04 周三 · 第一次 API 调用（流式 / 多轮 / 参数）
输入（早间 15 分钟）
- 目标模型 API 文档的"对话补全"和"流式"两节（只读这两节）
敲代码（90 分钟）→ bootcamp/d03_api_call.py
- 三段式写在一个文件里，用 --mode nonstream|stream|multi 切换：
  a. 非流式：一次调用拿完整响应
  b. 流式（SSE）：逐字/逐块打印，体验"打字机效果"
  c. 多轮：自己维护 messages 数组，连续问 3 轮，第 3 轮问"我刚才说了什么"
- 调 temperature（0 / 0.7 / 1.5 各跑一次同一个 prompt）和 max_tokens，把 3 个输出贴进笔记做对比
- 加上超时和重试（指数退避，最多 3 次）
产出
- notes/d03.md：3 组输出对比 + 2 条笔记（"temperature 到底改变了什么" / "多轮对话是谁在维护状态"）
验收
[ ] 三个 mode 都能跑
[ ] 亲手看到 temperature=1.5 的输出明显更散
[ ] 知道"messages 数组由客户端维护"这件事
面试点：API 是无状态的，那多轮对话是怎么实现的？流式有什么实际价值（除了好看）？
15 分钟保底：只做非流式 + 一组 temperature 对比。
D004 · 11-05 周四 · 结构化输出（让模型听话）
输入（早间 15 分钟）
- Pydantic v2 官方文档的 "Models / Validators / JSON Schema" 三节
敲代码（90 分钟）→ bootcamp/d04_structured.py
- 定义 Pydantic 模型 ResumeInfo{name, years_of_experience: int, skills: list[str], projects: list[str]}
- 三种方式对比：① 直接要 JSON ② JSON mode ③ Pydantic + 校验
- 写失败重试：校验不过就把错误信息喂回模型，最多重试 2 次
- 造 3 个"脏输入"（缺字段、类型不对、额外废话），看你的代码怎么处理
- 打印 model_json_schema()，看看生成的 JSON Schema 长什么样
产出
- notes/d04.md：3 条笔记（为什么不能只靠 prompt / JSON mode 和 schema 校验的区别 / 校验失败该重试还是该报错）
验收
[ ] 脏输入全部被拦住，没有脏数据漏出去
[ ] 重试逻辑生效（故意让它第一次输出坏的）
[ ] 能解释 model_json_schema() 有什么用
面试点：怎么保证 LLM 输出能被程序消费？校验失败怎么办？
15 分钟保底：定义 Pydantic 模型 + 三种方式各跑一次。
D005 · 11-06 周五 · Prompt 工程 + 建立测试用例思维
输入（早间 15 分钟）
- 读 Anthropic 那篇 prompt engineering 指南（或 OpenAI 的官方 cookbook 对应章节）
敲代码（90 分钟）→ bootcamp/d05_prompt_eval.py
- 把 D04 的简历解析器改造成可测试的：run_prompt(prompt_version, text) -> dict
- 写 20 条测试用例（10 正常 + 5 边界 + 5 恶意），存成 bootcamp/data/resume_cases.jsonl
- 跑一遍，统计通过率（脚本自己输出"通过 12/20"这种）
- 然后优化 prompt（加 few-shot 示例、明确边界、约束输出），再跑一遍
产出
- notes/d05.md：记录 prompt v1 通过 12/20 → v2 通过 19/20 这个过程和改了什么
- bootcamp/data/resume_cases.jsonl：20 条用例（后面所有项目都用这个格式）
验收
[ ] 有真实的"改前/改后"两个数字
[ ] 20 条用例里至少 3 条是故意刁难的
[ ] 这个"通过率从 X 提到 Y"的数字，这就是你面试里最值钱的一句话
面试点：你怎么知道 prompt 改动是有效的？怎么防止改好一个坏三个？
15 分钟保底：只写 20 条测试用例（不写代码），这是最重要的资产。
D006 · 11-07 周六 · 周末攻坚：把脚本变成服务
- 输入：无新材料——直接动手，用到时再查文档（今天以产出为主）
今日主题：从"能跑的脚本"到"能用的服务"
敲代码（4h）→ bootcamp/llm-service/
- 用 FastAPI 包一层：POST /parse（解析简历）、GET /health
- 加 SSE 流式端点 POST /parse/stream
- 加统一错误处理：参数校验失败 → 400；模型超时 → 504；上游 429 → 503 + Retry-After
- 加 结构化日志（每次请求记：trace_id / 耗时 / token 数 / 是否重试）
- 写 Dockerfile + docker-compose.yml（app + 一个 mock 上游）
产出
- bootcamp/llm-service/README.md：架构图（ASCII 就行）+ 怎么跑 + 3 个 curl 示例
验收
[ ] docker compose up 之后 curl 能通
[ ] 故意让上游超时，返回 504 而不是 500 堆栈
[ ] 日志里有 trace_id 能串起一次请求
面试点：FastAPI 为什么快？async 里调同步库会怎样？超时怎么分级？
15 分钟保底：只写 Dockerfile 和 docker-compose.yml。
D007 · 11-08 周日 · 周复盘 + 知识固化
- 输入：无新材料——读本周自己的笔记 + 前一天的产出代码（复习优先于学新东西）
时间分配：项目攻坚 2h + 复盘自测 2h + 前沿扫描 0.5h + 休息 1.5h
复盘自测（2h）
1. 跑一遍本周所有脚本，确认都能跑（python bootcamp/d0*.py）
2. 不看笔记，回答本周 5 个面试点，写在纸上 → 答不上的用红笔标
3. 把 notes/d01.md ~ d05.md 合并成 notes/W1_知识地图.md（一页纸，30 行以内）
4. 填 progress.md 的本周自检（6 条）
敲代码（2h 项目攻坚，详见下方「项目攻坚」段）
项目攻坚（2h）
- 给 llm-service 补一个 pytest 测试（至少 3 个用例：正常 / 脏输入 / 超时）
- 把 20 条测试用例接进 CI（GitHub Actions，.github/workflows/test.yml）
前沿扫描（0.5h）
- 扫 FRONTIER.md 第二节的版本表，看看这周有没有变化
- 查 1 个 AI 工程周刊，只找"被正式命名的新实践"（比如 context engineering 这种）
- 有变化 → 追加到 FRONTIER.md 第五节；没变化 → 写"无变化"
验收
[ ] pytest 能跑，CI 配置在仓库里
[ ] W1 知识地图写完（一页纸）
[ ] 5 个面试点答不上的，记进欠账区
面试点：本周 5 个面试点（见上方「复盘自测」第 2 条）——不看的题就是你的面试事故
15 分钟保底：只做"5 个面试点自测"并标红。
W2 · Python 突击（D08-D14 · 11-09 ~ 11-15）
目标：达到"能读懂、能改、能自己写 500 行服务"的程度。不求精通 Python，求能干活。
⚠️ 这周会难受，因为 Python 没有 Spring 那套脚手架。熬过去，后面全是顺风。
D008 · 11-09 周一 · 类型系统 + Pydantic v2
输入：Python 官方 typing 文档 + Pydantic v2 "Strict Mode / Validators" 节
敲代码（90 分钟）→ bootcamp/d08_typing_pydantic.py
- 类型注解：list[str] / Optional[X] / TypedDict / Literal / Annotated
- dataclass vs BaseModel 的区别（各写一个同样的类，对比）
- Pydantic v2：Field 约束、field_validator、model_validator（跨字段）、model_config
- Strict 模式：model_config = ConfigDict(strict=True)，看它怎么拦住 "25" 这种字符串年龄
产出：notes/d08.md —— 3 条笔记 + 一张"Java 语法 → Python 语法"对照表（这是你后面每天都要用的）
验收：
[ ] 写出 2 个自定义 validator，其中 1 个是跨字段的
[ ] strict 模式成功拦住一次类型转换
[ ] 对照表里有 ≥ 15 条 Java→Python 映射
面试点：Java 的 Jackson 和 Pydantic 在校验时机上有什么区别？Python 为什么是"运行时类型检查"？
15 分钟保底：只写 Java→Python 对照表（15 条）。
D009 · 11-10 周二 · asyncio（JD 明确点名要会）
输入：Python asyncio 官方文档的 "Coroutines / Task / Synchronization Primitives" 三节
敲代码（90 分钟）→ bootcamp/d09_asyncio.py
- async/await 基本写法，asyncio.run 的作用
- asyncio.gather 并发多个调用，打印总耗时 vs 串行耗时（必须有明显差距）
- Semaphore 限流：并发调 10 次但最多同时 3 次
- wait_for 超时、TaskGroup（3.11+）或 gather(return_exceptions=True) 处理异常
- 反例实验：在 async 函数里调一个同步的 time.sleep(2)，观察整个程序被卡住
产出：notes/d09.md —— 3 条笔记（含"async 里调同步库的后果"）
验收：
[ ] 并发耗时明显小于串行耗时（数字记下来）
[ ] 限流生效（同一时刻不超过 3 个在跑）
[ ] 反例实验跑出来，这是面试高频题的现场证据
面试点：asyncio 的事件循环是什么？为什么 async 里写 requests.get 会卡住所有人？
15 分钟保底：只写 gather 对比实验。
D010 · 11-11 周三 · FastAPI 全家桶
输入：FastAPI 官方教程的 "Request Body / Dependencies / SSE / Exception Handling" 四节
敲代码（90 分钟）→ bootcamp/d10_fastapi.py
- 路由 + 依赖注入（Depends）+ 请求/响应模型（Pydantic）
- SSE 流式：StreamingResponse + text/event-stream，前端能逐字收到
- 中间件：加一个 X-Request-ID 头 + 耗时头
- 全局异常处理器：把 HTTPException 和未捕获异常统一成 JSON
- 用 httpx.AsyncClient 写一个客户端测试脚本
产出：notes/d10.md —— 3 条笔记（依赖注入怎么工作 / SSE 的报文长什么样 / 异常处理为什么要全局统一）
验收：
[ ] SSE 端点用 curl 能看到增量输出
[ ] 每个响应都有 request-id
[ ] 客户端脚本能跑通
面试点：FastAPI 的依赖注入和 Spring 的 DI 有什么本质区别？
15 分钟保底：只写一个带 SSE 的端点 + curl 验证。
D011 · 11-12 周四 · 可靠性四件套（重试/超时/限流/熔断）
输入：读一遍 tenacity 官方 README 的 "Retrying" 节
敲代码（90 分钟）→ bootcamp/d11_reliability.py
- httpx.AsyncClient + 连接池配置（max_connections / timeout 分级：connect/read/write/pool）
- tenacity 重试：指数退避 + 抖动（jitter）+ retry_if_exception_type
- 只对可重试错误重试（429/5xx/超时），4xx 业务错误直接抛
- 简单熔断：连续 N 次失败就短路，直接返回降级结果
- 把这套加到 D10 的 FastAPI 服务上
