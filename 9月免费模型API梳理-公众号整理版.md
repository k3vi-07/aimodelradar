# 9 月免费大模型 API 梳理：25 个基础快照可测试，14 个需核实，9 个暂不推荐（新增：本月 AI 大事件月历）

<!-- 配图：9月刊封面（同 8 月版封面风格，主数字 23/16/9 + "AI 大事件"角标） -->

> **信息截止**：2026-09-21（GMT+8）｜**核实原则**：全部条目经官网定价页/官方文档/官方活动页逐项核对，官网无法核实的均标注状态，不采信第三方转述。
> **复核轮次**：初核（官网直读）之后，9 月 21 日对 curl 只能取到 JS 空壳的页面追加无头浏览器渲染复核；条目按「官方直读 / 官方渲染 / 官方存在+社区细节 / 社区口径」分层标注信源。
> **免费口径**：永久免费层 / 一次性注册赠金 / 每日或每月循环额度 / 限时免费活动，四类全收；**有速率或额度限制也算免费**。
> **本期新增**：应读者要求，月刊新增「AI 大事件月历」板块，记录每月 AI 行业大事，放在正文最前。
> **一句话结论**：9 月海外免费层"总量稳定、名单轮换"，国内出现久违的加码（腾讯 TokenHub、火山协作奖励、美团 LongCat）；上月预告的下线全部如期落地，没有新增的"免费层死亡"，反而是红名单里跑出一个复活者（AI21）。

---

## 〇、本月 AI 大事件月历（2026-09-01 ～ 09-21）🆕

<!-- 配图：9月AI大事件时间线（横向时间轴，标注 5 个里程碑） -->

编辑部从本月起固定记录 AI 行业大事，不只盯着免费 API——模型的迭代节奏，决定了下个月免费层里会出现什么。

### 模型发布：一个月五连发，密度创今年纪录

| 日期 | 事件 | 与免费层的关系 |
|---|---|---|
| 9/1 | **Anthropic 发布 Claude Fable 5.1 与 Claude Mythos 5.1**，同日在 GitHub Copilot GA | API 付费；Copilot 订阅档可用 |
| 9/2 | **Google 发布 Gemini 3.8 Flash 与 3.8 Flash Cyber**（四个月内第 4 个 Flash 型号） | ✅ **第一时间进入 AI Studio / API 免费层**（社区口径约 10 RPM / 250K TPM / 1500 RPD） |
| 9/3 | **OpenAI 发布 GPT-6 Astra**（9/4 GA），105 万上下文，OpenRouter 口径 $10/$50 每百万 token，batch 半价 | 付费旗舰；Copilot 9/4 GA |
| 9/3 | **Qwen3.8-27B 上线 Cerebras**，社区实测约 1850 tok/s | 可用 Cerebras $5 试用金跑 |
| 9/9-10 | **DeepSeek 发布 V4.1-Flash**（552B MoE 多模态，开放权重）；9/14 起 v4-pro 请求全部按 V4.1-Flash 路由计价 | 开放权重 + 超算互联网 ¥1/M 的"准免费"路线 |
| 9/15 | **Google 发布 Gemini 3.8 Live 与 Live Extended Thinking**（音频到音频） | Live API 预览，免费口径未确认 |
| 8/28（跨月） | **腾讯混元 Hy4-Preview 发布并开源**（770B 总参 / 49B 激活 / 1M 上下文），上线 TokenHub 与 OpenRouter；9/1 出轻量版 | TokenHub 内限免（截止日待核，见下文） |

### 公司与资本：NVIDIA 系整合是本月最大变量

| 日期 | 事件 | 说明 |
|---|---|---|
| 9/3 | **NVIDIA 同意以约 $12.9-13B 收购 Hugging Face**（8 月底还是"洽谈"，9/3 落定） | 开源托管巨头易主；ggml 作者公开回应 llama.cpp 前景，社区讨论"去留"；对 HF 每月 $0.10 免费信用的长期影响未知 |
| 9/8 | **Mistral 融资 €3B**，主打"主权开放权重 AI 到前沿" | 开放权重路线获巨额注资，自托管生态利好 |
| 9/9-11 | **NYT 报道监管机构调查 NVIDIA-Groq 许可协议**（反垄断） | 巨头整合的监管反弹开始 |
| 9/15 | **Hugging Face 就此前入侵事件向 OpenAI 索赔 $100M** 算力痕迹 | 两家巨头纠纷延续；9/20 WSJ 观点版称该事件"没有传得那么邪乎" |

### 产品与生态

- **9/11**：DeepSeek V4.1 Flash 上线国家超算互联网（低价按量计费）。
- **9/14**：书生 Intern-S2 正式版开源（HuggingFace / ModelScope），Preview 版 397B 将于 **10-31 下线**。
- **9/16**：硅基流动上线全国产开源模型 `Xing4.0-29B-A4B`（256K 上下文）。
- **9/16**：Mistral × Mozilla 推出私有双语浏览合作。
- **9/18**：x.ai 发布 Grok Voice Transcribe 2.0（页面显示主体为"SpaceXAI"，名称存疑；Grok 5 仍未发布）。
- **9/16-17**：OpenRouter 出现新 stealth 匿名模型 **Union Alpha**（社区疑为混装 GLM/Gemini 的"模型路由器"），截至 9-21 官方目录已检索不到 stealth 模型——窗口疑似已关。

### 安全与治理

- **9/10**：Anthropic 9 月版威胁情报报告披露 **GTG-50021 假"廉价 Claude"转售骗局**（实际代理到别的模型并窃取凭据）及 API key 黑产。**贪便宜中转站之前，先想想你的 key 和数据会去哪。**
- **9/16**：Wired 报道 Kimi K3 "逃出沙箱"争议，K3 海外合规话题延续。

### 本月主线（编辑部观点）

1. **旗舰五连发，但"新旗舰进免费层"只有 Google 一家**——Gemini 3.8 Flash 发布当天即可免费调用，DeepSeek 走"开放权重 + 超算互联网 ¥1/M"的准免费路线，Anthropic/OpenAI 新旗舰与免费无缘。中美免费策略进一步分化。
2. **免费主角从厂商官方转向聚合器**：OpenRouter 免费款 15→21、stealth 模型"月抛化"（ox-alpha → Union Alpha 无缝接棒），聚合平台成为免费额度的主要供应方。
3. **NVIDIA 系整合加速**（Groq 资产 → Lepton → Hugging Face），中立托管方减少，监管开始介入；免费推理资源的长期获取成本可能上升。
4. **免费/低价 API 的黑产浮出水面**：假"廉价 Claude"骗局、key 窃取、账号农场——预计更多厂商跟进 Cerebras 式绑卡门槛。

---

## 上期预告，本期验尸：8 月刊 7 个"待落地事件"的核实结果

上期（8-24）留下的悬念，本期逐一交底：

| 上期记录 | 9 月核实结果 | 结论 |
|---|---|---|
| Kimi `moonshot-v1`/`k2.5` 将于 8-31 全平台下线 | **官方模型页确认已如期下线**；现役仅剩 4 款（见下文） | ✅ 落地 |
| 商汤 6.7 Flash Lite 将于 8-31 下线并路由至 6.8 | 官网产品清单已切换为 6.8；社区实测**旧 ID 路由过渡期已结束，仍调 6.7 直接报错**，需手动换 ID | ✅ 落地（下线公告原文未检索到） |
| 混元 Hy3 限时免费至 8-31 | 官方页确认免费至 8-31（Pacific）；多家媒体称**到期后再度延长至 9-30**，且 8-28 起 WorkBuddy 首发接入 Hy4-Preview（限免两周） | ⚠️ 延期说法为媒体源，以入口实时显示为准 |
| OpenRouter stealth/ox-alpha 窗口约至 8-27 | **已下线**（9-21 实时目录无任何 stealth 模型）；但 9/16-17 出现接棒者 Union Alpha，亦已消失 | ✅ 落地 + 出现接棒现象 |
| Cerebras 免费层终结，转绑卡 $5/30 天 | 官方定价页与文档确认**新政执行中，无反复**；9/3 还上了 Qwen3.8-27B | ✅ 落地 |
| 国家超算互联网 DeepSeek-V4-Flash 邀测 | **邀测免费通道已消失，8-2 起转正式计费**（¥1/百万 token）；免费仅剩网页 Chat 页；9/10 上线 V4.1 Flash | ⚠️ 转低价付费，不再是免费渠道 |
| 魔搭"新计费机制、旧免费额度口径失效" | **本次未找到任何官方公告或社区讨论能证实该说法**；主流社区口径仍是"每日 2000 次调用" | ❌ 上期口径存疑，本期更正（详见第五章） |

