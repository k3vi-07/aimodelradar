# 8 月免费大模型 API 梳理：29 个当前可用，13 个需核实，17 个暂不推荐

![8月免费模型 API 梳理封面](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/01-cover.png)

> **信息截止**：2026-08-24（GMT+8）｜**核实原则**：全部条目经官网定价页/官方文档/官方活动页逐项核对，官网无法核实的均标注状态，不采信第三方转述。
> **免费口径**：永久免费层 / 一次性注册赠金 / 每日或每月循环额度 / 限时免费活动，四类全收；**有速率或额度限制也算免费**。
> **一句话结论**：本月免费 API 政策变化很大，但截至 2026-08-24，仍有 29 个渠道值得测试。本文按免费类型、使用门槛、模型用途和风险做了整理，适合用来搭建低成本的测试与备用调用方案。

## 8 月 24 日追更：发布后 5 天，又有这些变化

原始清单是 8 月 19 日的基础快照。本节记录发布后至 8 月 24 日发现的新渠道和待核实变化；这些内容暂不直接并入“29 个当前可测试”的原始统计，避免不同日期的口径混在一起。

### ⭐ 新增关注：OpenRouter 出现匿名免费模型

OpenRouter 在 8 月 20 日出现 `stealth/ox-alpha`，目前被社区标记为免费模型，窗口期据称持续到 8 月 27 日左右。公开信息显示它具备长上下文和编码/Agent 使用场景，但运营方和底层模型身份尚未明确，社区关于其模型指纹的判断不能当作官方事实。

**使用建议**：可以用无敏感内容做短期测试；不要提交客户资料、私有代码、密钥或未公开数据。免费状态和可用期限以 OpenRouter 模型页实时显示为准。

### ⭐ 新增渠道：国家超算互联网 DeepSeek-V4-Flash 邀测

国家超算互联网出现 DeepSeek-V4-Flash 邀测活动，公开信息提到最高可获得较大规模的 Token 额度。由于该活动可能需要申请、审核或受邀请资格限制，暂列为“新增待核实渠道”，不纳入原有 29 个稳定可测试平台。

### ⭐ 限时福利：混元 Hy3

WorkBuddy、CodeBuddy 或腾讯云 TokenHub 的相关入口出现 Hy3 限时免费通道，活动据称持续至 8 月 31 日。该福利与本文原先记录的混元共享资源包不是同一条额度，使用前应确认入口、适用模型、每日上限和到期时间。

### ⚠️ 四项额度出现口径差异

| 平台 | 原清单 | 追更发现 | 当前处理 |
|---|---|---|---|
| 火山豆包 | 每模型 50 万 Token | 社区称部分模型可能达到 200 万 Token | 以控制台实际额度为准 |
| 硅基流动 | 新用户 14 元 | 有来源称实名后赠送 16 元券 | 以账户到账记录为准 |
| 商汤 | DeepSeek-V4-Flash 为 500 次/5 小时 | 有来源称部分账号为 150 次/5 小时 | 可能存在账号或活动差异 |
| NVIDIA NIM | 17 款 Free Endpoint | 有来源称免费模型数量更多 | 需按 Free Endpoint 标记逐项确认 |

### ✅ 暂未发现需要推翻的核心结论

截至 8 月 24 日，Kimi 老模型 8 月 31 日下线、Cerebras 免费层终止、GitHub Models 退役、Groq 免费层限制以及智谱 Flash 免费层等核心判断暂未发现需要改写的依据。由于免费政策可能按地区、账号和活动批次变化，仍建议在正式调用前重新打开官方页面确认。

---

## 导语：这届白嫖党，先学会避雷再谈薅羊毛

2026 年 8 月，免费大模型 API 市场经历了今年以来最剧烈的一次洗牌：

- **GitHub Models** —— 曾经白嫖界的"圣地"，**7 月 30 日全面退役**，playground / API / BYOK 全部下线；
- **Cerebras** —— 那个号称"免费无限 token"的速度怪兽，**8 月 17 日正式终结开放免费层**，从此要绑卡才有 $5 信用；
- **Kimi** —— `moonshot-v1` 和 `k2.5` 系列**已停止向新用户开放，8 月 31 日全平台正式下线**；
- **商汤** 6.7 Flash Lite 同一天（8-31）下线；**无问芯穹**个人服务 6 月底已关停；**阶跃星辰** Step Plan 免费活动 7 月底截止。

听起来像末日？别慌。截至本文核查日，仍有不少渠道提供免费层、注册赠金或限时额度。需要特别说明：免费政策会随地区、账号类型、实名状态和活动周期变化，本文是一个时间快照，不构成长期可用承诺。每个平台都建议以控制台实际显示为准。

---

## 一、本月"政策地震"：五件事，件件影响你的代码

![8月政策变化时间线](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/02-timeline.png)

### 1. GitHub Models 退役（2026-07-30）——白嫖第一圣地的陨落

官方公告，无回旋余地：playground、API、BYOK 全部下线。以前靠 GitHub Copilot 附赠额度跑模型的日子彻底结束。**如果你有代码还在调 `models.github.ai`，现在就得迁移。**

### 2. Cerebras 免费层终结（2026-08-17）——"无限 token"神话破灭

Cerebras 曾是免费 API 圈的传说：注册即用、速度碾压全场。**2026 年 7 月起政策变更**：开放免费层终结，改为 **Free Trial = 绑卡后送 $5 一次性信用、30 天有效**；旧免费层保留到 **8 月 17 日**，此后全部账户过渡到新政策。更扎心的是，曾经免费的 **GLM-4.7 已于 8 月 17 日同步退役**。白嫖党请转 Groq。

### 3. Kimi 老模型 8 月 31 日全平台下线——代码要赶紧换

