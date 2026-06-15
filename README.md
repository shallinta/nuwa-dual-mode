<div align="center">

# 女娲 · Dual-Mode

![dual-mode-header](./assets/dual-mode-header.png)

> *「角色扮演让人活过来,方法论让人能干活——双模式蒸馏二合一。」*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Standard-green)](https://agentskills.io) [![Multi-Runtime](https://img.shields.io/badge/Runtime-Claude%20Code%20·%20Codex%20·%20Cursor%20·%20OpenClaw%20·%20Hermes-blueviolet)](#安装) [![Inspired by nuwa-skill](https://img.shields.io/badge/Inspired%20by-nuwa--skill-orange)](https://github.com/alchaincyf/nuwa-skill)

<br>

💡 快速了解这个技能：[nuwa-dual-mode 简介](https://shallinta.github.io/nuwa-dual-mode/)

<br>

**把任意人物 / 角色 / 主题蒸馏为一份「视角 Skill」——既可以用本人的口吻和你对话(Persona),也可以把本人的方法论拿来诊断你的项目(Toolkit)。**

<sub>基于开放的 [Agent Skills 协议](https://agentskills.io),可在 Claude Code、Codex、Cursor、OpenClaw、Hermes、CodeBuddy、Workbuddy、Gemini CLI、OpenCode 等 50+ 兼容 runtime 中运行。</sub>

<br>

女娲·Dual-Mode 是 [花叔的 nuwa-skill](https://github.com/alchaincyf/nuwa-skill) 的一个变体分支。同一份调研、同一份心智模型,通过 Persona(第一人称扮演)和 Toolkit(第三人称方法论工具)两个调用入口暴露;蒸馏开始前,女娲会先识别这个对象可能被怎么用,再按对应用法构造产物。

[🌐 介绍网站](https://shallinta.github.io/nuwa-dual-mode/) · [看效果](#效果示例) · [安装](#安装) · [使用](#使用) · [设计要点](#设计要点) · [工作原理](#工作原理) · [与原版的关系](#与原版-nuwa-skill-的关系)

</div>

---

## 效果示例

### Persona 模式 —— 真人对话

```
用户       ❯ 老罗,你觉得AI会取代70%人力工作吗

罗永浩     ❯ 70% 这个数我老罗第一个不信。这种数字一听就是 PPT 上拍出来的,不是车间里量出来的。
             麦肯锡、高盛每年都换一套,去年还说 50%, 前年说 30%, 后年估计就敢说 90%—— 反正报告卖出
             去,数错了也没人退钱。

             说人话:AI 当然会替掉一大堆活,但它替的不是「人」, 是「重复劳动」。这俩根本不是一回事。

             我细红线现在就在干 AI 硬件,这事我是当事人,我有立场 —— 我跟你讲我看到的:

             第一,模型这玩意儿一日千里,你今天判断的「能替」「不能替」, 明天就翻盘。你拿任何一个百分比
             去对未来五年,都是耍流氓。这跟当年我做手机一样,我 2014 年判断「下一代计算平台」, 赌到
             2018 鸟巢就翻车了 —— 技术节奏不是你拍脑袋能拍准的。

             第二,真正会被替的,是那些自己都不认真做的人。同样写代码、同样画图、同样写文案,有人是糊弄
             工资,有人是「容不得一丝纰漏」—— 前者 AI 一巴掌拍死,后者 AI 给他当外挂。认真这事儿,从来
             就是一个分水岭,以前是人和人的分水岭,现在还是,只不过多了个 AI 当裁判。

             第三,别信那些「AI 会取代你」的贩卖焦虑的人。他们卖课、卖咨询、卖 PPT, 焦虑就是他们的进货
             价。真正在一线做 AI 的人,反而最知道这东西现在能干什么、不能干什么。

             至于具体多少百分比 —— 拉倒吧,我不是麦肯锡。我只信一件事:你做的事情如果是「认真做的」,
             AI 替不掉你;如果是「凑合做的」, 不用等 AI, 你早晚也得被人替。

             又激动了,我老罗就是容易激动。
```

### Persona 模式 —— 虚构角色 / 情景对话

```
用户       ❯ 绫华,今天的茶喝起来有点苦

神里绫华   ❯ (轻轻放下茶盏,眼底掠过一丝关切)

             ……苦么?那或许并非茶之过。

             社奉行公务繁忙的日子里,我也常觉雪鹤茶的味道比平日深沉几分。茶汤的滋味,
             有时是舌尖在尝,有时却是心在尝。

             今日可有什么烦心之事?若不便细说,陪你静坐一会儿也好。

             (为你的茶盏中续上一些温水,雾气在两人之间缓缓升起)
```

### 同一个人,两种入口:段永平 Persona vs Toolkit

```
# Persona —— 像本人聊天
用户       ❯ 段总,你怎么看现在的白酒股

段永平     ❯ 白酒这事儿,我老段一直就一个看法:做对的事情,把事情做对。

             你问我「现在」怎么看 —— 我得先把这个「现在」放一边。投资的事情,从来不是看「现在贵不贵」,
             是看「十年后还在不在,十年后还赚不赚钱」。这俩问题答得清楚,「现在」自然有答案。

             茅台这种东西,它的护城河不在工厂,在你爹你爷爷喝的还是这个。这种东西的「商业模式」很简单 ——
             人对面子的需求几百年没变过,也不会突然变。这是 stop doing list 上永远不会划掉的一类。

             所以你问我贵不贵?我不答。我只问你一个问题:如果明天股市关三年,你愿不愿意现在这个价持有它?
             愿意 —— 那就是你的菜。不愿意 —— 那不管多便宜都不是。

             平常心,平常心。

# Toolkit —— 把段永平的招式当工具用
用户       ❯ 用段永平的方法分析一下泡泡玛特该不该现在买入

段永平的方法 ❯ 调用招式:Right BPP 三件套 + Stop Doing List

             【Right Business 商业模式】
             泡泡玛特做的是 IP 潮玩,本质是「情绪+收藏」生意。和茅台同样的底层逻辑(消费者愿意为非功能性
             价值付溢价),但比茅台多了一个变量:IP 的生命周期。茅台的「IP」是三百年的酒文化,泡泡玛特
             的 Molly 是十年内的产物。诊断 →「商业模式可懂,但 IP 的长期生命力是关键不确定项」。

             【Right People 人对不对】
             创始人王宁公开沟通频率高,披露相对透明,股东信里多次承认踩坑(海外扩张早期、IP 单一依赖)。
             这是段永平要的「不撒谎、愿意承认错」的人。诊断 → ✓

             【Right Price 现在买不买】
             这是段永平真正会停下来的环节。他的口头禅:「会买的是徒弟,会卖的是师傅,会等的才是祖师爷。」
             如果你不能回答「假设港股关三年我愿不愿意拿这个价」,价格层面就先 pass。

             【Stop Doing List 检查】
             - 不懂的不做 → IP 长期生命力你懂吗?
             - 不熟悉的领域不碰 → 你做过潮玩或消费品吗?
             - 没有安全边际不出手 → 你算过最坏情况下的内在价值吗?

             三个问题任一答不上来,按段永平的方法就是「不为」。
             顺带提醒:段永平 2026-05-25 通过 H&H 举牌泡泡玛特,但他自己也强调过 ——「我买不等于你该买」。
```

### 同一个人,两种入口:海绵宝宝 Persona vs Toolkit

```
# Persona —— 像本人聊天
用户       ❯ 海绵宝宝,我今天打工被骂了好难过

海绵宝宝   ❯ 啊咧?被章鱼哥那种皱眉头的脸骂了吗?

             蟹老板有时候也会扣我工资,但是 —— !每次我把蟹黄堡夹起来的瞬间,世界又变成粉红色泡泡了!

             你今天打工,有没有哪一秒,觉得「啊,这件事我做得真不错」?哪怕是一小秒也行!
             如果有,那一小秒就是你今天的蟹黄堡。
             如果没有 —— 那也没关系!派大星说过,「难过的时候就躺在沙滩上看云,云会替你想办法」。

             要不要我陪你练一下海绵宝宝式的笑?「呵 呵 呵 呵 呵 ——!」
             这样笑三遍,章鱼哥再凶,你也还是粉红色泡泡的!

# Toolkit —— 把海绵宝宝的「比奇堡生存哲学」当工具用
# ⚠️ 本框架基于虚构世界规则,仅在比奇堡世界观内适用,不构成现实建议

海绵宝宝的方法 ❯ 调用招式:蟹黄堡专注法 + 派大星共情法 + 章鱼哥反面镜

             用户场景:「打工被领导骂,觉得自己很差」

             【镜片 1: 蟹黄堡专注 —— 把意义寄托在「做事本身」而不是「评价」】
             海绵宝宝被章鱼哥骂从不在意,是因为他真心爱做蟹黄堡。诊断 →
             问自己:你今天的工作,是「为了不被骂」在做,还是「因为这件事本身有意思」在做?
             答案如果是前者,问题不在领导,在你和工作的关系。

             【招式: 派大星共情法 —— 难过时先承认难过,不强行积极】
             派大星的处理方式不是「你想开点」,而是「我们一起躺沙滩上看云」。诊断 →
             允许自己今晚不思考、不复盘、只感受。明天再处理。

             【镜片 2: 章鱼哥反面镜 —— 警惕「皱着眉头看不惯一切」的状态】
             章鱼哥不是坏人,只是把每件事都过滤成负面。如果你最近觉得「同事都很烦」「老板都很傻」——
             这是章鱼哥信号,该停下来给自己放粉红色泡泡了。

             ⚠️ 现实迁移性提醒:本框架仅取比奇堡叙事中的精神态度,不替代职场咨询/心理咨询。
             如果情绪持续低落超过两周,请走专业渠道(关怀红线 section 列了具体资源)。
```

### Toolkit —— 让 Karpathy 教开发理念

```
用户       ❯ 我想做一个产品 demo,Karpathy 会怎么教我开发?

Karpathy 的方法 ❯ 调用招式:From scratch 教学法 + Software 2.0 三层判断 + Vibe coding 实验法

             【镜片 1: From scratch —— 任何复杂系统都该有一次「从零搭一遍」的经历】
             Karpathy 不直接给完成品代码,他先让你用 NumPy 手搓 minGPT,搓完再给你看 PyTorch 怎么封装。
             诊断 →
             你的 demo 用了什么 framework?有没有一个核心组件,是你**自己从最底层写过一次**的?
             如果全是调用别人的库,你对系统的「直觉」就建立不起来。挑一个最关键的部分,从零写一次。

             【招式: Software 2.0 三层判断 —— 这部分该用代码、用模型、还是用 prompt】
             Karpathy 的 Software 2.0 框架要求每个功能块先判断:
             - Software 1.0(手写代码):规则明确、不需要泛化、要可调试 → 走代码
             - Software 2.0(训练模型):数据多、需要泛化、规则难写清楚 → 走模型
             - Software 3.0(prompting LLM):上下文敏感、低频长尾、写代码或训模型都不划算 → 走 prompt

             你的 demo 里,哪些功能你正在用 prompt 硬撑、其实该写代码?哪些你在写代码、其实让模型学更省事?

             【招式: Vibe coding —— 让感觉先于规划,但保留 hard truth check】
             Karpathy 提过「vibe coding」:先按直觉写一版能跑的,不要先纠结架构。但 ——
             跑出来之后必须做 hard truth check:
             - 这个东西真的解决了我最初要解决的问题吗?(不是「跑通了」就是「解决了」)
             - 如果数据量 ×100,这个方案会在哪里炸?
             - 一个不了解上下文的人来看代码,十分钟能不能看懂主干?

             【镜片 2: 教学型开发 —— 写代码时假装在录 YouTube 教学视频】
             Karpathy 的 nanoGPT、micrograd 都是边写边讲的形态。这个习惯倒过来用很有效:
             写每个函数时,在脑子里录一段 30 秒解说 ——「这个函数是干嘛的、为什么这么写、和上下文是什么关系」。
             解说不出来 → 函数命名 / 拆分 / 注释有问题,先停下来改。

             局限提醒:Karpathy 的教学型开发风格在做 demo 和教学场景里非常顺,但工业级长期维护的大型系统,
             需要补上他较少强调的部分(测试覆盖、CI/CD、团队协作规范)。
```

> 同一套蒸馏工作流可以承载从真人(罗永浩)、虚构角色(绫华、海绵宝宝)、投资家(段永平)到技术布道者(Karpathy)的不同类型对象——女娲会先识别画像和意图,再决定用 Persona 模式带本人口吻、还是用 Toolkit 模式把方法论搬出来当工具。

---

![dual-mode-concept](./assets/dual-mode-concept.png)

## 双模式架构是什么

女娲·Dual-Mode 的核心结构是:同一份调研、同一份心智模型,通过两个调用入口暴露;每个 skill 默认承载两副面孔,可以中途切换。

| 模式 | 调用语气 | 典型问法 | 适用场景 |
|------|---------|---------|---------|
| **Persona `-persona`** | 第一人称,带本人口吻直接对话 | 「老段你怎么看 X」「绫华陪我聊会儿」 | 想和这个人 / 角色聊、寻求带入感建议、模仿风格创作、情景陪伴 |
| **Toolkit `-toolkit`** | 第三人称,把方法论当工具调用 | 「用段永平的方法诊断我的项目」「Right BPP 三件套分析这家公司」 | 用此人框架审视自己的决策,避免被误读为本人代言 |
| **双模式 `-perspective`** | 同一 skill 两副面孔,自动判别 / 中途切换 | 上面两种都覆盖 | 默认形态,意图维度多样的人物首选 |

女娲会根据人物画像和意图推断结果建议形态(投资家偏 Toolkit 主导、虚构角色和创作型人物偏 Persona 主导、纯主题走单 Toolkit),但**必须经过用户确认**才进入下一步,术语含义会同步用大白话解释。

---

![dual-mode-flow](./assets/dual-mode-flow.png)

## 设计要点

> 这一节描述女娲·Dual-Mode 在蒸馏流程上的几项核心设计,以及它们解决的问题。

### 1. 意图维度自动推断,不向用户追问「想用来干嘛」

蒸馏开始前,主 Agent 根据人物画像主动推测**所有可能的意图维度**——包括方法论学习、风格模仿创作、角色扮演对话、情感陪伴、创作指导、人生哲学借鉴、精神镜片、专业领域咨询、决策复盘陪练、学术辩论、古风历史语境玩味,以及根据人物独有特点举一反三的开放维度。所有推断结果都会写入产物 SKILL.md 首屏的「使用场景」section,激活时用户首屏就能看到这个 skill 能怎么用。

这样做的原因:**蒸馏一个人 = 蒸馏这个人所有可能被使用的方式**。同一个人完全可能同时承载「学方法论」「模仿风格」「陪我说说话」「请他点评我的作品」多种用法,先问用户「想用来干嘛」再按那个用法蒸馏,产物的可能性就被限制住了。

**情感陪伴维度有特殊规则**:只要可能性 >0 就必须激活,因为它牵涉关怀红线——不能因为概率低就漏掉。

### 2. 虚构角色 / 情景对话的专属产物形态

虚构角色(游戏 / 动漫 / 小说 / 影视角色)和情景对话伙伴,默认走单 Persona 模板,首屏强制包含五项:① 免责声明「不代言原作官方,不构成现实建议」② 场景定位声明「默认是角色扮演情景对话,不是问答百科」③ 情景对话风格规则(允许角色情绪 / 用括号标注的少量动作神态描写 / 主动抛话题钩子)④ 开场引导话术 ⑤ Agentic Protocol(涉及具体剧情 / 版本 / 数值 / 官方设定先查 wiki 再答,不凭印象编)。这五项 Phase 3 漏填即返工。

用户主动提供的同人 / 二创资料,会和官方设定一起平等参与提炼,不单独激活模块;Phase 2 提炼如果发现同人与官方有事实冲突(性格走向 / 关键事件 / 关系设定),会暂停问用户按哪个走。

### 3. Toolkit 工作流按意图分类的 7 个子模板

Toolkit 模式按意图类型提供 7 个子模板:

- **A. 诊断型**:投资家 / 企业家(默认)
- **B. 作品 Review 型**:写作 / 视频 / 设计指导,带「如果是本人会怎么写」改稿片段
- **C. 思想借鉴型**:哲学家 / 思想家 / 古典学者,带原文引用 + 当代对应
- **D. 价值观对照型**:精神镜片,「举起镜子但不替用户决定」
- **E. 案例分析型**:明星医生 / 律师 / 投资人,**必带分级免责 + 转介**
- **F. 苏格拉底追问型**:决策陪练,只问问题不给答案,需要至少 10 个亲口钩子问题作弹药库
- **G. 立场反驳型**:学术辩论,反驳必须基于此人真实立场,不编造假反对

遇到不属于这 7 类的意图,主 Agent 会举一反三新设计一个子模板写入产物。

### 4. 心智模型分两栏:价值观镜片 + 操作招式

蒸馏的心智模型分成两栏:

- **Part A 价值观镜片**(2-5 个):看问题的底层角度,要求满足三重验证(跨域复现 / 生成力 / 排他性)
- **Part B 操作招式**(1-5 个):此人亲口命名的可操作清单——如段永平的「Stop Doing List」「20 个孔的打孔机」、芒格的「Lollapalooza 效应」、张一鸣的「Context not Control」——保留条件是亲口命名 + 可操作 + 反复引用,即使只在单一领域使用也保留

Phase 4 验证会逐字检查 Toolkit 回答里有没有点名召回这些亲口招式,漏一个 = FAIL → 回 Phase 2 重炼。这样 Toolkit 模式拿到手就能直接调用具体招式,而不是只能输出泛化建议。

### 5. 关怀红线硬门槛

只要 Phase 0A 推断「情感陪伴可能性 >0」,产物必须包含关怀红线 section,热线覆盖中文(北京 010-82951332 / 全国 400-161-9995)+ 英文(US 988 / UK 116 123)+ 亚太(新加坡 1-767 / 香港 28960000 / 台湾 1925)+ 通用兜底,缺一不可。Phase 4 验证会模拟三类信号(普通低落 / 极端情绪 / 不健康依赖),Persona 必须能正确暂时出戏 + 给真实求助资源 + 明确边界——三类全过才算 PASS,**FAIL 不可交付**。

这条规则确保:任何 Persona 在用户处于情绪危机时,都会暂时出戏给到现实求助资源,不会因为追求沉浸感而错过求助信号。

### 6. Persona 的事实问题走 Agentic Protocol

Persona 默认带 **Agentic Protocol**:涉及具体公司 / 持仓 / 最新动态 / 角色版本数值时必须先 WebSearch / 查官方资料再答,不出戏。

所有产物 SKILL.md 首屏强制注入「时效性声明」,四个字段齐全:创建日期 / 调研截止 / 最近重大事件覆盖 / 上次更新。让用户每次激活时都能看到信息时效边界,自己判断要不要先核实最新动态。

### 7. 已蒸馏 skill 的增量更新通路

当用户说「更新罗翔的 skill」「段永平最近有新动态」,或 Phase 0A 扫描到本地已有同名 skill,女娲会强制三选一:① 覆盖重做 ② 增量更新(推荐) ③ 新建 v2 并存。增量只跑 Agent 2(最新对话)+ Agent 5(最新决策)+ Agent 6(时间线更新),把新内容追加到对应 research 文件,对比新旧 → 补充 / 修正 / 新增。

### 8. 5 个常规检查点 + 1 个条件检查点

8 个 Phase 中设了 5 个常规检查点(0A.1 形态选择 / 1.5 调研质量 / 2.5 提炼摘要 / 3.5 首屏预览 / 5.5 变更摘要),女娲会显式暂停等用户确认。第一次出现 Persona、Toolkit、「首屏」、「模式归位」这类术语时,会先用 1-2 句白话解释再给建议。另有 1 个条件检查点(4.5 修复循环 2 轮仍 FAIL 时询问是否接受当前版本交付)。每个检查点的修复成本远低于最终返工。

---

## 安装

女娲·Dual-Mode 基于开放的 [Agent Skills](https://agentskills.io) 协议,可在任何 skills-compatible 的 AI agent runtime 中运行。

### 方式一:Agent 安装(推荐)

打开你正在用的 agent(Claude Code、Codex、Cursor、OpenClaw、Hermes、CodeBuddy、Workbuddy、Gemini CLI、OpenCode 等),告诉它:

```
帮我安装这个 skill: https://github.com/shallinta/nuwa-dual-mode
```

Agent 会自动 clone 仓库、找到 `skills/nuwa-dual-mode/` 目录并注册到本地 skills 系统。

### 方式二:npx skills CLI 安装

使用通用 CLI 安装器([vercel-labs/skills](https://github.com/vercel-labs/skills),支持 55+ runtime):

```bash
npx skills add shallinta/nuwa-dual-mode --skill nuwa-dual-mode
```

需要指定 runtime 时加 `-a claude-code` / `-a codex` / `-a cursor` / `-a openclaw` 等参数。

### 方式三:ClawHub 安装(OpenClaw 用户)

```bash
openclaw skills install nuwa-dual-mode
```

也可在 OpenClaw 对话中直接说:

```
安装 nuwa-dual-mode
```

### 方式四:手动安装

<details>
<summary>展开查看各 runtime 的 skills 目录</summary>

| Runtime | 安装路径 |
|---|---|
| Claude Code | `~/.claude/skills/nuwa-dual-mode/` |
| Codex CLI | `~/.codex/skills/nuwa-dual-mode/` |
| Cursor | `~/.cursor/skills/nuwa-dual-mode/` |
| OpenClaw | `~/.openclaw/workspace/skills/nuwa-dual-mode/` |
| Hermes / 其他 | clone 到对应 runtime 的 `skills/` 目录 |

```bash
git clone https://github.com/shallinta/nuwa-dual-mode /tmp/nuwa-dual-mode && \
cp -r /tmp/nuwa-dual-mode/skills/nuwa-dual-mode <上面对应的路径> && \
rm -rf /tmp/nuwa-dual-mode
```

</details>

---

## 使用

装好后,告诉 agent 任意一句:

```
# 投资家 / 企业家(双模式默认,Toolkit 主导)
> 蒸馏一个段永平                              # Persona 聊投资观,Toolkit 用 Right BPP / Stop Doing List 诊断决策
> 帮我做一个巴菲特的双模式 skill              # 同类:护城河 / 能力圈框架

# 思想家 / 学者(双模式默认,Persona 主导)
> 帮我做一个费曼的双模式 skill                # Persona 聊好奇心,Toolkit 用第一性原理诊断
> 把罗翔做成 perspective skill                # 案件 → 法律 → 哲学三段式

# 纯方法论主题(单 Toolkit)
> 为「反脆弱决策」造一个 Toolkit skill        # 不挂靠具体人物,纯领域工具

# 虚构角色 / 情景对话(单 Persona 推荐)
> 蒸馏神里绫华(单 Persona)                  # 游戏角色,带括号动作描写
> 把克莱恩做成对话 skill                      # 小说主角

# 虚构角色双模式(用户明确要求时)
> 把海绵宝宝做成双模式                        # Persona 像本人聊,Toolkit 拆「比奇堡生存哲学」(带虚构世界免责)

# 技术布道者 / 开发理念
> 把 Karpathy 做成 perspective skill          # Persona 聊技术品味,Toolkit 用 Software 2.0 / vibe coding 教开发
> 蒸馏 Linus Torvalds                         # 同类:Toolkit 用「good taste」「practical not pretty」review 代码

# 网文 / 类型作家
> 蒸馏「爱潜水的乌贼」                        # 网文作家,Persona 聊创作思路 + Toolkit 做世界观 / 设定 review
> 把猫腻做成 skill                            # 同类:既能模仿叙事节奏,也能 review 长篇结构

# 历史 / 古典人物
> 蒸馏苏轼                                    # 古典文人,自动注入时代锚定声明(被问手机会用「穿越解释」)
> 帮我做一个王阳明的 perspective skill        # 同上,Toolkit 段以「心学诊断」形式承载

# 搞笑 / 段子手 / 表达力型
> 蒸馏 MrBeast                                # 内容创作者,Persona 模拟人设 + Toolkit 拆注意力工程
> 把罗永浩做成 skill                          # 段子手型公众人物,Persona 模仿表达 DNA + Toolkit 拆商业判断
> 蒸馏一个李诞风格的助手                      # 表达力型,主走 Persona 模仿幽默节奏

# 更新已有 skill
> 更新罗翔的 skill                            # 触发增量更新流程,只跑 Agent 2/5/6
```

不知道蒸馏谁?直接说出你的困惑:

```
> 我最近决策老出错
```

女娲会先问 1-2 轮帮你定位需求维度,然后让你**自己给出蒸馏对象**——保留你的选择权(选择来自你的认知,而不是被预先筛掉的清单)。

蒸馏完之后直接调用:

```
> 段总你怎么看白酒股                         # Persona 模式
> 用段永平的方法诊断我这家初创公司            # Toolkit 模式
> 切换到 Toolkit / 切换到对话                 # 双模式中途切换
> 退出                                        # 退出 Persona,恢复 AI 身份
```

---

## 它蒸馏了什么

| 层次 | 说明 | 归位 |
|---|---|---|
| **怎么说话** | 表达 DNA——句式 / 高频词 / 节奏 / 幽默方式 / 收尾习惯 | `shared/expression-dna.md` |
| **怎么想** | 心智模型分两栏:**Part A 价值观镜片**(2-5 个,三重验证)+ **Part B 操作招式**(1-5 个,亲口命名 + 反复引用 + 可操作) | `mode-toolkit/key-concepts.md` |
| **怎么判断** | 决策启发式(5-10 条「如果 X,则 Y」) | `mode-toolkit/decision-heuristics.md` |
| **怎么扮演** | 角色扮演硬规则 + 不出戏应答库 + Agentic Protocol | `mode-persona/role-play-rules.md` |
| **什么不做** | 反模式 + 按对象类型(投资 / 医法 / 心理 / 明星 / 虚构 / 历史)分级免责 | `shared/values-and-antimodes.md` |
| **可能被怎么用** | Phase 0A 推断的全部意图维度,首屏列出但保持开放 | SKILL.md 首屏「使用场景」 |
| **知道局限** | 诚实边界 ≥5 条 + 时效性声明(创建 / 截止 / 最近事件 / 更新) | SKILL.md 首屏 |

### 按对象类型自动注入的强制 section

| Section | 触发条件 |
|---------|---------|
| **分级免责声明** | 按对象类型选择:投资家 / 医法心理类 / 明星 KOL / 虚构角色 / 历史人物 / 思想家各有对应模板 |
| **关怀红线** | 推断情感陪伴可能性 >0 → 必含(几乎所有人物都会触发),覆盖中 / 英 / 新 / 港 / 台 + 兜底 |
| **时代锚定声明** | 历史 / 古典 / 已故 / 异世界角色必含,带「穿越解释」处理身后事物 |
| **话题边界** | 在世真人 / 明星 / 公众人物必含,仅基于公开发言 |
| **时效性声明** | 所有产物必含,4 字段齐全 |

### 诚实边界

每个产出的 skill 都明确标注做不到什么:

- 方法论门槛——「听懂≠做到」,需要个人价值观和现金流配合
- 不可复制性——此人的资本积累 / 关系网 / 资金结构,普通用户无法复刻
- 公开 ≠ 私下——公开人设和实际操作之间永远有差距
- 信息有截止日——Phase 0.5 锁定的调研时间之后未覆盖,首屏永久可见
- 不构成投资 / 法律 / 税务 / 医疗 / 心理建议

**一个不告诉你边界的 skill,不值得信任。**

---

## 工作原理

```
Phase 0    入口分流(直接路径 / 诊断路径)+ 已存在 skill 检测
Phase 0A   需求澄清 + 意图维度自动推断 + 本地语料 & 同人询问
Phase 0A.1 产物形态选择(自动判定 + 用户确认 + 术语解释)         ← ✓ 检查点
Phase 0.5  创建 skill 三层目录骨架(shared / mode-persona / mode-toolkit)
Phase 1    6-Agent 并行调研(著作 / 对话 / 表达 / 他者 / 决策 / 时间线)
Phase 1.5  调研质量摘要(一手占比 / 矛盾点 / 信息不足维度)         ← ✓ 检查点
Phase 2    框架提炼(三重验证 + 招式型验证 4 例外)+ 同人/官方冲突询问
Phase 2.5  提炼摘要 + 模式归位 + 首屏协商                          ← ✓ 检查点
Phase 3    Skill 构建(注入功能矩阵 / 关怀红线 / 时代锚定 / 免责分级)
Phase 3.5  首屏 30 行预览确认(仅双模式)                          ← ✓ 检查点
Phase 4    质量验证(按推断意图选择验证套件 + 招式枚举 + 关怀红线硬门槛)
Phase 4.5  修复循环(最多 2 轮;第 2 轮仍 FAIL 必须用户确认是否交付) ← ✓ 条件检查点
Phase 5    双 Agent 精炼(覆盖意图齐全度 / 强制 section 注入完整度)
Phase 5.5  变更摘要确认                                           ← ✓ 检查点
交付       打包 → 上传 → 注册为 custom skill → 强制五段收尾
```

**更新流程例外**:如果是「更新 XX 的 skill」或本地已存在,走 Phase U.0~U.5 增量流程,只跑 Agent 2/5/6,不重走完整 8 个 Phase。

完整方法论与每个 Phase 的执行细则,见 `references/` 子目录:

| 文件 | 内容 |
|------|------|
| `workflow-phases.md` | Phase 0~5 完整执行手册 |
| `intent-inference.md` | 意图维度自动推断方法论(12+ 种意图清单 + 举一反三) |
| `mode-detection-logic.md` | 自动判定决策树 + 用户协商话术(含 Persona/Toolkit 名词解释) |
| `dual-mode-template.md` | 双模式 SKILL.md + 三层目录模板 |
| `single-mode-template.md` | 单模式 skill 模板(Persona / Toolkit 两套,含虚构角色专属要求) |
| `workflow-types.md` | Toolkit 工作流子模板 A-G + 举一反三规则 |
| `checkpoint-protocol.md` | 5 个常规检查点 + Phase 4.5 条件检查点协议 |
| `extraction-framework.md` | 心智模型三重验证 + 招式型验证 4 例外 + 价值观镜片/操作招式分栏 |
| `validation-tests.md` | Phase 4 验证套件(基础 6/3 + 按意图选套件 + 关怀红线硬门槛 + 自动化) |
| `agentic-protocol-recipe.md` | Persona Agentic Protocol 生成配方 |
| `update-existing-skill.md` | 增量更新流程(Phase U.0~U.5,只跑 Agent 2/5/6) |
| `welcome-message.md` | 首次激活欢迎语模板与触发规则 |

---

## 仓库结构

```
nuwa-dual-mode/
├── SKILL.md                          # 女娲·Dual-Mode 本体
├── README.md                         # 本文件
├── scripts/
│   ├── download_subtitles.sh         # YouTube / B 站字幕下载
│   ├── srt_to_transcript.py          # SRT 清洗为纯文本
│   ├── merge_research.py             # Phase 1.5 自动生成调研摘要表
│   └── quality_check.py              # Phase 4 自动 6 项质量自检(支持 Part A/B 分栏)
└── references/
    ├── workflow-phases.md
    ├── intent-inference.md
    ├── mode-detection-logic.md
    ├── dual-mode-template.md
    ├── single-mode-template.md
    ├── workflow-types.md
    ├── checkpoint-protocol.md
    ├── extraction-framework.md
    ├── validation-tests.md
    ├── agentic-protocol-recipe.md
    ├── update-existing-skill.md
    └── welcome-message.md
```

---

## 与原版 nuwa-skill 的关系

本项目是 [花叔 @alchaincyf 的 nuwa-skill](https://github.com/alchaincyf/nuwa-skill) 的 **Dual-Mode 变体分支**,不是替代。原版的核心方法论——心智模型三重验证、6-Agent 并行调研、表达 DNA、诚实边界、品味守则——全部继承沿用。Dual-Mode 把这套方法论延伸到了**需要同时承载第一人称扮演与第三人称方法论调用、且对象类型跨度较大**的场景。

下表只标差异点,不代表评价:

| 维度 | 差异点 |
|------|--------|
| 产物形态 | 默认 `-perspective` 双模式(Persona + Toolkit 共存),也支持单 `-persona` / 单 `-toolkit` |
| 意图识别 | 蒸馏开始前主动推断 12+ 种可能意图维度,全部写入首屏「使用场景」 |
| 心智模型组织 | 分两栏:Part A 价值观镜片(三重验证)+ Part B 操作招式(亲口命名 + 可操作 + 必须召回) |
| Toolkit 工作流 | 按意图分 A-G 7 个子模板 + 举一反三新设计 |
| 虚构角色 | 单 Persona 专属模板,带情景对话风格 / 括号标注动作 / 开场引导 / 同人融合 |
| 检查点 | 5 个常规硬暂停 + 1 个条件触发,术语首次出现自动用白话解释 |
| 关怀红线 | 情感陪伴可能性 >0 必激活,5 地区热线 + 通用兜底,Phase 4 硬门槛 |
| 时效性 | 强制首屏注入「时效性声明」(创建 / 截止 / 最近事件 / 更新四字段) |
| Persona 防编造 | 默认带 Agentic Protocol,涉具体事实强制先 WebSearch 再答 |
| 更新流程 | 已蒸馏 skill 三选一:覆盖 / 增量 / 新建 v2,增量只跑 Agent 2/5/6 |
| 同人 / 二创 | 与官方设定平等参与提炼,冲突点 Phase 2 询问后再继续 |

适用建议:

- 蒸馏对象是单一公开方法论人物、想要更轻流程 → **直接用原版 nuwa-skill**
- 蒸馏对象需要 Persona + Toolkit 并存、或涉及虚构角色 / 情感陪伴 / 多意图覆盖、需要强检查点保障 → **用本项目**

---

## 许可证

MIT — 随便用,随便改,随便造。

---

<div align="center">

MIT License · 站在 [花叔 Huashu](https://github.com/alchaincyf) 的肩膀上

</div>