> 🔧 **上期勘误**：① "腾讯 TokenHub"上期标注为待核实，本期已通过腾讯云官方文档确认真实存在且为混元开放平台的升级形态（见政策变化第 2 条）；② 上期称 Cloudflare "Kimi 全系付费"，经官方计价表复核，**kimi-k2.5 不在付费专属名单内，免费 Neurons 可跑**；③ 上期"魔搭新计费机制"未获证实，请按本章口径回退。

---

## 一、本月政策变化：七件事会影响接口使用

<!-- 配图：9月政策变化时间线 -->

### 1. 智谱进入 5.x 世代，"Flash = 永久免费"不再自动成立（重要）

官方定价页（9-21 实测）确认：**GLM-4.x 世代的 8 款 Flash 模型依旧 ¥0 免费**（GLM-4.7-Flash、GLM-4-Flash-250414、GLM-Z1-Flash、GLM-4.6V-Flash、GLM-4V-Flash、GLM-4.1V-Thinking-Flash、CogView-3-Flash、CogVideoX-Flash）；但新一代 **GLM-5.3 / GLM-5.2 已上线，`GLM-5.3-Flash` 为付费**（0.8/2.8 元每百万）。**"Flash 后缀 = 免费"的经验规则从 5.x 世代起失效**，接智谱的脚本别想当然换 ID。另有全模型"缓存存储"限时免费、新用户 2000 万 token 赠额（社区口径）。
**官网来源**：https://docs.bigmodel.cn/cn/guide/start/pricing ✅（9-21 直读）

### 2. 腾讯 TokenHub 落地：从"8 款共享 100 万"升级到"每模型 100 万/1 年"

混元开放平台迁移 TokenHub 完成（官方文档 9-04 更新）：新人免费体验包**语言模型每模型 100 万 token、有效期 1 年**；多模态理解模型每模型 100 万/1 年；视觉模型积分制（生视频 50 积分、混元 3D 100 积分）；每账号每模型限领 1 次，**活动至 2026-12-31**。平台还接入了第三方 DeepSeek-V4-Pro/Flash、GLM-5、MiniMax-M3。叠加 8-28 发布并开源的 Hy4-Preview（上线即限免，社区称至 9-10，待核），**腾讯成为本月国内加码最狠的大厂**。
**官网来源**：https://cloud.tencent.com/document/product/1823/130053 ✅

### 3. 商汤免费政策改积分制，6.7 调用直接报错

官方 token-plan 页（9-21 实测）：Free 档 ¥0/月、**60,000 积分/5 小时**（社区换算约 1500 次调用/5h），覆盖 `SenseNova-6.8-Flash-Lite` 与 `SenseNova-U1-Fast`；付费 Lite/Pro 档"即将上线"。上期"deepseek-v4-flash、glm-5.2 各 500 次/5h"的口径**已被积分制替代**。社区另有说法称 KimiK3、DeepSeek-V4Pro 在其平台"全免"（单源待核）。**还在调 `sensenova-6.7-flash-lite` 的代码现在就会报错**，请换 `sensenova-6.8-flash-lite`。
**官网来源**：https://www.sensenova.cn/token-plan ✅（9-21 直读）

### 4. Kimi 老模型下线落地，开放平台只剩 4 款模型

官方定价页（9-21 实测）现役清单：`kimi-k3`（1M 上下文，输入未命中 ¥20/输出 ¥100 每百万）、`kimi-k2.6`（¥6.5/¥27）、`kimi-k2.7-code`、`kimi-k2.7-code-highspeed`。上期的"新用户 15 元代金券"官方首页与定价页已无横幅，但**登录页明示「认证领 15¥ 体验金」仍在（9-21 读者核实 platform.kimi.com/login）**——实名认证后发放，K3 是否参与以控制台为准。文件内容抽取/存储接口限时免费。K3 权重 7-27 已在 HuggingFace 开放，可自部署。
**官网来源**：https://platform.kimi.com/pricing ✅（9-21 直读）

### 5. OpenRouter 免费生态大换血：15 → 21 款，新厂进场

官方 API 实时拉取（9-21）：全站 446 模型中 **21 款带 `:free` 后缀**。新面孔包括 `qwen/qwen3.8-27b:free`（**9/17 后本周新增**）、Thinking Machines `inkling`/`inkling-small:free`（1M 上下文，文本+图像+音频）、poolside `laguna-s-2.1`/`laguna-xs-2.1:free`（代码）、`z-ai/glm-5.2:free`、`nex-agi/nex-n2.5-mini/pro:free`、`dots-studio/dots-3-note-preview:free` 等；6 月的老免费款（DeepSeek R1、Llama 3.3 70B 等）已全部转付费。另有官方免费模型随机路由器 **`openrouter/free`**（2026-02 上线，上期未收录）：一个模型 ID 自动路由到当前可用免费款，做 failover 很顺手。限额不变：20 RPM / 50 次/天，累计充值 ≥$10 后 1000 次/天。
**官网来源**：https://openrouter.ai/api/v1/models ✅（9-21 实时）

### 6. 红名单反向修正：AI21 复活，DeepSeek 官方待核

- **AI21**（上期红名单"官方定价页未核实到免费"）：官方定价页 9-21 直读现挂 **"$10 credits for 7 days, No credit card needed"**——限时试用版免费渠道，本期从红名单除名，改列国外赠金组。
- **DeepSeek 官方**（上期红名单"无免费 API"）：两条 9 月社区信源独立称 **V4 Flash/Pro 新用户有数百万元级 token 赠额、30 天有效**；官方 api-docs 定价页未列明，仅提到"granted balance"概念。若属实则红名单需摘牌——**本期移入存疑清单，注册前自行验证**。
- **Novita**：免费层 2025 年中"暂停"，现仅剩 $0.50 一次性试用（社区源）。

### 7. NVIDIA 收购 Hugging Face 落定，免费推理的中立托管又少一个

9/3 收购落定（约 $13B）。短期 HF 免费信用（$0.10/月）政策未变，但开源托管生态的中立性存疑，ggml/llama.cpp 社区已公开讨论去留；叠加 9/9 NVIDIA-Groq 反垄断调查，**"大厂免费层 + 中立开源托管"两条供给线都在向 NVIDIA 收拢**，值得持续观察但暂不影响本月可用性。

---

## 二、基础快照总览（2026-09-21）：✅ 25 个可测试 / ⚠️ 14 个需核实 / ❌ 9 个暂不推荐

<!-- 配图：23/16/9 总览 + 与 8 月对比（29→23 的去留流向图） -->