官网模型列表原文：**「`kimi-k2.5` 和 `moonshot-v1` 系列模型已停止向新注册用户开放（全平台正式下线时间为 8 月 31 日）」**。另外 `kimi-k2` 系列早已于 5 月 25 日下线、`kimi-latest` 1 月 28 日下线。**还在用这些 ID 的，请尽快切到 `kimi-k3`**。

### 4. 无问芯穹：个人服务关停（2026-06-26 起）

官方公告：停止向个人用户提供大模型按量调用，**不再接受新用户注册**，全面转向企业服务。官网已无注册入口。曾经的"算力平台白嫖"选项，没了。

### 5. 阶跃星辰：Step Plan 免费活动截止（2026-07-31）

限时免费活动已截止，官网首页已无活动入口。想白嫖 Step 系列？等下一波活动。

---

## 二、总览速查：✅ 29 个当前可测试 / ⚠️ 13 个需核实 / ❌ 17 个暂不推荐

![29个当前可测试、13个需核实、17个暂不推荐](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/03-overview.png)

![免费 API 的四种形态](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/04-free-types.png)

![29个免费 API 渠道分类](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/05-platform-groups.png)

| 级别 | 平台 | 免费内容 | 类型 | 关键模型 ID | 核心限制 |
|---|---|---|---|---|---|
| ✅ | **Google Gemini** | 免费层约 20 款模型 | 永久免费层 | gemini-3.7/3.6/3.5-flash、2.5-pro、embedding-2、gemma-4 | 速率限制；图像/视频/音乐不免费 |
| ✅ | **智谱 AI** | 9 款 Flash 模型永久免费 | 永久免费层 | GLM-4.7-Flash、GLM-Z1-Flash、GLM-4.6V-Flash、CogView-3-Flash、CogVideoX-Flash | QPS≈2；需实名 |
| ✅ | **Groq** | 免费层 12 款 | 永久免费层 | gpt-oss-120b/20b、qwen3.6-27b、whisper-large-v3、orpheus TTS | 30 RPM/1K RPD/模型；Llama/GLM 不在免费层 |
| ✅ | **NVIDIA NIM** | 17 款 Free Endpoint | 永久免费层 | nemotron-3.5-lightning、z-ai/glm-5.2、minimax-m3、diffusiongemma | 40 RPM；限原型用途 |
| ✅ | **Cloudflare Workers AI** | 每日 10,000 Neurons | 循环额度 | Llama 3.3-70B、qwen3、gemma-4、glm-4.7-flash、kimi-k2.5 | 每日重置；5 款前沿模型需付费 |
| ✅ | **SambaNova** | 永久免费层 5 款 | 永久免费层 | DeepSeek-V3.1、Llama-3.3-70B、gpt-oss-120b、DeepSeek-V3.2(预览) | 20 RPM/20 RPD/20万token/天 |
| ✅ | **书生 Intern AI** | 永久免费 OpenAI 兼容 API | 永久免费层 | intern-s2-preview、s1-pro、s1、s1-mini、internvl3.5 | 密钥 6 个月需续 |
| ✅ | **Agnes AI** | 全模态无限期免费 | 永久免费层 | agnes-2.0-flash、agnes-image-2.1-flash、agnes-video-2.0 | RPM 限制；1M 上下文灰度 50% |
| ✅ | **商汤 SenseNova** | 公测期全免费 | 限时免费 | sensenova-6.8-flash-lite、u1-fast、deepseek-v4-flash、glm-5.2 | 6.7 8-31 下线；U1 图带水印 |
| ✅ | **阿里云百炼** | 每模型 100 万 token | 一次性赠金 | qwen-max、qwen3-coder-plus、qwen-vl-max-latest | 90 天有效；仅北京地域 |
| ✅ | **火山引擎·豆包** | 文本每模型 50 万 token+每日可领 | 赠金+循环 | doubao-seed-evolving、seed-2-1-pro 等 12 款 | 图像 200 张/视频 200 万 token |
| ✅ | **腾讯混元** | 8 款模型共享 100 万 token | 一次性资源包 | Hunyuan-a13b、role、translation、vision 系列 | 1 年有效；迁移 TokenHub |
| ✅ | **百度千帆** | 17 款各 100 万 token | 一次性赠金 | ERNIE-4.5-Turbo、DeepSeek-R1/V3.1、Kimi-K2、Qwen3 | 3 个月有效 |
| ✅ | **百川智能** | 新用户 80 元（≈1000 万 token） | 一次性赠金 | Baichuan4、4-Turbo、4-Air、3-Turbo、M3 医疗系 | 3 个月有效 |
| ✅ | **Kimi 开放平台** | 新用户 15 元代金券 | 一次性赠金 | kimi-k3、k2.7-code、k2.6 | K3 不参与代金券；老模型 8-31 下线 |
| ✅ | **讯飞星火** | 每模型 20 万 token（活动） | 限时活动 | Spark4.0 Ultra、Spark Max、Spark Pro | 智能体 API 限 100 次权益 |
| ✅ | **白山智算** | 注册+实名送 150 元，再调用再送 300 元 | 赠金+永久免费 | DeepSeek-R1-0528-Qwen3-8B、bge-m3 永久免费 | **限量前 500 名** |
| ✅ | **硅基流动** | 新用户 14 元赠金+¥0 免费模型 | 赠金+免费模型 | Qwen3-8B、GLM-4-9B-0414、DeepSeek-R1-0528-Qwen3-8B | 免费档限速限并发；需大陆手机号 |
| ✅ | **Fireworks AI** | 注册送 $1 | 一次性赠金 | kimi-k3、deepseek-v4、glm-5.2、qwen3.8-max 等 15+ | 额度小 |
| ✅ | **OpenRouter** | `:free` 免费模型 | 永久免费模型 | nemotron-3-ultra-550b:free、gemma-4:free、gpt-oss-20b:free | 20 RPM/50 次/天 |
| ✅ | **ModelScope 魔搭** | 每日 2000 次 | 循环额度 | 带闪电标识的开源模型（Qwen/DeepSeek/GLM） | 单模型≤500 次/天；需绑阿里云 |
| ✅ | **扣子 Coze** | 累计 500 次免费调用 | 循环额度 | 豆包/Kimi/DeepSeek 等 50+ 模型 | RPM 300；超 500 次即停 |
| ✅ | **Hugging Face** | 每月 $0.10 信用 | 循环额度 | Llama-3.3-70B、DeepSeek-V3.1、Qwen3-235B、GLM-5.2 等 100+ | 额度极小 |
| ✅ | **Azure 免费账户** | $200/30 天+常免 AI 服务 | 赠金+常免 | Azure Speech 50 万字符/月、Document Intelligence 500 页/月 | 必须绑卡；Azure OpenAI 无免费层 |
| ✅ | **PPIO 派欧云** | 注册+邀请码+实名送 5 元 | 赠金+免费尝鲜 | deepseek-r1/v3 community 版免费 | 需邀请码+实名 |
| ✅ | **Cohere** | Trial 每月 1,000 次 | 循环额度 | Command A+、A Reasoning、North Mini Code 等 | 20 req/min；免绑卡 |
| ✅ | **Nebius Token Factory** | 新账号 $1 免费信用 | 一次性赠金 | 60+ 开源模型（Llama/DeepSeek/Qwen/Kimi-K2） | 无永久免费模型 |
| ⚠️ | **Mistral** | 免费套餐含 $10/月 API 信用 | 订阅附带 | mistral-large-3、codestral、voxtral、ocr 等 13 款 | 非无限免费 |
| ⚠️ | **Anthropic** | 新用户赠金约 $5 | 一次性赠金 | Claude Haiku 4.5 / Sonnet 4.6 / Opus 4.x | 需手机验证；官方未标金额 |
| ⚠️ | **Cerebras** | **免费层已终结** | 一次性信用 | gpt-oss-120b、gemma-4-31b | 绑卡送 $5、30 天过期 |