| 级别 | 平台 | 免费内容 | 类型 | 关键模型 ID | 核心限制 | 较 8 月变化 |
|---|---|---|---|---|---|---|
| ✅ | **Google Gemini** | 免费层约 20 款 | 永久免费层 | **gemini-3.8-flash（9/2 新增）**、3.7/3.6/3.5-flash、2.5-pro、embedding-2、gemma-4 | 约 10 RPM/250K TPM/1500 RPD（社区口径）；imagen/veo/lyria 不免费 | 🆕 3.8 Flash 发布当天进免费层 |
| ✅ | **智谱 AI** | 8 款 4.x Flash 免费 | 永久免费层 | GLM-4.7-Flash、GLM-Z1-Flash、GLM-4.6V-Flash、CogView-3-Flash、CogVideoX-Flash | QPS≈2；需实名 | ⚠️ 5.3-Flash 付费，规则变了 |
| ✅ | **Groq** | 免费层延续 | 永久免费层 | gpt-oss-120b/20b、qwen3.6-27b、whisper-large-v3、orpheus TTS | 30 RPM/1K RPD/200K TPD/模型 | 无变化 |
| ✅ | **Cloudflare Workers AI** | 每日 10,000 Neurons | 循环额度 | Llama 3.3-70B、qwen3、gemma-4、glm-4.7-flash、**kimi-k2.5（勘误：可用）** | 每日 UTC 重置；付费专属名单扩容（+glm-5.3 系） | 🔧 修正 k2.5 口径 |
| ✅ | **SambaNova** | 免费层 5 款 | 永久免费层 | DeepSeek-V3.1、Llama-3.3-70B、gpt-oss-120b、DeepSeek-V3.2(preview) | 20 RPM/20 RPD/20 万 token/天 | 无变化（官方文档 9-21 直读） |
| ✅ | **书生 Intern AI** | 免费 OpenAI 兼容 API | 永久免费层 | **intern-s2（9/14 正式版开源）**、s1-pro、s1、internvl3.5 | Token 6 个月需续 | 🔄 S2-Preview 10-31 下线，换正式版 |
| ✅ | **Agnes AI** | 全模态免费 | 永久免费层 | **agnes-3.0-flash、agnes-2.5-flash**、image-2.5-flash、video-2.5-flash(720P 限时) | 文本 20 RPM/视频 1 RPM | 🔄 免费矩阵换代到 2.5/3.0 |
| ✅ | **商汤 SenseNova** | 60,000 积分/5h | 限时免费 | sensenova-6.8-flash-lite、u1-fast | 6.7 已停，旧 ID 报错 | 🔄 改积分制 |
| ✅ | **美团 LongCat** 🆕 | 新用户 1000 万 token；邀请新用户双方各 1000 万 | 一次性赠金 | LongCat-Flash-Lite（685 亿参数 MoE）、LongCat-2.0 | **无每日免费额度**；OpenAI 兼容 | 🔧 读者 9-21 登录核实，修正"每日 5500 万"社区口径 |
| ✅ | **阿里云百炼** | 每模型 100 万 token | 一次性赠金 | qwen-max、qwen3.8 系列、qwen-vl-max-latest | 90 天；仅北京地域 | 无变化 |
| ✅ | **火山引擎·豆包** | 每模型 50 万 token + 协作奖励 | 赠金+循环 | doubao-seed-evolving、seed-2-1 系列 12 款 | 协作奖励**个人 200 万/模型/日、企业认证 500 万/模型/日**，需授权数据训练 | 🆕 加码（✅官方福利页渲染核实） |
| ✅ | **腾讯 TokenHub** | **每模型 100 万 token/1 年** | 一次性资源包 | Hunyuan-Hy4-Preview、Hy3（延期至 9-30？待核）+ DeepSeek-V4、GLM-5、MiniMax-M3 | 每账号每模型限领 1 次；至 12-31 | 🆕 额度升级 |
| ✅ | **百川智能** | 新用户 80 元（≈1000 万 token）+ Assistants API 限时免费 | 一次性赠金 | Baichuan-M3 系、M3-Plus | 3 个月有效（✅官方定价页直读） | 🔄 复核后回归官方口径 |
| ✅ | **百度千帆** | 每模型 100 万 token | 一次性赠金 | ERNIE-4.5-Turbo、DeepSeek-R1/V3.1 等（✅官方帮助文档直读）；ERNIE-Speed 永久免费（社区口径待核） | 3 个月有效 | TokenPlan 个人版转积分制（9 月中） |
| ✅ | **硅基流动** | 新用户 14 元 + L0 免费档 16 款 | 赠金+免费模型 | Qwen3-8B、GLM-4-9B-0414、DeepSeek-R1-0528-Qwen3-8B、**Xing4.0-29B-A4B（9/16 新上）** | 免费档限速限并发；需大陆手机号 | 🆕 新模型 |
| ✅ | **讯飞星火** | 每模型 20 万 token（✅官网口径）+ 新用户 1 万次交互量 | 限时活动 | Spark4.0 Ultra 等；Spark Lite「永久免费」为社区口径待核 | 官网未标注活动截止日 | 🔄 活动额度获官网佐证 |
| ✅ | **扣子 Coze** | **每日 1500 免费积分**（登录发放） | 循环额度 | 豆包/Kimi/DeepSeek 等 50+ 模型 | 2026-01-18 起订阅制新口径 | 🔧 上期"累计 500 次"为旧口径 |
| ✅ | **OpenRouter** | 21→24 款 `:free`（动态）+ 免费路由器 | 永久免费模型 | qwen3.8-27b:free、inkling:free、glm-5.2:free、nemotron-3-ultra:free(1M)、`openrouter/free` | 20 RPM/50 次/天 | 🆕 名单大换血 |
| ✅ | **NVIDIA NIM** | 50+ Free Endpoint | 动态免费端点 | DeepSeek-V4-Flash、Nemotron、**glm-5-3（5.2→5.3）**、MiniMax-M3 | 数量和限制以目录为准 | 🔄 GLM 端点升级 |
| ✅ | **Cohere** | Trial 每月 1,000 次 | 循环额度 | Command A+、A Reasoning、North Mini Code 等 | 20 req/min；禁生产用途 | 无变化 |
| ✅ | **Hugging Face** | 每月 $0.10 信用 | 循环额度 | 100+ 经 HF 路由模型 | 额度极小；NVIDIA 收购待交割 | 无变化（母公司变了） |
| ✅ | **Fireworks AI** | 注册送 $1 | 一次性赠金 | kimi-k3、deepseek-v4、glm-5.2、qwen3.8-max | 额度小 | 无变化 |
| ✅ | **AI21** 🆕 | **$10 信用/7 天，免卡** | 限时试用 | Jamba Mini/Large | 7 天有效 | 红名单除名 |
| ✅ | **Azure 免费账户** | $200/30 天+常免 AI 服务 | 赠金+常免 | Speech 50 万字符/月、Document Intelligence 500 页/月 | 必须绑卡；Azure OpenAI 无免费层 | 无变化 |
| ✅ | **Kimi 开放平台** | 认证领 15 元体验金 | 一次性赠金 | kimi-k3、k2.6、k2.7-code | 实名认证后发放；K3 是否参与以控制台为准 | 🔄 读者核实登录页后回归 |
| ⚠️ | **白山智算 / PPIO / Nebius / Mistral / Anthropic / ModelScope / MiniMax / DeepSeek 官方 / 阶跃 / 面壁 / 天工 / 零一 / Novita / Together** | 详见第七章存疑清单（共 14 个） | — | — | — | — |
| ❌ | **Cerebras / GitHub Models / 无问芯穹 / 国家超算互联网 / OpenAI / xAI / DeepInfra / Replicate / 302.AI 系** | 详见第八章红名单（共 9 条） | — | — | — | AI21 除名、DeepSeek 移存疑 |

> ⚠️ 存疑条目完整清单见第七章，共 **14 个**；❌ 暂不推荐条目见第八章，共 **9 条**。"暂不推荐"只表示截至核查日不适合作为免费 API 方案，不代表平台本身不可用。
> 与 8 月对比：✅ 29 → 25（Cerebras 死亡、白山/PPIO/Nebius 降级待核；百川、Kimi 复核后回归；AI21/LongCat/TokenHub 入列）。免费渠道的总供给量并未下降，主要变化是**确定性收敛**——能官方核实口径的变少了。

### 如果你只想马上开始

<!-- 配图：按用途选择免费 API 平台 -->

| 需求 | 优先测试 | 主要原因 |
|---|---|---|
| 国内直连、量大 | **智谱**、火山豆包（协作奖励 200 万/日）、硅基流动 | 火山个人 200 万/模型/日 + 智谱免费 Flash 是可持续组合 |
| 海外免费文本 API | **Gemini（3.8 Flash）**、Groq | 新旗舰当天进免费层 + 速度顶格 |
| 多模型统一调用 | **OpenRouter**（`openrouter/free` 路由器） | 21 款免费款 + 一个 ID 自动切换 |
| 长上下文（1M 级） | OpenRouter `nemotron-3-ultra:free`/`inkling-small:free`、TokenHub Hy4-Preview | 都是 1M 上下文免费渠道 |
| 视觉、图像、视频 | 智谱、Agnes、商汤 | 覆盖模态多，注意水印与活动期限 |
| 代码 | Groq gpt-oss-120b、poolside laguna:free、硅基流动 | 速度与免费额度平衡 |

### 使用前先确认四件事（老规矩）

1. 免费额度是永久层、循环额度、一次性赠金，还是限时活动。
2. 超出额度后是停止服务、返回错误，还是自动进入付费计费。
3. 是否需要实名、手机验证、信用卡，以及是否受地区限制。
4. 输入输出数据是否会用于服务改进——**火山协作奖励计划就是"用数据换额度"的显式样本**；企业代码、客户资料和隐私内容不要直接提交。

---

## 三、第一梯队：长期免费层

<!-- 配图：免费 API 梯队图 -->

### 1. Google Gemini —— 新旗舰当天进免费层，独一家

- **免费层**：输入/输出 token 全免、无美元上限、免绑卡。**9/2 发布的 `gemini-3.8-flash` 与 `3.8-flash-cyber` 发布当天即可在 AI Studio / API 免费层调用**（社区口径限速约 10 RPM / 250K TPM / 1500 RPD）。
- **免费模型**：3.8-flash（新）、3.7/3.6/3.5-flash、2.5-pro/flash、embedding 系、gemma-4、live/tts 预览系。9/15 又发布 3.8 Live（音频到音频，免费口径未确认）。
- **红线**：imagen-4、veo、lyria 仍不在免费层。免费层数据用于改进 Google 产品（EEA/英国/瑞士以外）。
- **注意**：官方 rate-limits 页本次核查从本环境不可达，模型级限额为第三方多源一致口径；`gemini-omni-flash-preview` 端点将于 9-30 弃用（官方 release notes 口径，未能复核原文）。
- **官网来源**：https://ai.google.dev/pricing ✅（以发布前官方页为准）

### 2. 智谱 GLM —— 4.x Flash 依旧免费，但换代规则变了

- **免费模型（8 款，官方定价页 9-21 实测 ¥0）**：文本 `GLM-4.7-Flash`（200K）、`GLM-4-Flash-250414`、`GLM-Z1-Flash`；视觉 `GLM-4.6V-Flash`、`GLM-4.1V-Thinking-Flash`、`GLM-4V-Flash`；图像 `CogView-3-Flash`；视频 `CogVideoX-Flash`。
- **本月关键变化**：`GLM-5.3-Flash`、`GLM-5.2` 已上线且**均为付费**（5.3-Flash 为 0.8/2.8 元每百万）。免费只认 4.x 世代的 Flash。
- **额外福利**：全模型"缓存存储"限时免费；新用户 2000 万 token 赠额（社区口径，控制台为准）。
- **官网来源**：https://docs.bigmodel.cn/cn/guide/start/pricing ✅（9-21 直读）

### 3. Groq —— 政策稳如老狗

- 免费层与限额与 8 月完全一致：gpt-oss-120b/20b、qwen3.6-27b 等（30 RPM/1K RPD/200K TPD），whisper/orpheus 语音系。Llama 对话模型与 GLM 仍不在免费层（Llama 3.3-70B/3.1-8B 8 月中已转企业专属）。官方按季度轮换阵容，10 月可期。
- **信源说明**：官方文档对脚本与无头浏览器均返回 403/Forbidden（9-21 复核确认），以上限额为多源一致口径，登录控制台后以官方页为准。
- **官网来源**：https://console.groq.com/docs/rate-limits（官方页反爬 403，多源交叉核实）

### 4. Cloudflare Workers AI —— 每日 10,000 Neurons，一份勘误

- **免费额度不变**：每天 10,000 Neurons，UTC 零点重置。
- **勘误**：上期"Kimi 全系付费"不准确——官方计价表（9-21 直读）中**付费专属名单为 7 款**：kimi-k2.6、kimi-k2.7-code、glm-5.2、**glm-5.3、glm-5.3-flash（本月新增）**、deepseek-v4-flash-0731、deepseek-v4-pro-0813；**kimi-k2.5 不在名单内，免费 Neurons 可跑**（建议自行实测确认）。
- **官网来源**：https://developers.cloudflare.com/workers-ai/platform/pricing/ ✅（9-21 直读）

### 5. SambaNova —— 本月唯一"逐字节无变化"的官方文档

- 免费层 5 款（DeepSeek-V3.1、Llama-3.3-70B、gpt-oss-120b + V3.2/gemma-4-31B 预览），20 RPM/20 RPD/20 万 token/天。社区流传的"免费层 3 月已停"与官方现行文档矛盾，以官方为准。
- **官网来源**：https://docs.sambanova.ai/docs/en/models/rate-limits ✅（9-21 直读）

### 6. 书生 Intern AI —— S2 正式版上位，Preview 倒计时

- **9/14 Intern-S2 正式版开源**（HuggingFace/ModelScope），免费体验入口 chat.intern-ai.org.cn；**S2-Preview-397B 将于 10-31 下线**，正在用的抓紧迁到正式版。s1-pro（内置联网）、s1、internvl3.5 延续。
- 免费 OpenAI 兼容 API（base_url：`https://chat.intern-ai.org.cn/api/v1/`）、Token 6 个月有效的口径未见变化。
- **官网来源**：https://internlm.intern-ai.org.cn ✅

### 7. Agnes AI —— 免费矩阵整体换代

- 官方 pricing 页（9-21 实测）：文本 `agnes-3.0-flash`、`agnes-2.5-flash`（$0）；图像 `image-2.0/2.1/2.5-flash`（$0）；视频 `video-v2.0`（$0/秒）、`video-2.5-flash` 720P 限时免费。上期的 2.0 系已标记 deprecated。收费款为 2.5-pro 与 video-2.5。
- 限制：免费档文本 20 RPM、视频 1 RPM；多 Key 共享限制池。
- **官网来源**：https://wiki.agnes-ai.com/en/docs/pricing ✅（9-21 直读）

### 8. 商汤 SenseNova —— 积分制时代

- Free 档 ¥0/月、**60,000 积分/5 小时**（≈1500 次调用/5h），覆盖 `sensenova-6.8-flash-lite`（256K 轻量多模态）与 `sensenova-u1-fast`（原生多模态/信息图）。付费 Lite/Pro 档"即将上线"——上期的 deepseek-v4-flash/glm-5.2 免费口径已被替代，**别再按 500 次/5h 写死限流逻辑**。
- 社区（9-06）称 KimiK3、DeepSeek-V4Pro 在其平台全免——单源待核，以 token-plan 页为准。
- **官网来源**：https://www.sensenova.cn/token-plan ✅（9-21 直读）


---

## 四、第二类：注册赠金和限时额度

### 国内赠金组

| 平台 | 赠金内容 | 有效期 | 关键模型 ID | 获取 | 9 月变化 |
|---|---|---|---|---|---|
| **腾讯 TokenHub** | **每模型 100 万 token**（原 8 款共享 100 万） | 1 年；活动至 12-31 | Hunyuan-Hy4-Preview、DeepSeek-V4-Pro/Flash、GLM-5、MiniMax-M3 | 腾讯云实名 | 🆕 大幅加量 |
| **火山引擎·豆包** | 每模型 50 万 token（文本）+ 图像 200 张/模型 + 视频 200 万 token/模型；协作奖励**个人 200 万/模型/日、企业认证 500 万/模型/日**，开通新模型另赠 300 万代金券 | 长期+每日 | doubao-seed-evolving、seed-2-1 系列 12 款 | 注册+实名；协作奖励需授权数据（✅官方福利页渲染核实 9-21） | 🆕 循环加码 |
| **阿里云百炼** | 每模型 100 万 token | 90 天；仅北京地域 | qwen-max、qwen3.8、qwen-vl-max-latest | 注册自动发放 | 无变化 |
| **百度千帆** | 每模型 100 万 token（✅官方帮助文档直读 9-21：ERNIE-4.5-Turbo 系、ERNIE-X1-Turbo、DeepSeek-R1/V3 系等各 100 万）；ERNIE-Speed 永久免费为社区口径待核 | 3 个月 | ERNIE-4.5-Turbo、DeepSeek-R1/V3.1、Qwen3 | 百度智能云实名 | TokenPlan 转积分制 |
| **硅基流动** | 新用户 14 元 + L0 免费档 16 款 ¥0 模型 | — | Qwen3-8B、GLM-4-9B、Xing4.0-29B-A4B（新） | 注册（大陆手机号） | 🆕 新模型 |
| **美团 LongCat** 🆕 | 新用户 **1000 万 token**；邀请新用户**双方各 1000 万** | — | LongCat-Flash-Lite（685 亿参数 MoE/A29B）、LongCat-2.0（1.6T） | 美团账号注册；**无每日免费额度**；OpenAI 兼容 | 🔧 读者登录核实修正 |
| **百川智能** | 新用户 80 元（≈1000 万 token）+ Assistants API 限时免费（✅官方定价页直读：2024-05-22 起新注册 80 元、3 个月） | 3 个月 | Baichuan-M3 系、M3-Plus（API 降价 70%） | 注册+实名 | 🔄 复核后回归 ✅ |
| **Kimi 开放平台** | **认证领 15 元体验金**（登录页明示，读者 9-21 核实） | 3 个月 | kimi-k3（1M）、k2.7-code、k2.6；K3 是否参与以控制台为准 | 实名认证后发放 | 🔄 回归 ✅ |
| **讯飞星火** | 每模型 20 万 token + 新用户 1 万次交互量（✅官网口径 9-21 渲染核实）；Spark Lite「永久免费」为社区口径 | 活动期 | Spark4.0 Ultra、Spark Lite | 注册+实名 | 🔄 部分获官网佐证 |
| **白山智算** ⚠️ | 实名 150 元（**+300 元部分 3-15 已过期**） | — | DeepSeek-R1-0528-Qwen3-8B、bge-m3（永久免费状态待核） | 注册+实名 | ⚠️ 活动退坡 |
| **MiniMax** ⚠️ | 实名新用户 15 元代金券（第三方源）；GMI Cloud 20 亿 token 活动 **9-6 已截止** | — | MiniMax-M3 | 注册+实名 | 活动已过期一项 |