> ⚠️ 存疑条目完整清单见第七章，共 **13 个**；❌ 暂不推荐条目见第八章，共 **17 个**。这里的“暂不推荐”只表示截至核查日不适合作为本文的免费 API 方案，不代表平台本身不可用。

### 如果你只想马上开始

![按用途选择免费 API 平台](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/06-use-cases.png)

| 需求 | 优先测试 | 主要原因 |
|---|---|---|
| 国内直连、中文对话 | 智谱 GLM、硅基流动 | 注册门槛相对低，接口资料较完整 |
| 海外免费文本 API | Gemini、Groq | 免费层清晰，适合做原型和个人项目 |
| 多模型统一调用 | OpenRouter | 一个接口切换多个模型，但免费额度动态变化 |
| 视觉、图像、视频 | 商汤、智谱、Agnes | 覆盖模态较多，需重点确认水印和活动期限 |
| 代码和推理 | Gemini、Groq、SambaNova | 模型选择和速度较适合测试 |

### 使用前先确认四件事

![注册和使用前的五个门槛](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/07-thresholds.png)

1. 免费额度是永久层、循环额度、一次性赠金，还是限时活动。
2. 超出额度后是停止服务、返回错误，还是自动进入付费计费。
3. 是否需要实名、手机验证、信用卡，以及是否受地区限制。
4. 输入输出数据是否会用于服务改进；企业代码、客户资料和隐私内容不要直接提交。

---

## 三、第一梯队：永久免费层，注册即白嫖

![免费 API 三个梯队](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/08-tiers.png)

这几家是"零成本、零风险、长期可用"的首选，建议全部注册。

### 1. Google Gemini —— 白嫖之王，没有之一

- **免费层**：输入/输出 token 全免，**无美元上限**，**无需绑卡**。AI Studio 建个 API Key 就能用。
- **免费模型（约 20 款）**：
  - 对话：`gemini-3.7-flash`、`3.6-flash`、`3.5-flash`、`3.5-flash-lite`、`3.1-flash-lite`、`3-flash-preview`、`2.5-pro`、`2.5-flash`、`2.5-flash-lite`
  - 实时语音/TTS：`gemini-3.5-live-translate-preview`、`3.1-flash-live-preview`、`3.1-flash-tts-preview`、`2.5-flash-native-audio`、`2.5-flash-tts`
  - 嵌入：`gemini-embedding-2`（多模态）、`gemini-embedding-001`
  - 开源：`gemma-4`；机器人：`gemini-robotics-er-2-preview` 等
- **红线**：**图像（imagen-4）、视频（veo 系列）、音乐（lyria-3）在免费层均不可用**，别指望白嫖 Veo。免费层数据用于改进 Google 产品（EEA/英国/瑞士以外）。2.0-flash 系列已于 6 月 1 日停服。
- **官网来源**：https://ai.google.dev/pricing ✅（2026-08-19 逐模型复核）

### 2. 智谱 GLM —— 国内最良心，9 款 Flash 全家桶

- **免费内容**：**9 款 Flash 模型永久免费**（官方模型概览页明确标注"免费"），国内直连、OpenAI 兼容。
- **免费模型**：
  - 文本：`GLM-4.7-Flash`（200K/128K）、`GLM-4-Flash-250414`（128K/16K）、`GLM-Z1-Flash`（128K 推理）、`GLM-4.5-Flash`（即将下线）
  - 视觉：`GLM-4.6V-Flash`（128K/32K）、`GLM-4.1V-Thinking-Flash`（64K/16K）、`GLM-4V-Flash`（16K/1K）
  - 图像：`CogView-3-Flash`；视频：`CogVideoX-Flash`（10 秒/4K/60fps）
- **注意**：`GLM-4.7-FlashX` 和 `GLM-4-FlashX-250414` **不免费**，别搞混。免费模型速率限制（第三方测 QPS≈2）。
- **官网来源**：https://docs.bigmodel.cn/cn/guide/start/model-overview ✅