**重点提示**：
- **TokenHub 是本月国内赠金首选**：每模型独立 100 万且有效期长达 1 年，还附带第三方模型（DeepSeek-V4、GLM-5、MiniMax-M3）——相当于一个腾讯壳里的多模型赠金包。
- **火山协作奖励**的额度不是白给的：机制是授权推理数据用于模型优化、T+1 按采集量返还（个人 200 万/模型/日、企业认证 500 万/模型/日）。**敏感数据勿走此通道**。

### 国外赠金组

| 平台 | 赠金内容 | 有效期/限制 | 关键模型 ID | 获取 | 9 月变化 |
|---|---|---|---|---|---|
| **AI21** 🆕 | **$10 信用 / 7 天** | 免卡；7 天有效 | Jamba Mini（$0.20/$0.40）、Jamba Large（$2/$8 每百万） | 注册即得 | 红名单除名 |
| **Fireworks AI** | 注册送 $1 | 额度小 | kimi-k3、deepseek-v4、glm-5.2、qwen3.8-max | 注册即得 | 无变化（官方页 9-21 直读） |
| **Mistral** ⚠️ | 免费套餐存在；"$10/月 API 信用"与"限速免费（约 1 RPS）"两种口径冲突 | 非无限 | mistral-large-3、codestral、voxtral | 注册即得 | 口径仍未官方确认 |
| **Anthropic** ⚠️ | 新用户赠金约 $5：多数第三方称有、亦有汇总称无，官方页不可达未能裁决 | 需手机验证 | Claude Fable 5.1 / Mythos 5.1（新旗舰） | console 注册 | 口径冲突维持 |
| **Azure 免费账户** | $200/30 天 + 12 个月热门服务免费 | 必须绑卡 | Azure Speech、Document Intelligence（常免） | 注册+绑卡 | 无变化（官方页 9-21 直读） |
| **Nebius Token Factory** ⚠️ | 上期"$1 新账号信用"本期官方文档未找到标注 | — | 60+ 开源模型 | 注册 | 降级待核 |

**红线**：Azure 的 $200 试用到期后，Azure OpenAI/Foundry 仍无独立免费层。

---

## 五、第三类：聚合平台和中转接口

### 1. OpenRouter —— 免费款 21→24 款，生态大换血

- **当前免费模型（9-21 官方 API 两次实测 21→24 款，名单每日动态变化）**：`qwen/qwen3.8-27b:free`（本周新增）、`z-ai/glm-5.2:free`、`cohere/north-mini-code:free`、`google/gemma-4-26b/31b:free`、`nvidia/nemotron-3-ultra-550b-a55b:free`（1M）、`nemotron-3.5-lightning:free`（1M）、`nemotron-3-super/nano-omni:free`、`nemotron-3.5-content-safety:free`、`thinkingmachines/inkling:free`、`inkling-small:free`（1M，文本+图像+音频）、`poolside/laguna-s-2.1 / laguna-xs-2.1:free`（代码）、`nex-agi/nex-n2.5-mini/pro:free`、`inclusionai/ling-3.0-flash-fin/sante/vl:free`、`liquid/lfm-2.5-2.6b:free`、`dots-studio/dots-3-note-preview:free`。
- **免费路由器**：`openrouter/free`（官方，2026-02 上线）——自动随机路由到当前可用免费款，failover 神器，上期漏收录。
- **限额不变**：20 RPM / 50 次/天；累计充值 ≥$10 后 1000 次/天。余额为负时免费模型也报 402。
- **官网来源**：https://openrouter.ai/api/v1/models ✅（9-21 实时）

### 2. ModelScope 魔搭 —— 上期"新计费机制"说法未获证实，本期回退口径

- 上期记录"魔搭已启用新计费、每日 2000 次口径失效"。**本期核查未找到任何官方公告或社区讨论佐证该说法**；主流社区口径（8-09 实测、9 月复述）仍是 **API-Inference 免费、每日 2000 次调用（按次数、不限 token）**、非商业化产品、额度随平台压力动态调整。
- 处理：本期按"免费、每日 2000 次（社区口径）"收录，同时维持提醒——**以官方 limits 文档与控制台实时显示为准**。仍需绑定阿里云账号实名、单并发。
- **官网来源**：https://www.modelscope.cn/docs/model-service/API-Inference/limits

### 3. 扣子 Coze —— 订阅制新口径：每日 1500 积分

- 2026-01-18 起订阅套餐升级：**每日免费积分 500 → 1500，改为登录后发放**（官方文档）。上期"累计 500 次免费调用、RPM 300"为旧口径，9 月未见再调整。
- **官网来源**：https://docs.coze.cn ✅

### 4. Hugging Face —— $0.10/月不变，母公司要换了

- 免费用户 $0.10/月信用（官方注明 subject to change），覆盖 15+ Inference Providers、38K+ 模型。NVIDIA 收购 9/3 落定、待交割；短期政策未变，长期中立性存疑（见大事件板块）。
- **官网来源**：https://huggingface.co/pricing

### 5. NVIDIA NIM —— GLM 免费端点升级 5.2 → 5.3

- 模型目录免费端点延续，官方页可见 **"Free Endpoint glm-5-3"**；DeepSeek-V4-Flash、Nemotron、MiniMax-M3、Cosmos 等无下架反证。"50+"总数为动态口径，本次未能精确复核。开发者计划成员可免费无限原型。
- **官网来源**：https://build.nvidia.com/models

### 6. Cohere —— Trial Key 每月 1,000 次，无变化

- 免费模型：Command A+、A Reasoning、A Translate、A Vision、Command A、R+、R、R7B、North Mini Code（均 20 req/min）+ Embed/Rerank。禁生产用途。
- **官网来源**：https://docs.cohere.com/docs/rate-limits ✅（9-21 直读）

### 7. Stealth 观察角：从 ox-alpha 到 Union Alpha，"月抛彩蛋"成连续节目

- 上期的 `stealth/ox-alpha` 窗口如期结束（9-21 官方目录已无任何 stealth 模型）。
- **9/16-17 出现接棒者 `Union Alpha`**（HN 热帖 + OpenRouter 官方 X 确认），社区分析怀疑它其实是"模型路由器"、底层混有 GLM/Gemini 系模型；截至 9-21 它也已从目录消失。
- **使用建议不变**：匿名免费模型可用无敏感内容做短期测试；不要提交客户资料、私有代码、密钥或未公开数据。编辑部将把"stealth 观察"作为固定栏目追踪。

---

---

## 专题：RAG 辅助免费 API（向量化 / 重排 / 语音 / 检索）

> 读者点播新增。以读者 **9-10 已核验**的《免费 AI 模型 API 清单》为底稿，编辑部 **9-21 复核更新**：官方已核验条目标 ✅，第三方口径标 ⚠️。主角大模型之外，Embedding / Rerank / STT / TTS 这些"配角"调用量往往更大、成本最容易失控。

### Embedding：文本向量化

**国内直连**

| 平台 | 免费额度 | 关键模型 | 核心限制 |
|---|---|---|---|
| **硅基流动** | bge-m3、bge-large-zh/en-v1.5 **完全免费**（限 RPM）✅9-10 官方价格页核验 | BAAI/bge-m3（1024 维、100+ 语言、8K） | 需实名；Pro 加速版 ¥0.07/百万 |
| **阿里云百炼** | 每模型 100 万 token（90 天）；异步批处理另送 2000 万 ✅ | text-embedding-v4、qwen3-text-embedding | 动态降维、OpenAI 兼容 |
| **智谱 AI** | 新用户 2000 万 token 赠金可抵扣（各模型共享） | embedding-3（256~2048 维） | 🔧 9-21 官方定价页确认：**Embedding-3/2 本体付费**（0.5/0.25 元/百万），非免费层 |
| **腾讯 TokenHub** | Embedding 单独 100 万 token、1 年 ✅ | hunyuan-embedding | 有效期最长的选择 |
| **百度千帆** | 各模型独立免费额度（bge-large-zh 等第三方向量模型） | bge-large-zh | 需实名 |
| **火山豆包** | 每模型 50 万 token；协作奖励可叠加 ✅ | doubao-embedding | 按模型计 |

**海外**

| 平台 | 免费额度 | 关键模型 | 备注 |
|---|---|---|---|
| **Gemini** | 约 1500 请求/天 ⚠️（第三方口径） | gemini-embedding-001（3072 维） | 免绑卡；免费层数据可能用于训练 |
| **Cloudflare** | 1 万 Neurons/天 ✅ | bge-large 系 | 边缘节点低延迟 |
| **NVIDIA NIM** | 免费端点 40 RPM | nv-embedqa 系 | 注册即用 |
| **Jina AI** | 约 100 万 token/月 ⚠️ | jina-embeddings-v3/v4 | 开源版 CC-BY-NC 禁商用 |
| **Cohere** | 每月 1,000 次（与 Chat 共享）✅9-21 官方文档核验 | embed-v4（Trial） | 禁商用 |
| **Mistral** | 实验计划免费层 ⚠️ | mistral-embed | 口径待官方确认 |

### Rerank：检索结果精排

| 平台 | 免费内容 | 关键模型 | 备注 |
|---|---|---|---|
| **硅基流动** | **bge-reranker-v2-m3 完全免费** ✅9-10 官方核验 | BAAI/bge-reranker-v2-m3 | Cohere 兼容 `POST /v1/rerank` |
| **阿里云百炼** | qwen3-rerank（0.6B/4B/8B）享每模型 100 万/90 天 | qwen3-rerank | 中文榜单第一梯队、支持 instruction |
| **NVIDIA NIM** | 免费端点 40 RPM | rerank-qa-mistral-4b | 免绑卡 |
| **Cohere** | 每月 1,000 次 ✅ | rerank-3.5 | 质量顶级；禁商用 |
| **Jina AI** | Starter 免费额度（与 Embedding 共享）⚠️ | jina-reranker-v2 | — |
| **OpenRouter** | ❌ **9-21 两次实测 `:free` 清单均无 rerank 模型**（Rerank VL 疑已下架） | — | 免费 rerank 需另寻，清单以 models?max_price=0 实时为准 |
| **智谱** | ❌ **付费**（9-21 核实：价格页无免费 rerank；GLM-rerank 0.8 元/百万） | — | 赠金可抵扣 |

### 语音：STT 转写 & TTS 合成

**STT（转写）**
- **Groq**：whisper-large-v3-turbo **2,000 请求/天**（另有 7,200 音频秒/时、28,800 秒/天 ≈ 8 小时）✅9-10 官方文档核验，海外最优解；
- **硅基流动**：SenseVoiceSmall（比 Whisper 快约 15 倍）、Qwen3-ASR-1.7B、XingChenASR V3.2（含说话人分离，会议场景利器）**全部免费** ✅；单文件 50MB / 1 小时；
- **火山豆包**：每应用 20 小时试用（半年有效）✅；**Cloudflare** whisper large-v3-turbo（1 万 Neurons/日）✅；**ElevenLabs Scribe** 4.5 小时批量 + 2.5 小时实时/月 ⚠️；**Google STT V2** 60 分钟/月永久 + $300 首充信用 ⚠️；**NIM** Parakeet-TDT 0.6B（开源 ASR 榜首）40 RPM；**Deepgram** $200 一次性信用 ⚠️。
- ⚠️ **避坑**：OpenAI 语音转写从第一分钟起计费，零免费额度。

**TTS（合成）**
- **火山豆包**：语音合成 2 万次 / 大模型合成 2 万字符 / 声音复刻 2 万字符 / Seed-Audio 30 分钟（均半年有效）✅，中文自然度第一梯队；
- **Azure Speech F0**：50 万字符/月滚动（需国际信用卡）；**NIM**：Magpie-TTS-Multilingual / Zeroshot（支持声音克隆）；**ElevenLabs** 1 万字符/月（免费层**禁商用**）；**Cloudflare**：aura-1（英文）。
- **本地开源（真·免费不限量）**：Kokoro（82M、CPU 实时、Apache 2.0）、ChatTTS、FishAudio S1-mini、Piper（MIT）。

### 联网检索与向量库（编辑部 9-21 新核实）

| 服务 | 免费内容 | 用途 | 信源 |
|---|---|---|---|
| **Exa** | **注册 $20 + 每月 $10 credits，免绑卡** | RAG 联网检索 API | ✅官方定价页直读 9-21 |
| **Qdrant Cloud** | **Free forever**：0.5 vCPU / 1GB RAM / 4GB 盘 + 免费云端推理 | 向量数据库 | ✅官方定价页直读 9-21 |
| Tavily / Pinecone / Zilliz | 官网 JS 渲染，本轮未能完成核验 | 检索 / 向量库 | ⚠️ 待核（各自定价页） |

### 零成本 RAG 组合（照抄可用）

| 场景 | 组合 |
|---|---|
| 零成本 RAG | 硅基 bge-m3（向量）+ bge-reranker-v2-m3（重排）+ GLM-4.7-Flash（生成，本刊免费层） |
| 带联网检索 | 上述组合 + Exa（注册 $20 + 每月 $10） |
| 批量转写 | Groq whisper（2,000 次/天）或硅基 SenseVoice |
| 涉敏/内网 | 全本地：bge-m3 + bge-reranker + Whisper + Kokoro（均 Apache 2.0，数据不出门） |

> **四条避坑**：① Google 免费层数据用于训练、国内平台实名留痕——涉敏数据走本地；② Jina 开源版 CC-BY-NC、Cohere/ElevenLabs 免费层禁商用；③ 火山语音试用半年、百炼 90 天、TokenHub 1 年，记好到期日；④ 免费额度是厂商获客成本，生产环境准备付费或本地兜底。

## 六、选型横评：9 月的白嫖性价比榜

<!-- 配图：性价比横评雷达图或星级表 -->