### 3. Groq —— 速度之王，12 款免费模型

- **免费层**：注册即用、**免绑卡**，推理速度号称"最快"。免费模型共 **12 款**：
  - LLM：`openai/gpt-oss-120b`、`gpt-oss-20b`、`gpt-oss-safeguard-20b`、`qwen/qwen3.6-27b`（30 RPM/1K RPD/8K TPM/200K TPD）
  - 推理：`groq/compound`、`compound-mini`（30 RPM/250 RPD）
  - 语音：`whisper-large-v3`、`whisper-large-v3-turbo`（20 RPM，按音频秒限）
  - TTS：`canopylabs/orpheus-v1-english`、`orpheus-arabic-saudi`（10 RPM）
  - 安全：`meta-llama/llama-prompt-guard-2-22m` / `86m`
- **重要**：**Llama 对话模型和 GLM 不在免费层**（免费表里没有任何 Llama chat / GLM）。
- **官网来源**：https://console.groq.com/docs/rate-limits ✅

### 4. Cloudflare Workers AI —— 每日循环额度，白嫖永动机

- **免费额度**：**每天 10,000 Neurons**，每日 UTC 零点重置，超出才需付费（$0.011/1000 Neurons）。
- **免费模型**：绝大多数在免费额度内——Llama（3.1/3.2/3.3/4-scout/guard）、DeepSeek（V3.2/R1-distill）、Qwen（qwen3/qwen3-embedding/qwen2.5-coder）、GLM-4.7-flash、Gemma（3-12b/4-26b）、gpt-oss-120b/20b、Kimi-K2.5、Nemotron-3-120b、FLUX 图像、whisper 音频、moondream3.1 视觉。
- **红线**：仅 **5 款前沿模型需付费账单**：`@cf/moonshotai/kimi-k2.6`、`@cf/moonshotai/kimi-k2.7-code`、`@cf/zai-org/glm-5.2`、`@cf/deepseek-ai/deepseek-v4-flash-0731`、`@cf/deepseek-ai/deepseek-v4-pro-0813`。
- **官网来源**：https://developers.cloudflare.com/workers-ai/platform/pricing/ ✅

### 5. SambaNova Cloud —— DeepSeek-V3.1 免费跑

- **免费层**：生产模型 3 款（`DeepSeek-V3.1`、`Meta-Llama-3.3-70B-Instruct`、`gpt-oss-120b`）+ 预览 2 款（`DeepSeek-V3.2`、`gemma-4-31B-it`）。
- **限制**：每模型 **20 RPM / 20 RPD / 20 万 tokens/天**；**MiniMax-M2.7 仅 Developer Tier 可用**（要绑卡），免费层没有。
- **官网来源**：https://docs.sambanova.ai/docs/en/models/rate-limits ✅

### 6. 书生 Intern AI —— 上海AI实验室的免费午餐

- **免费内容**：官方教程原文："**Intern 系列模型提供免费的 OpenAI 兼容格式 API**"，永久免费、无需绑卡。
- **免费模型**：`intern-s2-preview`（35B-A3B，256K，最新）、`intern-s1-pro`（256K，内置联网搜索）、`intern-s1`（32K 科学多模态）、`intern-s1-mini`（32K）、`internvl3.5-241b-a28b`（32K 多模态）；别名 `intern-latest` 当前指向 s2-preview。
- **注意**：**API Token 有效期 6 个月**，到期前记得续；未提供嵌入模型。base_url：`https://chat.intern-ai.org.cn/api/v1/`。
- **官网来源**：https://internlm.intern-ai.org.cn/doc/docs/模型列表/ ✅

### 7. Agnes AI —— 全模态无限期免费（新加坡 Sapiens AI）

- **免费内容**：官网原文 **"Free API — Free Access to Frontier Models"**，官方 FAQ 原文 "**Our core AI models are free to use indefinitely**"——**无限期免费**，文本/图像/视频全模态，**免绑卡**，OpenAI/Anthropic 兼容（base_url：`https://apihub.agnes-ai.com/v1`）。
- **免费模型**：`agnes-2.0-flash`（文本，Claw-Eval 第 9）、`agnes-image-2.1-flash`（文生图，最高 4K）、`agnes-video-2.0`（文生视频，音画同步）。
- **注意**：**1M 上下文是灰度上线 50%**，不是全量；免费范围限 2.0/2.1 系列；免费用户受 RPM 限制。
- **官网来源**：https://agnes-ai.com ✅ ｜ https://wiki.agnes-ai.com/en/docs/faqs ✅

### 8. 商汤 SenseNova —— 公测期全免费（有下线预警，重点看）

- **免费额度**：公测期 **¥0/月**，各模型独立计数，同账户所有 Key **共享配额**。
- **免费模型与次数（每 5 小时）**：
  - `sensenova-6.8-flash-lite`（256K 轻量多模态智能体）→ **1,500 次/5h**
  - `sensenova-u1-fast`（原生多模态，信息图生成）→ **1,500 次/5h**
  - `deepseek-v4-flash`（1M 上下文，支持思考/非思考+工具调用）→ **500 次/5h**
  - `glm-5.2`（智谱旗舰，1M 上下文，128K 输出）→ **500 次/5h**
- 🔴 **下线预警**：**SenseNova 6.7 Flash Lite 将于 2026-08-31 正式下线**（现已平滑路由至 6.8，代码里 Model ID 要手动换成 `sensenova-6.8-flash-lite`）。
- ⚠️ **水印**：U1 Fast 生成图片默认带水印，去水印需传 `watermark` 参数（限时免费）。
- **官网来源**：https://platform.sensenova.cn/token-plan ✅

---

## 四、第二梯队：注册送钱，一次性赠金

适合"短期项目 + 白嫖充值"，把各家赠金领一遍，够跑不少实验。