| 平台 | 免费量级 | 折算逻辑 | 适合场景 | 白嫖评级 |
|---|---|---|---|---|
| **美团 LongCat** | 新用户 1000 万 + 邀请各 1000 万 | 一次性 | 短期批量任务 | ★★★☆☆（读者核实：无每日额度） |
| **Google Gemini** | 无美元上限（速率限制） | 新旗舰当天进免费层 | 日常对话/翻译/嵌入 | ★★★★★ 首选 |
| **智谱 GLM** | 8 款 4.x Flash 免费 | 无 token 上限，QPS≈2 | 国内生产级小流量 | ★★★★★ 首选 |
| **火山豆包** | 50 万×12 款 + 最高 500 万/日 | 数据换额度 | 中文长文本批量 | ★★★★☆（注意数据授权） |
| **腾讯 TokenHub** | 每模型 100 万×多模型×1 年 | 赠金有效期最长 | 多模型对比、长周期项目 | ★★★★☆ 本月升级 |
| **Groq** | 30 RPM/1K RPD/模型 | 速度顶格 | 实时对话/低延迟 | ★★★★☆ |
| **OpenRouter** | 50 次/天（21 款免费） | 一个 Key 调全家 | 路由 failover | ★★★☆☆ |
| **百度千帆** | 100 万×N + Speed 不限量 | ERNIE-Speed 兜底 | 多模型轮换 | ★★★☆☆ |
| **商汤** | 60,000 积分/5h | 高频小步快跑 | 多模态轻量任务 | ★★★☆☆（口径刚变，留意付费档上线） |
| **Cloudflare** | 每日 10,000 Neurons | 中量循环 | 边缘函数/小工具 | ★★★☆☆ |
| **AI21** | $10/7 天 | 短期试用 | Jamba 架构尝鲜 | ★★☆☆☆（7 天倒计时） |
| **HF** | $0.10/月 | 极小 | 连通性测试 | ★★☆☆☆ |

**结论**：国内日常跑量认 **智谱 + 火山协作奖励（个人 200 万/模型/日）**；海外铁三角 **Gemini + Groq + OpenRouter(:free)** 延续；长上下文免费渠道本月最富——OpenRouter 两款 1M 免费 + TokenHub Hy4-Preview（1M）；批量活依旧是 **豆包 + 千帆 + 百炼 + TokenHub** 四家赠金打包。

---

## 七、存疑清单：14 个「注册前先核实」的平台

| 平台 | 已核实事实 | 待确认 | 依据来源 |
|---|---|---|---|
| **DeepSeek 官方** 🔺 | 上期红名单"无免费"；本期两条 9 月社区信源独立称 **V4 Flash/Pro 新用户赠数百万元级 token/30 天**；官方 api-docs 仅提"granted balance"概念，未列赠额条目 | 新用户赠金是否属实——**若属实将摘掉红名单** | 社区两源（9-18 等）；api-docs.deepseek.com |
| **白山智算** | 9-21 无头浏览器复核：**官网现行页面已无任何赠金活动信息**（"免费/150/300/赠"全部零命中，网站已改版）；"+300 元"部分 2026-03-15 已过期 | 150 元是否仍可领、永久免费模型现状 | ai.baishan.com |
| **PPIO 派欧云** | 官方定价页（9-21 直读）**已无任何免费/赠金说明**；模型阵容很新 | 5 元注册赠金是否还在 | ppio.com/pricing |
| **ModelScope 魔搭** | 免费每日 2000 次为社区口径，官方 limits 页无法直读 | 计费口径（上期"新计费"未证实） | modelscope.cn |
| **Nebius** | 官方文档无新账号赠金标注 | 上期"$1 信用"是否注册流程内展示 | docs.tokenfactory.nebius.com |
| **Mistral** | 免费套餐存在（官方）；$10/月信用 vs 限速免费两种口径 | 免费额度形态 | mistral.ai/pricing |
| **Anthropic** | 新用户赠金约 $5：多源称有、亦有汇总称无 | 赠金存续与金额 | console.anthropic.com（本环境不可达） |
| **MiniMax** | 实名 15 元券（第三方 8-11）；20 亿 token 活动 9-6 截止 | 官方免费政策页未找到 | platform.minimaxi.com |
| **阶跃星辰** | Step Plan 3-23 起转常规包月订阅（Flash Mini/Plus/Pro/Max） | 后续是否再开免费活动 | platform.stepfun.com |
| **面壁智能** | lantay.modelbest.cn 实测已变为"文档处理智能工作台" | MiniCPM-V 4.6 免费 API 是否还在线 | lantay.modelbest.cn |
| **昆仑万维·天工** | 网页版免费；Skywork-OR1 开源可自部署 | API 免费额度未公开 | model-platform.tiangong.cn |
| **零一万物** | 核心团队并入阿里，独立 API 基本停止；Yi 系列由百炼托管（享每模型 100 万/90 天） | 独立平台后续 | help.aliyun.com |
| **Novita AI** | 免费层 2025 年中"暂停"，现仅 $0.50 一次性试用 | 是否恢复 | novita.ai |
| **Together AI** | 有 $0.00/M 标价模型（prism-ml-ternary-bonsai-27b）；最低 $5 充值才可用 | 注册赠金无证据 | together.ai |

---

## 八、避坑红名单：9 条别碰（本月一条除名、一条移出待核）

| 平台 | 结论 | 依据 |
|---|---|---|
| **Cerebras** | 免费层已终结：绑卡 $5/30 天一次性信用；社区吐槽无缓存折扣、同会话比 OpenRouter 贵数倍 | 官方定价页+文档（9 月执行中） |
| **GitHub Models** | 7-30 全面退役，无回旋；官方推荐迁 Azure AI Foundry，社区主流是 OpenRouter/Ollama | 官方 changelog |
| **无问芯穹 Infini-AI** | 官网明示个人服务停止；3-30 起基础版 LLM API 免费服务也已停止 | 官网+官方文档 |
| **国家超算互联网** | 8-2 起 DeepSeek-V4-Flash 转正式计费（¥1/百万），**邀测免费通道消失**；免费仅剩网页 Chat（非 API）。低价但不再免费 | 凤凰科技 8-02 + 官网 |
| **OpenAI** | 无免费层，$5 预付起步；免费 token 仅限数据共享计划 | 官方口径（页面对部分网络 403） |
| **xAI Grok** | API 无免费层，维持 | 官方文档 |
| **DeepInfra** | 无免费层/赠金说明 | 定价页 |
| **Replicate** | 纯用量计费，无免费层 | 官方定价页（9-21 直读） |
| **302.AI / AiHubMix / API2D / Chutes** | 纯付费/点数制，无免费额度；其中转性质叠加本月披露的"假廉价 Claude"骗局，**采买中转请格外谨慎** | 各自官网 + Anthropic 9 月威胁报告 |

> 本月红名单变动：**AI21 除名**（官方 $10/7 天试用确认）；**DeepSeek 官方移入存疑清单**（新用户赠额有两条社区源，待官方确认）。

---

## 九、低成本调用方案：给接口准备备用链路

<!-- 配图：免费 API 备用链路图（更新：加入 LongCat 与 openrouter/free） -->

1. **统一接口层**：本月绝大多数推荐渠道兼容 OpenAI 格式（LongCat、TokenHub、硅基、智谱、OpenRouter 等全家兼容），但视觉/音频/视频与工具调用参数各家有差异，接 LiteLLM 或自建路由时逐家验证错误码。
2. **Failover 路由**：主模型 429/额度耗尽自动切下一家。本月推荐链：主用 GLM-4.7-Flash（国内直连）→ doubao-seed（协作奖励 200 万/日）→ Gemini 3.8 Flash（海外）→ `openrouter/free`（免费路由器兜底）。
3. **分工矩阵**（9 月版）：
   - **日常对话/推理**：GLM-4.7-Flash + Gemini 3.8 Flash + doubao-seed（协作奖励）
   - **长上下文（1M）**：OpenRouter `nemotron-3-ultra:free` / `inkling-small:free` + TokenHub Hy4-Preview
   - **嵌入/检索**：Gemini embedding-2 + 硅基 bge 系
   - **语音**：Groq whisper + orpheus TTS、Cloudflare whisper
   - **图像/视频**：智谱 CogView-3-Flash / CogVideoX-Flash、Agnes image/video-2.5-flash、商汤 U1-Fast（水印参数注意）
   - **代码**：Groq gpt-oss-120b、OpenRouter `poolside/laguna-s-2.1:free`、硅基 Xing4.0
4. **额度监控**：各家控制台可查，写个每日脚本汇总；商汤积分制、Coze 积分制、千帆积分制……**"积分"正在替代"次数/token"成为新的计量黑话**，监控脚本要分别适配。
5. **换 ID 提醒**：本月起以下旧 ID 已死或将死——`sensenova-6.7-flash-lite`（报错）、`intern-s2-preview`（10-31 下线）、`moonshot-v1`/`kimi-k2.5`（已下线）、`gemini-omni-flash-preview`（9-30 弃用）。

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_API_KEY",
    base_url="https://YOUR_PROVIDER/v1",
)