### 国内赠金组

| 平台 | 赠金内容 | 有效期 | 关键模型 ID | 获取 |
|---|---|---|---|---|
| **阿里云百炼** | **每个模型各 100 万 token**（独立计算） | 90 天；仅北京地域 | qwen-max、qwen3-coder-plus、qwen-vl-max-latest、wanx | 注册自动发放，免实名即用 |
| **火山引擎·豆包** | 文本**每模型 50 万 token**；图像每模型 200 张；视频每模型 200 万 token | 长期+每日可领 | doubao-seed-evolving、seed-2-1-pro-260628、seed-2-1-turbo、seed-2-0 系列等 12 款 | 注册+实名（身份证+人脸） |
| **腾讯混元** | **8 款模型共享 100 万 token** + embedding 单独 100 万 | 1 年 | Hunyuan-a13b、role-latest、translation、turbos-vision | 腾讯云实名 |
| **百度千帆** | **17 款模型各 100 万 token** | 3 个月 | ERNIE-4.5-Turbo-128K/32K、ERNIE-X1-Turbo、DeepSeek-R1/V3.1、Kimi-K2-Instruct、Qwen3-235B/30B/Coder | 百度智能云实名 |
| **百川智能** | **80 元**（≈1000 万 token） | 3 个月 | Baichuan4、4-Turbo、4-Air、3-Turbo、M3-Plus 医疗系 | 注册+实名 |
| **Kimi 开放平台** | **15 元代金券** | 3 个月 | kimi-k3（1M）、k2.7-code、k2.6；**K3 不参与代金券** | 实名后发放 |
| **讯飞星火** | **每模型 20 万 token**（活动）+ 新用户 1 万次交互量 | 活动期 | Spark4.0 Ultra、Spark Max(32K)、Spark Pro(128K) | 注册+实名 |
| **白山智算** | 注册+实名 **150 元** + 首次调用再送 **300 元**（**限量前 500 名**）；邀新 +200 元/人 | 代金券无有效期 | DeepSeek-R1-0528-Qwen3-8B / BAAI/bge-m3 等**永久免费** | 注册+实名 |
| **硅基流动** | **新用户 14 元**（官方计费文档原文） | — | Qwen3-8B、GLM-4-9B-0414、GLM-Z1-9B、DeepSeek-R1-0528-Qwen3-8B、DeepSeek-OCR、SenseVoiceSmall 等**¥0 免费** | 注册（需大陆手机号） |
| **PPIO 派欧云** | 注册+邀请码+实名 **5 元**（≈500 万 DeepSeek-V3 token）；邀请注册 15 元、邀好友 30 元/人 | — | deepseek-r1/v3 community 版免费尝鲜 | 需邀请码+实名 |

**重点提示**：
- **火山豆包**还有循环福利——协作奖励计划：个人每天每模型额外领 **200 万 tokens**，企业 500 万；开通最新模型再赠 **300 万 token 代金券**。这是国内唯一"可持续薅"的大厂。
- **白山智算**的 450 元体验金**限量前 500 名**，先到先得，去晚了汤都没了。
- **硅基流动**的免费模型不消耗余额（限速限并发），适合挂后台跑小任务。

### 国外赠金组

| 平台 | 赠金内容 | 有效期/限制 | 关键模型 ID | 获取 |
|---|---|---|---|---|
| **Fireworks AI** | 注册送 **$1** | 额度小 | kimi-k3、deepseek-v4-pro/flash、glm-5.2、qwen3.8-max、minimax-m3、gpt-oss-120b 等 15+ | 注册即得 |
| **Nebius Token Factory** | 新账号 **$1 免费信用** | 无永久免费模型；海外网络 | 60+ 开源模型（Llama/DeepSeek/Qwen/Kimi-K2/gpt-oss） | 注册即得，免信用卡 |
| **Mistral** | 免费套餐含 **$10/月 API 信用** | 非无限；Pro $14.99/月含 $30 | mistral-large-3、medium-3.5、small-4、codestral、voxtral、ocr | 注册即得 |
| **Anthropic** | 新用户赠金约 **$5** | 需手机验证；官方未标金额 | Claude Haiku 4.5 / Sonnet 4.6 / Opus 4.x | console 注册 |
| **Azure 免费账户** | **$200/30 天** + 12 个月热门服务免费 | **必须绑卡**（$1 临时验证） | Azure AI Speech 50 万字符/月、Document Intelligence 500 页/月（常免） | 注册+绑卡 |

**红线**：Azure 的 $200 试用到期后，**Azure OpenAI/Foundry 没有独立免费层**——想靠它白嫖 GPT 系，只能吃这 30 天窗口。

---

## 五、第三梯队：聚合与中转，一个 Key 调全网

不想一家家注册？用这些聚合平台，一个 Key 打通几十个模型。

### 1. OpenRouter —— 免费模型路由器（重点推荐）

- **免费额度**：带 `:free` 后缀的模型；**20 RPM / 每天 50 次请求**；历史累计充值 ≥ $10 后升级为 **1000 次/天**（注意是累计门槛，不是保持余额）。
- **当前免费模型（2026-08 抓取，约 15 款）**：`nvidia/nemotron-3-ultra-550b-a55b:free`（1M 上下文）、`nemotron-3.5-lightning:free`、`nemotron-3-super-120b:free`、`nemotron-3-nano:free`、`poolside/laguna-s-2.1:free`（编码）、`cohere/north-mini-code:free`、`google/gemma-4-26b:free`、`openai/gpt-oss-20b:free`、`deepgram/flux-tts:free`、`fish-audio/s2.1-pro-free:free` 等。
- **注意**：免费列表**动态变化**（经典 deepseek/qwen:free 本轮未见，可能下架）；余额为负时免费模型也报 402。
- **官网来源**：https://openrouter.ai/models?max_price=0 ✅

### 2. ModelScope 魔搭 —— 国内直连，每日 2000 次