resp = client.chat.completions.create(
    model="YOUR_MODEL_ID",
    messages=[{"role": "user", "content": "用一句话介绍这个模型。"}],
)
print(resp.choices[0].message.content)
```

首次接入时，建议先用短文本测试鉴权、模型 ID、超时、限流和错误返回，再接入真实业务。

---

## 十、高频疑问（FAQ）

**Q1：8 月说 29 个可测试，9 月变 24 个，免费渠道在萎缩吗？**
渠道总量没少多少，**少的是"确定性"**：白山、PPIO、Nebius 这几家从"官方可核实"退到"社区口径待核"（百川、Kimi 均在 9-21 复核后回归），Cerebras 彻底转付费。同时 LongCat、TokenHub、AI21 是净新增。真正的趋势是：永久免费层向头部集中（Gemini/智谱/Groq/Cloudflare），其余玩家转向试用金和积分制。

**Q2：LongCat 的免费额度到底是什么？**
9-21 经读者登录核实：**没有每日免费额度**，只有新用户一次性 1000 万 token、邀请新用户双方各 1000 万。此前社区流传的"每日 5500 万"口径不成立，本刊已修正——登录墙后面的额度数字，必须以控制台为准。

**Q3：智谱的免费规则到底怎么记？**
一句话：**4.x 世代的 Flash 免费，5.x 世代全部付费**。`GLM-4.7-Flash` 免费，`GLM-5.3-Flash` 付费，别看后缀想当然。

**Q4：stealth 模型（ox-alpha/Union Alpha）能不能用在正式项目里？**
不能。匿名模型不知运营方、不知数据去向、随时下线，只适合无敏感内容的短期测试。等它"转正"（公布身份与条款）再说。

**Q5：NVIDIA 买下 Hugging Face，我的免费额度会没吗？**
短期内不会（收购待交割、政策未变）。但开源托管中立性是长期变量，重要权重建议本地备份一份，别把鸡蛋放在正在被收购的篮子里。

**Q6：免费额度能商用吗？**
分平台。Gemini/智谱等免费层一般允许商用（有限速）；OpenRouter 部分 :free 模型可能用数据训练；Cohere Trial 明确禁生产用途；火山协作奖励需授权数据。商用前读条款或发邮件要书面确认。

**Q7：想跑 100 万 token 级大任务，怎么凑？**
火山协作奖励（个人 200 万/模型/日）+ LongCat 新用户 1000 万（一次性）+ TokenHub（每模型 100 万）+ 千帆/百炼（每模型 100 万）+ 商汤积分（5 小时窗口）。9 月凑免费算力比 8 月容易。

---

## 结语：确定性的时代结束了，清单的时代还在

老规矩，最后三句话：

1. **这份清单是 2026-09-21 的快照**。本月最大的教训是"口径会突然变"——商汤从次数制改积分制、Coze 从累计制改每日积分、智谱免费规则换代，都是不打招呼的。**对接前务必点开官网来源复核**。
2. **优先用 ✅ 永久免费层**（Gemini/智谱/Groq/Cloudflare），赠金当零食；⚠️ 名单里的平台先核实再注册。
3. **红名单维持 9 条**，别在 OpenAI/xAI/Cerebras 上浪费时间；DeepSeek 官方和 AI21 的动向下期继续追。

**本月核查方法说明**：海外平台以官方页直读 + OpenRouter 官方 API 实时拉取为主；国内平台以官方文档/定价页直读为主，社区信源仅作交叉验证且均已标注。**9 月 21 日增补复核**：对 curl 只能取到 JS 空壳的页面（火山、讯飞、白山、LongCat、Groq、Gemini）改用无头浏览器渲染复核——火山福利页与讯飞活动额度由此获得官方口径；千帆、百川官方文档直读升级；白山确认活动已从官网撤下；LongCat 平台页为美团登录墙——**读者当日登录核实：无每日免费额度，仅新用户 1000 万 + 邀请双方各 1000 万，本刊已据此修正**；Groq 文档反爬（对无头浏览器同样 Forbidden）、Gemini 域名在本核查环境网络不可达，这两家维持分层标注。免费政策变化很快，收藏时请同时记下核查日期。

---

## 附录：本期全部官网来源（按条目挂靠，可直接复核）

**Gemini**
https://ai.google.dev/pricing ✅｜https://blog.google（3.8 Flash / 3.8 Live 发布页）

**智谱**
https://docs.bigmodel.cn/cn/guide/start/pricing ✅（9-21 直读）｜https://docs.bigmodel.cn/cn/api/rate-limit

**Groq**
https://console.groq.com/docs/rate-limits｜https://groq.com/blog（9 月无公告，已直读）

**Cloudflare**
https://developers.cloudflare.com/workers-ai/platform/pricing/ ✅（9-21 直读）

**SambaNova**
https://docs.sambanova.ai/docs/en/models/rate-limits ✅（9-21 直读）

**书生 Intern AI**
https://internlm.intern-ai.org.cn ✅｜https://huggingface.co（Intern-S2 正式版）

**Agnes AI**
https://wiki.agnes-ai.com/en/docs/pricing ✅（9-21 直读）

**商汤**
https://www.sensenova.cn/token-plan ✅（9-21 直读）

**美团 LongCat**
https://longcat.chat ✅｜https://tech.meituan.com

**阿里百炼**
https://help.aliyun.com/zh/model-studio/new-free-quota ✅

**火山豆包**
https://www.volcengine.com/docs/87301/2106521 ✅（2026-09-21 无头浏览器渲染核实；福利页更新时间 2025-12-04）

**腾讯 TokenHub**
https://cloud.tencent.com/document/product/1823/130053 ✅（9-04 官方文档）

**百度千帆**
https://ai.baidu.com/ai-doc/WENXINWORKSHOP/3mh3fw81w ✅（新用户免费额度官方帮助文档，9-21 直读）｜TokenPlan 积分制为社区源，约 9-15

**百川智能**
https://platform.baichuan-ai.com/prices ✅（9-21 直读：新注册 80 元、3 个月；Assistants API 限时免费）

**讯飞星火**
https://www.xfyun.cn/prices（"每模型 20 万 tokens、新用户 1 万次"官网促销口径，9-21 渲染核实）｜https://www.xfyun.cn/doc/spark/TokenPlan.html

**Kimi**
https://platform.kimi.com/pricing ✅（9-21 直读）｜https://platform.kimi.com/docs/models ✅（下线确认）

**硅基流动**
https://siliconflow.cn/models ✅｜https://docs.siliconflow.cn/cn/release-notes/overview ✅

**扣子 Coze**
https://docs.coze.cn ✅（订阅套餐公告）

**OpenRouter**
https://openrouter.ai/api/v1/models ✅（9-21 实时）｜https://openrouter.ai/docs/guides/routing/routers/free-router

**NVIDIA NIM**
https://build.nvidia.com/models

**Cohere**
https://docs.cohere.com/docs/rate-limits ✅（9-21 直读）

**Hugging Face**
https://huggingface.co/pricing

**AI21**
https://ai21.com/pricing ✅（9-21 直读，$10/7 天）

**Fireworks**
https://fireworks.ai/pricing ✅（9-21 直读）

**Azure**
https://azure.microsoft.com/en-us/free/ ✅（9-21 直读）

**Cerebras**
https://www.cerebras.ai/pricing ✅｜https://inference-docs.cerebras.ai ✅

**DeepSeek**
https://api-docs.deepseek.com ✅｜https://www.deepseek.com（V4.1-Flash 发布公告）

**ModelScope**
https://www.modelscope.cn/docs/model-service/API-Inference/limits

**国家超算互联网**
https://www.scnet.cn ✅｜凤凰科技 8-02 计费报道

**大事件来源**
https://www.anthropic.com/news（Fable/Mythos 5.1）｜https://openai.com/index/gpt-6-astra/ ｜https://www.cnbc.com/2026/09/03/（NVIDIA-HF）｜https://mistral.ai/news/（€3B 融资）｜https://www.anthropic.com/threat-intelligence-report-september-2026 ｜https://news.ycombinator.com/item?id=49728468（Union Alpha）

**上期对照**
见《8 月免费模型 API 梳理》（2026-08-24 快照）及其勘误说明（本文"上期预告，本期验尸"一节）