- **免费额度**：每位注册用户**每天 2000 次** API-Inference；**每模型每天最多 500 次**；部分大模型（DeepSeek-R1-0528 / V3.2-Exp）**仅 100 次/天**。
- **免费模型**：仅带"蓝绿闪电"标识的开源模型（Qwen 全系 / DeepSeek / GLM / Kimi / MiniMax 等）。
- **限制**：**必须绑定阿里云账号且实名**；单并发定位；429 时官方建议换模型或次日再用。
- **官网来源**：https://www.modelscope.cn/docs/model-service/API-Inference/limits ✅

### 3. 扣子 Coze —— 累计 500 次免费调用

- **免费额度**：官方 API 文档——个人免费版"**累计 500 次免费额度**"，用超即停。
- **可调模型**：50+ 大模型（豆包/Kimi/DeepSeek/通义等，经 Bot/工作流 API 调用）。
- **限制**：模型 **RPM 300**；发起对话 20 QPS；免费额度不适用 SDK 请求。
- ⚠️ 坊间流传的"QPS=2/QPM=60/QPD=3000"是 **2024 年老数据，已过时**，别信。
- **官网来源**：https://docs.coze.cn/developer_guides/coze_api_overview ✅

### 4. Hugging Face Inference —— 每月 $0.10 信用

- **免费额度**：Free 用户 **$0.10/月**，适用于**所有经 HF 路由的模型**（100+ 款，动态变化）：Llama-3.3-70B、DeepSeek-V3.1/V4-Pro/R1、Qwen3-235B、gpt-oss-120b/20b、MiniMax-M3、GLM-5.2/4.7-Flash、Kimi-K3/K2.6、gemma-4-31B 等。
- **限制**：额度极小（够你测接口，不够跑业务）；超额需先购信用。
- **官网来源**：https://huggingface.co/docs/inference-providers/pricing

### 5. NVIDIA NIM —— 17 款 Free Endpoint（附完整清单）

- **免费额度**：目录中带 **"Free Endpoint"** 标记的模型可用 API Key 免费原型调用，**40 RPM**，不按 token 计费。
- **已确认 17 款**：`nvidia/nemotron-3.5-lightning-30b-a3b`、`nemotron-3-ultra-550b-a55b`、`nemotron-3-nano-omni-30b-a3b-reasoning`、`nemotron-3-embed-1b`、`nemotron-3.5-content-safety`、`cosmos3-nano`、`cosmos3-nano-reasoner`、`synthetic-video-detector`、`riva-translate-4b-instruct-v2`、`ising-calibration-1.5-31b`、`z-ai/glm-5.2`、`minimaxai/minimax-m3`、`stepfun-ai/step-3.7-flash`、`meta/muse-glimmer-30b`、`google/diffusiongemma-26b-a4b-it`、`thinkingmachines/inkling`、`poolside/laguna-xs-2.1`。
- ⚠️ 目录是无限滚动 SPA，**此清单为已确认部分、非全量**（DeepSeek/Llama/Qwen 家族可能还有，需浏览器手动筛选）。
- **官网来源**：https://build.nvidia.com/models

### 6. Cohere —— Trial Key 每月 1,000 次

- **免费额度**：Trial Key **每月 1,000 次 API 调用**（总数），免绑卡免电话。
- **免费模型**：Chat 9 款（Command A+、A Reasoning、A Translate、A Vision、Command A、R+、R、R7B、**North Mini Code**，均 20 req/min）+ Embed（2,000 inputs/min）+ Rerank 等。
- **官网来源**：https://docs.cohere.com/docs/rate-limits

---

## 六、选型横评：谁是白嫖性价比之王

光列清单不够，给你算一笔"免费额度性价比"的账（按各家官方口径估算）：

| 平台 | 免费量级 | 折算逻辑 | 适合场景 | 白嫖评级 |
|---|---|---|---|---|
| **Google Gemini** | 无美元上限（速率限制） | 量大到测不出上限 | 日常对话/翻译/嵌入 | ★★★★★ 首选 |
| **智谱 GLM** | 9 款永久免费 | 无 token 上限，只有 QPS≈2 | 国内生产级小流量 | ★★★★★ 首选 |
| **Groq** | 30 RPM/1K RPD/模型 | 速度顶格，额度紧 | 实时对话/低延迟 | ★★★★☆ |
| **火山豆包** | 50 万×12 款 + 每日 200 万 | 约 380 万字×12 | 中文长文本批量 | ★★★★☆ |
| **白山智算** | 450 元 + 3 款永久免费 | 450 元≈千万级 token | 一次性大活 | ★★★★☆（限 500 名） |
| **百度千帆** | 17 款 × 100 万 | 17 款模型轮换 | 多模型对比评测 | ★★★★☆ |
| **阿里百炼** | 每模型 100 万 × N | 模型最多 | 全家桶试用 | ★★★★☆ |
| **商汤** | 500~1500 次/5h × 4 款 | 高频小步快跑 | 1M 长上下文/工具调用 | ★★★☆☆（有下线雷） |
| **Kimi** | 15 元代金券 | 一次性 | 代码/1M 上下文 | ★★★☆☆ |
| **OpenRouter** | 50 次/天 | 聚合 15 款免费 | 路由 failover | ★★★☆☆ |
| **Cloudflare** | 每日 10,000 Neurons | 中量循环 | 边缘函数/小工具 | ★★★☆☆ |
| **HF** | $0.10/月 | 极小 | 接口连通性测试 | ★★☆☆☆ |

**结论**：日常主力用 **Gemini + 智谱 + Groq** 铁三角（一个免绑卡量大、一个国内直连、一个速度快）；批量活交给 **豆包+千帆+百炼** 三个大厂赠金；长上下文场景认准 **商汤 deepseek-v4-flash 和 Kimi-k3**（都是 1M）。

---

## 七、存疑清单：13 个「注册前先核实」的平台

![免费 API 存疑与避坑风险分级](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/09-risk.png)

这些平台**官网有免费佐证，但关键细节（额度金额、有效期、平台域名）未获官方最终确认**。注册前务必到官网/控制台核实，别拿第三方说法当准话：

| 平台 | 已核实事实 | 待确认 | 官网来源 |
|---|---|---|---|
| **Anthropic** | 官方确认新用户有「small amount of free credits」；约 $5（多来源一致，官方定价页仍未标金额） | 需手机验证（部分国家不支持）；Claude Code 安装赠 $200 为第三方渠道福利 | console.anthropic.com |
| **阶跃星辰** | Step Plan 限时免费活动**已于 2026-07-31 截止**（官网首页已无活动入口） | 新用户赠金（100 万 token/30 天）未官方确认；后续是否再开新活动 | platform.stepfun.com |
| **零一万物** | 阿里云百炼托管版 Yi 模型各 100 万 token（180 天，需申请） | 零一官方平台自身免费额度（第三方称送 ¥10） | help.aliyun.com/zh/model-studio/yi-api |
| **MiniMax** | NVIDIA NIM 上可免费调 MiniMax M2.1（第三方） | 官方平台免费政策页未找到 | platform.minimaxi.com |
| **面壁智能** | MiniCPM-V 4.6 / MiniCPM-o 4.5 开放免费 API（官方 GitHub/官网） | 具体额度与平台域名（openbmclab → lantay 迁移） | lantay.modelbest.cn |
| **昆仑万维·天工** | 网页版免费 | API 免费额度未公开 | model-platform.tiangong.cn |
| **Google Vertex AI** | Agent Compute 每月前 50 vCPU-时等免费（官网） | 新用户 $300/90 天赠金 | cloud.google.com/vertex-ai |
| **Together AI** | 有标价 $0.00/M 的模型（prism-ml-ternary-bonsai-27b） | 新用户 $5 赠金未被定价页确认 | together.ai/pricing |
| **AI21** | 第三方称 $10 试用/3 个月 | 官方定价页未直接核实 | ai21.com/pricing |
| **Perplexity** | 免费用户无 API；Pro 订阅含 $5/月 API 额度 | 新 API 账户试用额度 | docs.perplexity.ai |
| **Novita AI** | — | 注册赠金口径混乱（$0.5 / $10），官网定价页无免费说明 | novita.ai/pricing |
| **DeepInfra** | 定价页无免费层/赠金说明 | 不排除注册流程另有赠金 | deepinfra.com/pricing |
| **Replicate** | 定价页按使用付费，无免费层/赠金说明 | — | replicate.com/pricing |

**怎么看这张表**：`已核实事实` 是官网/官方渠道确认过的；`待确认` 是注册前要自己验证的点。这类平台适合「顺手注册占个坑」，**不适合当主力**——等官方明确免费政策再上量。

---

## 八、避坑红名单：17 个别碰（含本月新晋）

以下平台要么**已确认无免费 API**，要么**免费政策已死**，别再浪费时间：

| 平台 | 结论 | 依据 |
|---|---|---|
| **DeepSeek** | 无免费 API，纯按量付费 | 官网定价页已核实 |
| **OpenAI** | 无免费层，新用户须充值 | 官网定价页已核实 |
| **GitHub Models** | **2026-07-30 全面退役** | 官方公告 |
| **xAI Grok** | API 无免费层（$25 促销/数据共享不适用 API） | 官方文档 |
| **Cerebras 免费层** | **8-17 已终结**，转绑卡 $5 信用 | 官网+官方邮件 |
| **无问芯穹 Infini-AI** | **个人服务 6-26 关停** | 官网+媒体报道 |
| **阶跃星辰 Step Plan** | **活动 7-31 截止** | 官网已无入口 |
| **Lepton AI** | 被 NVIDIA 收购，免费 API 已停运 | lepton.ai 核实 |
| **Predibase** | 疑似停服/被收购（跳转 rubrik.com） | 官网核实 |
| **Stability AI** | 无官方免费 API | 仅付费订阅 |
| **Hyperbolic** | 转型 GPU 租赁，免费信息无 | 官网 pricing 404 |
| **Lambda** | 无通用免费层（仅学术赠金） | 官网核实 |
| **Chutes / 302.AI / AiHubMix / API2D** | 纯付费/按需/点数制，无免费额度 | 各自官网核实 |

---

## 九、低成本调用方案：把免费层组一个备用链路

![免费 API 平台选择决策图](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/10-decision.png)

![免费 API 备用链路](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/11-failover.png)

最后给你一个实战方案（也是我自己的用法）：

1. **统一接口层**：上面不少渠道兼容 OpenAI API 格式，但并非全部完全兼容，尤其是视觉、音频、视频和工具调用。使用 LiteLLM 或自建路由时，应逐家验证参数和错误码。
2. **Failover 路由**：主模型 429 / 报错 / 额度耗尽 → 自动切下一家。比如：主用 Groq 跑 gpt-oss-120b，限流了切 SambaNova，再不行切 OpenRouter :free。
3. **分工矩阵**（推荐组合）：
   - **日常对话/推理**：智谱 GLM-4.7-Flash（国内直连）+ Gemini（免费层）+ Groq（速度）
   - **长上下文**：商汤 deepseek-v4-flash（1M，500 次/5h）+ Kimi-k3（1M）
   - **嵌入/检索**：Gemini embedding-2 + 白山 bge-m3 + 硅基 bge 系
   - **语音**：Groq whisper + orpheus TTS、Cloudflare whisper
   - **图像/视频**：智谱 CogView-3-Flash / CogVideoX-Flash、Agnes image/video、商汤 U1 Fast（注意默认水印及活动限制）
   - **代码**：Kimi k2.7-code、Fireworks kimi-k2p7-code、SambaNova DeepSeek-V3.2
4. **额度监控**：各家免费额度在控制台都能查到，写个每日脚本汇总到一张表，快用完自动降级到备用渠道。

这套方案适合个人实验、原型开发和低频备用，不建议直接当作生产系统：免费层可能限流、改价、下线，也通常没有稳定性和服务等级承诺。

### 一个最小的 OpenAI 兼容调用示例

多数兼容 OpenAI 接口的平台，只需要替换 `base_url`、`api_key` 和 `model`：

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

![免费 API 安全使用提醒](/Users/admin/Documents/Codex/2026-08-24/files-mentioned-by-the-user-8/outputs/api-svg/png/12-security.png)

**Q1：注册这么多平台，会不会有安全风险？**
建议使用专用邮箱和独立的支付方式，并遵守平台的注册、验证和使用条款。各家 Key 单独创建，设置额度提醒；不要把生产密钥写进前端、公开仓库或演示代码。

**Q2：免费额度能商用吗？**
分平台。Gemini/智谱/豆包等大厂的免费层一般允许商用（有速率限制），但**使用条款各有细则**；`OpenRouter :free` 部分模型可能用你的数据训练，商用前先读条款。最稳的做法：商用前发邮件问官方要书面确认。

**Q3：为什么我注册后看到的额度跟文章写的不一样？**
三种可能：① 活动已变（免费政策月抛）；② 新老用户政策不同（如硅基流动 2025-11-30 后改为代金券发放）；③ 地域/认证等级不同。**一律以控制台实际显示为准**，这正是文章里反复强调"官网来源可复核"的原因。

**Q4：赠金过期了怎么办？**
赠金类（Kimi 15 元、百川 80 元、千帆 100 万×17）都有有效期，过期不补。技巧：**先注册领了，不着急用**，等真有大活再集中消耗；或者用脚本在过期前把 token 量跑掉。

**Q5：想跑一个 100 万 token 级别的大任务，怎么免费凑够？**
组合拳：豆包（每模型 50 万×12 款）+ 千帆（17 款×100 万）+ 百炼（每模型 100 万）+ 白山（450 元）+ 商汤（1M 上下文×500 次/5h）——按需切模型 ID 轮换，理论上能白嫖跑完千万 token 级别的任务。

**Q6：这些免费模型能力跟付费版差多少？**
大部分免费层就是付费模型本身（如商汤直接上 deepseek-v4-flash 和 glm-5.2），只是限速；少数是"轻量版"（Flash/Lite 后缀）。**结论：跑通业务验证完全够用，上线扛量再充值。**

---

## 结语：免费 API 是月抛生态，用之前看官网

老规矩，最后三句话：

1. **这份清单是 2026-08-24 的快照**。免费政策变动极快——Cerebras 上月还无限免费，这月就终结了；GitHub Models 说退就退。**对接前务必点开官网来源复核**。
2. **优先用 ✅ 永久免费层**，赠金类（一次性/限时）当零食吃，别当主粮。
3. **别碰红名单**——DeepSeek/OpenAI/xAI 没有就是没有，省下的时间够你多薅三家。

**本文整理了 29 个截至核查日值得测试的渠道，并尽量附上官方来源。** 免费政策变化很快，收藏时请同时记下核查日期；如果你发现额度、模型或入口发生变化，建议以官网和控制台为准。

---

## 附录：全部官网来源（按条目挂靠，可直接复核）

**Gemini**

https://ai.google.dev/pricing ✅

**智谱**

https://docs.bigmodel.cn/cn/guide/start/model-overview ✅

**Groq**

https://console.groq.com/docs/rate-limits ✅

**Cloudflare**

https://developers.cloudflare.com/workers-ai/platform/pricing/ ✅

**SambaNova**

https://docs.sambanova.ai/docs/en/models/rate-limits ✅

**Intern AI**

https://internlm.intern-ai.org.cn/doc/docs/模型列表/ ✅

**Agnes AI**

https://agnes-ai.com ✅

**商汤**

https://platform.sensenova.cn/token-plan ✅

**阿里百炼**

https://help.aliyun.com/zh/model-studio/new-free-quota

**火山豆包**

https://docs.volcengine.com/docs/87301/2106521 ✅

**腾讯混元**

https://cloud.tencent.com/document/product/1729/97731/

**百度千帆**

https://ai.baidu.com/ai-doc/WENXINWORKSHOP/3mh3fw81w

**百川**

https://platform.baichuan-ai.com/prices

**Kimi**

https://platform.kimi.com/docs/models ✅（下线公告原文）

**讯飞**

https://www.xfyun.cn/activity_618

**白山智算**

https://ai.baishan.com ✅

**硅基流动**

https://docs.siliconflow.com/cn/faqs/billing-rules ✅

**PPIO**

https://ppio.com/docs/model-api/third-party/anythingllm-use.html ✅

**Fireworks**

https://fireworks.ai/pricing

**Nebius**

https://nebius.com/token-factory/prices ✅

**Mistral**

https://mistral.ai/pricing

**Anthropic**

https://docs.anthropic.com/en/docs/about-claude/pricing

**Azure**

https://azure.microsoft.com/en-us/free/

**OpenRouter**

https://openrouter.ai/models?max_price=0 ✅

**魔搭**

https://www.modelscope.cn/docs/model-service/API-Inference/limits ✅

**扣子 Coze**

https://docs.coze.cn/developer_guides/coze_api_overview ✅

**Hugging Face**

https://huggingface.co/docs/inference-providers/pricing

**NVIDIA NIM**

https://build.nvidia.com/models

**Cohere**

https://docs.cohere.com/docs/rate-limits

**GitHub Models 退役**

https://docs.github.com/en/github-models

**无问芯穹关停**

https://cloud.infini-ai.com + 芯流报道

**完整核实清单**

见《免费大模型API汇总-2026-08》报告附录
