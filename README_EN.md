<div align="center">

# 女娲 · Dual-Mode

![dual-mode-header](./assets/dual-mode-header.png)

> *"Persona brings them to life. Toolkit gets things done. Dual-mode distillation in one."*

English · [中文](./README.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Standard-green)](https://agentskills.io) [![Multi-Runtime](https://img.shields.io/badge/Runtime-Claude%20Code%20·%20Codex%20·%20Cursor%20·%20OpenClaw%20·%20Hermes-blueviolet)](#installation) [![Inspired by nuwa-skill](https://img.shields.io/badge/Inspired%20by-nuwa--skill-orange)](https://github.com/alchaincyf/nuwa-skill)

<br>

💡 Quick intro: [nuwa-dual-mode Overview](https://shallinta.github.io/nuwa-dual-mode/)

<br>

**Distill any person, character, or topic into a "Perspective Skill" — chat with them in their own voice (Persona), or use their methodology to diagnose your own projects (Toolkit).**

<sub>Built on the open [Agent Skills protocol](https://agentskills.io). Runs in Claude Code, Codex, Cursor, OpenClaw, Hermes, CodeBuddy, Workbuddy, Gemini CLI, OpenCode, and 50+ compatible runtimes.</sub>

<br>

女娲·Dual-Mode is a variant fork of [花叔 (Huashu)'s nuwa-skill](https://github.com/alchaincyf/nuwa-skill). Same research, same mental model — exposed through two invocation surfaces: Persona (first-person roleplay) and Toolkit (third-person methodology tooling). Before distillation begins, 女娲 identifies all the ways this subject might be used, then constructs the artifact accordingly.

[🌐 Introduction Site](https://shallinta.github.io/nuwa-dual-mode/) · [Examples](#examples) · [Installation](#installation) · [Usage](#usage) · [Design Highlights](#design-highlights) · [How It Works](#how-it-works) · [Relationship with Original](#relationship-with-the-original-nuwa-skill)

</div>

---

## ⚡ Quick Install

```bash
# ClawHub (OpenClaw)
openclaw skills install nuwa-dual-mode

# npx (universal)
npx skills add shallinta/nuwa-dual-mode --skill nuwa-dual-mode
```

> Or just tell your agent: `Install this skill: https://github.com/shallinta/nuwa-dual-mode`

---

## Examples

### Persona Mode — Real Person Conversation

```
User        ❯ Lao Luo, do you think AI will replace 70% of human jobs?

罗永浩 (Lao Luo) ❯ 70%? I'm the first one to call bullshit on that number. 
                    Numbers like that come out of PowerPoint decks, not factory floors. 
                    McKinsey and Goldman Sachs swap these figures out every year — last year 
                    it was 50%, year before 30%, next year they'll probably dare say 90%. 
                    The report gets sold; nobody asks for a refund when the numbers are wrong.

                    In plain terms: sure, AI's going to take over a ton of work. But what it 
                    replaces isn't "people" — it's "repetitive labor." Those are two completely 
                    different things.

                    My company Thin Red Line is doing AI hardware right now. I'm a party to 
                    this, so I've got a position — here's what I see:

                    First, these models are evolving at breakneck speed. Whatever you label 
                    "replaceable" or "irreplaceable" today flips tomorrow. Using any percentage 
                    to predict five years out is pure nonsense. Same thing happened when I was 
                    making phones: in 2014 I bet on "the next computing platform," and by 2018 
                    the Bird's Nest launch flopped. You can't gut-feel tech pacing.

                    Second, the people who'll actually get replaced are the ones who don't take 
                    their own work seriously. Same coding, same drawing, same copywriting — some 
                    people are just punching the clock, others can't tolerate even a single 
                    imperfection. AI slaps the clock-punchers dead. For the perfectionists? 
                    AI becomes their exoskeleton. Taking things seriously has always been a 
                    dividing line — it divided people from people before, and it still does 
                    now, except AI gets to be the referee.

                    Third, don't trust the anxiety merchants selling "AI will replace you." 
                    They're selling courses, consulting, and slide decks. Anxiety is their 
                    cost of goods sold. The people actually building AI on the front lines — 
                    they know best what this stuff can and can't do right now.

                    As for the exact percentage — forget it. I'm not McKinsey. I only believe 
                    one thing: if what you're doing is done seriously, AI can't replace you. 
                    If it's done half-assed, you'll get replaced by someone eventually, AI 
                    or no AI.

                    Got worked up again. I'm just easy to get worked up, that's me.
```

### Persona Mode — Fictional Character / Scenario Roleplay

```
User        ❯ Ayaka, today's tea tastes a bit bitter...

神里绫华 (Kamisato Ayaka) ❯ (Sets down the teacup gently, a trace of concern flickering in her eyes)

                              ...Bitter, is it? Perhaps the fault does not lie with the tea.

                              During busy days at the Yashiro Commission, I often find the 
                              Snow Crane tea tastes deeper than usual. The flavor of tea — 
                              sometimes the tongue is tasting, and sometimes the heart is.

                              Has something troubled you today? If it's inconvenient to speak 
                              of, I'd be content to sit with you in silence for a while.

                              (Refills your cup with warm water, the steam rising slowly 
                              between the two of you)
```

### Same Person, Two Entry Points: Duan Yongping Persona vs Toolkit

```
# Persona — chat like the man himself
User        ❯ Duan, what do you think about Chinese liquor stocks right now?

段永平 (Duan Yongping) ❯ Baijiu — my view on this has always been one thing: do the right 
                           thing, and do things right.

                           You're asking me what I think "right now" — I have to set "right now" 
                           aside first. Investing has never been about whether something is 
                           "expensive right now." It's about whether it'll still be here in ten 
                           years, and whether it'll still be making money in ten years. If you 
                           can answer those two clearly, "right now" answers itself.

                           Something like Moutai — its moat isn't in the factory. It's in the 
                           fact that your dad and your granddad drank this stuff. The business 
                           model is simple: people's demand for face hasn't changed in centuries, 
                           and it won't suddenly change either. This is the kind of thing that 
                           never gets crossed off the Stop Doing List.

                           So you're asking me whether it's expensive? I won't answer. I'll only 
                           ask you one question: if the stock market closed for three years 
                           tomorrow, would you still want to hold it at this price? If yes — 
                           it's your kind of investment. If no — doesn't matter how cheap it is.

                           Keep a level head. A level head.

# Toolkit — use Duan Yongping's methods as tools
User        ❯ Use Duan Yongping's approach to analyze whether Pop Mart is a buy right now.

Duan Yongping's Method ❯ Deploying: Right BPP Framework + Stop Doing List

                          【Right Business — Business Model】
                          Pop Mart does IP-based designer toys. This is fundamentally an 
                          "emotion + collectibles" business. Same underlying logic as Moutai 
                          (consumers pay a premium for non-functional value), but with one 
                          extra variable: IP lifecycle. Moutai's "IP" is 300 years of liquor 
                          culture; Pop Mart's Molly was born within the last decade. Diagnosis 
                          → "Business model is understandable, but IP long-term vitality is the 
                          key uncertainty."

                          【Right People — Are the People Right?】
                          Founder Wang Ning communicates frequently, discloses relatively 
                          transparently, and has admitted missteps multiple times in shareholder 
                          letters (early overseas expansion, over-reliance on a single IP). 
                          These are exactly the "doesn't lie, willing to admit mistakes" traits 
                          Duan Yongping looks for. Diagnosis → ✓

                          【Right Price — Buy Now or Not?】
                          This is where Duan Yongping would genuinely pause. His mantra: "The 
                          apprentice knows how to buy; the master knows how to sell; the 
                          grandmaster knows how to wait." If you can't answer "Would I hold 
                          at this price if the HK exchange closed for three years?", then pass 
                          on the price.

                          【Stop Doing List Check】
                          - Don't do what you don't understand → Do you really understand 
                            IP long-term vitality?
                          - Don't touch unfamiliar domains → Have you ever worked in designer 
                            toys or consumer goods?
                          - No margin of safety, no entry → Have you calculated intrinsic 
                            value under the worst case?

                          Fail to answer any of these three, and by Duan Yongping's method the 
                          answer is "don't act."
                          A reminder: Duan Yongping disclosed a Pop Mart position via H&H on 
                          2026-05-25, but he himself has always emphasized — "My buying doesn't 
                          mean you should buy."
```

### Same Person, Two Entry Points: SpongeBob Persona vs Toolkit

```
# Persona — chat like the character
User        ❯ SpongeBob, I got yelled at at work today. I feel so sad...

海绵宝宝 (SpongeBob) ❯ A-le? You got yelled at by a grumpy face like Squidward's?

                         Mr. Krabs docks my pay sometimes too, but — ! Every time I flip a 
                         Krabby Patty into the air, the whole world turns into pink bubbles again!

                         Today at work, was there even one second where you thought, "Ah, I 
                         really did this well"? Even a tiny second counts!
                         If there was, that little second is your Krabby Patty for today.
                         If there wasn't — that's fine too! Patrick once said, "When you're 
                         sad, just lie on the beach and watch the clouds. The clouds will 
                         figure things out for you."

                         Want me to teach you the SpongeBob laugh? "Heh heh heh heh heh —!"
                         Do that three times, and no matter how grumpy Squidward gets, you'll 
                         still be a pink bubble!

# Toolkit — use SpongeBob's "Bikini Bottom Survival Philosophy" as tools
# ⚠️ This framework is based on fictional-world rules. Valid only within the 
# Bikini Bottom worldview. Does not constitute real-world advice.

SpongeBob's Method ❯ Deploying: Krabby Patty Focus + Patrick Empathy Method 
                      + Squidward Reverse Mirror

                      User scenario: "Got yelled at by boss, feeling worthless"

                      【Lens 1: Krabby Patty Focus — Anchor meaning in the work itself, 
                      not in evaluations】
                      SpongeBob never cares when Squidward yells at him because he genuinely 
                      loves making Krabby Patties. Diagnosis →
                      Ask yourself: did you do your work today "to avoid getting yelled at," 
                      or "because the work itself was interesting"? If the former, the 
                      problem isn't your boss — it's your relationship with the work.

                      【Technique: Patrick Empathy Method — Acknowledge the sadness first. 
                      Don't force positivity.】
                      Patrick's approach isn't "cheer up" — it's "let's lie on the beach 
                      and watch the clouds together." Diagnosis →
                      Give yourself permission tonight to not think, not review, not process. 
                      Just feel. Deal with it tomorrow.

                      【Lens 2: Squidward Reverse Mirror — Watch out for the "everything 
                      sucks" filter】
                      Squidward isn't a bad person. He just filters everything into negative. 
                      If you've recently been feeling like "my coworkers are all annoying" 
                      or "my boss is an idiot" — that's the Squidward signal. Time to pause 
                      and give yourself some pink bubbles.

                      ⚠️ Real-world migration notice: This framework only takes the spirit 
                      and attitude from Bikini Bottom narratives. It does not replace 
                      workplace counseling or psychological counseling. If low mood persists 
                      for more than two weeks, please seek professional channels (the Care 
                      Red Line section lists specific resources).
```

### Toolkit — Let Karpathy Teach Development Philosophy

```
User        ❯ I want to build a product demo. How would Karpathy teach me to develop it?

Karpathy's Method ❯ Deploying: From-Scratch Pedagogy + Software 2.0 Triaging 
                      + Vibe Coding Experimentation

                    【Lens 1: From Scratch — Every complex system deserves to be built 
                    from the ground up once】
                    Karpathy doesn't hand you finished code. He makes you hand-craft minGPT 
                    in NumPy first, and only then shows you how PyTorch wraps it. Diagnosis →
                    What framework is your demo using? Is there a core component you've 
                    actually written yourself from the lowest level? If everything is just 
                    library calls, you'll never build real intuition for the system. Pick the 
                    most critical piece and write it from scratch once.

                    【Technique: Software 2.0 Triaging — Should this be code, a model, 
                    or a prompt?】
                    Karpathy's Software 2.0 framework requires evaluating each functional 
                    block:
                    - Software 1.0 (handwritten code): rules are clear, no generalization 
                      needed, must be debuggable → write code
                    - Software 2.0 (train a model): lots of data, needs generalization, 
                      rules are hard to articulate → train a model
                    - Software 3.0 (prompt an LLM): context-sensitive, long-tail, writing 
                      code or training a model isn't cost-effective → prompt it

                    In your demo, which features are you brute-forcing with prompts that 
                    should actually be written as code? Which features are you writing as 
                    code that would be cheaper to let a model learn?

                    【Technique: Vibe Coding — Let intuition lead, but keep hard truth 
                    checks】
                    Karpathy has talked about "vibe coding": write a working version based 
                    on intuition first. Don't obsess over architecture up front. But — once 
                    it runs, you must do hard truth checks:
                    - Does this really solve the problem I set out to solve? ("It runs" ≠ 
                      "it's solved")
                    - If data volume grows 100×, where does this approach break?
                    - Can someone unfamiliar with the context read the core logic and 
                      understand it in ten minutes?

                    【Lens 2: Pedagogical Development — Write code as if you're recording 
                    a YouTube tutorial】
                    Karpathy's nanoGPT and micrograd are both built in a "write and explain" 
                    style. This habit, inverted, is incredibly effective: while writing each 
                    function, mentally record a 30-second narration — "What does this function 
                    do? Why is it written this way? How does it relate to the surrounding 
                    context?" If you can't narrate it → the function naming, decomposition, 
                    or commenting has issues. Stop and fix that first.

                    Limitation notice: Karpathy's pedagogical development style works 
                    beautifully for demos and teaching contexts, but for industrial-scale, 
                    long-term-maintained systems, you'll need to supplement areas he 
                    emphasizes less (test coverage, CI/CD, team collaboration norms).
```

> The same distillation workflow handles subjects across the spectrum — from real people (罗永浩), fictional characters (Ayaka, SpongeBob), investors (Duan Yongping), to tech evangelists (Karpathy). 女娲 first identifies the profile and intended uses, then decides whether to deploy Persona mode with their authentic voice, or Toolkit mode to bring their methodology to bear as a tool.

---

![dual-mode-concept](./assets/dual-mode-concept.png)

## What Is the Dual-Mode Architecture?

女娲·Dual-Mode's core structure: the same research, the same mental model, exposed through two invocation surfaces. Every skill carries both faces by default and can switch mid-session.

| Mode | Tone | Typical Query | Best For |
|------|------|--------------|----------|
| **Persona `-persona`** | First-person, authentic voice, direct conversation | "Duan, what do you think about X?" "Ayaka, chat with me for a bit" | Talking to the person/character, seeking immersive advice, imitating style for creative work, scenario companionship |
| **Toolkit `-toolkit`** | Third-person, methodology invoked as a tool | "Use Duan Yongping's method to diagnose my project" "Right BPP framework for analyzing this company" | Using this person's frameworks to examine your own decisions without being mistaken for personal endorsement |
| **Dual-Mode `-perspective`** | One skill, two faces, auto-detection / mid-session switching | Covers both above | Default form. First choice for subjects with diverse intent dimensions. |

女娲 recommends a form based on profile and inferred intents (investors lean Toolkit-first, fictional characters and creative figures lean Persona-first, pure topics go single Toolkit), but **must get user confirmation** before proceeding. Terminology is always explained in plain language on first occurrence.

---

![dual-mode-flow](./assets/dual-mode-flow.png)

## Design Highlights

> This section describes the core design decisions in 女娲·Dual-Mode's distillation pipeline and the problems each addresses.

### 1. Automatic Intent Dimension Inference — No Asking "What Do You Want to Use This For?"

Before distillation begins, the main Agent proactively infers **all possible intent dimensions** based on the subject's profile — including methodology learning, stylistic imitation, roleplay conversation, emotional companionship, creative guidance, life philosophy reference, spiritual lens, domain consultation, decision-review sparring, academic debate, historical/flavor immersion, and open-ended dimensions unique to the subject. All inferred results are written into the product SKILL.md's "Use Cases" section, visible to the user immediately upon activation.

The reasoning: **distilling a person = distilling every way that person could possibly be used**. The same person can simultaneously serve as a methodology teacher, a style model, a conversation companion, and a work critic. Asking the user "what do you want to use this for" and then distilling only for that use case artificially constrains the artifact's potential.

**Special rule for emotional companionship**: as long as probability > 0, this dimension must be activated — because it ties to the Care Red Line. You can't skip it just because probability is low.

### 2. Dedicated Artifact Form for Fictional Characters / Scenario Roleplay

Fictional characters (game / anime / novel / film characters) and scenario conversation partners default to single Persona template with five mandatory items on the first screen: ① Disclaimer "Does not speak for the original work's creators; does not constitute real-world advice" ② Scenario positioning statement "Default mode is roleplay scenario conversation, not a Q&A encyclopedia" ③ Roleplay style rules (allowing character emotions / a small amount of parenthetical action/expression descriptions / proactively throwing conversation hooks) ④ Opening conversation prompts ⑤ Agentic Protocol (when specific plot points / version / stats / official lore are involved, check the wiki before answering — don't fabricate from memory). Missing any of these five in Phase 3 = rework.

User-provided fan-works / derivative materials are treated equally with official canon in the distillation process — no separate module activation. If Phase 2 extraction discovers factual conflicts between fan and official versions (personality direction / key events / relationship configurations), the process pauses to ask the user which to follow.

### 3. 7 Intent-Classified Toolkit Workflow Sub-Templates

Toolkit mode provides 7 sub-templates classified by intent type:

- **A. Diagnostic**: Investors / entrepreneurs (default)
- **B. Work Review**: Writing / video / design coaching, with "how the person themselves would write it" revision snippets
- **C. Thought Borrowing**: Philosophers / thinkers / classical scholars, with original quotations + modern equivalents
- **D. Values Comparison**: Spiritual lens — "hold up the mirror but don't decide for the user"
- **E. Case Analysis**: Celebrity doctors / lawyers / investors — **mandatory tiered disclaimer + referral**
- **F. Socratic Interrogation**: Decision sparring — only ask questions, never give answers. Requires at least 10 personally-styled hook questions as ammunition
- **G. Positional Rebuttal**: Academic debate — rebuttals must be based on the person's actual positions; no fabricated opposition

For intents outside these 7 categories, the main Agent designs a new sub-template by extrapolation and writes it into the artifact.

### 4. Mental Model Split into Two Columns: Value Lenses + Operational Techniques

The distilled mental model is split into two columns:

- **Part A — Value Lenses (价值观镜片)** (2-5): Foundational angles for viewing problems. Must pass Triple Validation (cross-domain recurrence / generative power / distinctiveness).
- **Part B — Operational Techniques (操作招式)** (1-5): Personally-named actionable checklists — like Duan Yongping's "Stop Doing List" and "20-Hole Punch Card," Munger's "Lollapalooza Effect," Zhang Yiming's "Context not Control." Retention criteria: personally named + actionable + repeatedly cited — preserved even if only used in a single domain.

Phase 4 validation checks Toolkit responses word-by-word for named recall of these personally-coined techniques. Missing one = FAIL → back to Phase 2 to re-extract. This ensures Toolkit mode can directly invoke specific techniques rather than only outputting generic advice.

### 5. Care Red Line — Hard Gate

Whenever Phase 0A infers "emotional companionship possibility > 0," the artifact must include a Care Red Line section with crisis hotlines covering Chinese (Beijing 010-82951332 / National 400-161-9995) + English (US 988 / UK 116 123) + Asia-Pacific (Singapore 1-767 / Hong Kong 28960000 / Taiwan 1925) + universal fallback — none may be omitted. Phase 4 validation simulates three signal types (ordinary low mood / extreme distress / unhealthy dependency). The Persona must correctly break character temporarily + provide real help resources + establish clear boundaries. All three passing = PASS; **FAIL means cannot deliver**.

This rule ensures that any Persona, when the user is in emotional crisis, will temporarily step out of character to provide real help resources — never missing a distress signal in pursuit of immersion.

### 6. Persona Factual Questions Follow Agentic Protocol

Persona mode defaults to **Agentic Protocol**: when specific companies / holdings / recent developments / character version stats are involved, must WebSearch / check official sources first before answering — no staying in character and fabricating.

All artifact SKILL.md front pages mandatorily inject a "Timeliness Declaration" with all four fields: creation date / research cutoff / most recent major event coverage / last update. This lets users see the information timeliness boundary every time they activate the skill.

### 7. Incremental Update Pathway for Already-Distilled Skills

When the user says "update Luo Xiang's skill" or "Duan Yongping has new developments recently," or Phase 0A scans and finds an existing skill with the same name locally, 女娲 forces a three-way choice: ① Overwrite and redo ② Incremental update (recommended) ③ Create v2 alongside. Incremental updates only run Agent 2 (latest conversations) + Agent 5 (latest decisions) + Agent 6 (timeline update), appending new content to corresponding research files, comparing old vs new → supplement / correct / add.

### 8. 5 Regular Checkpoints + 1 Conditional Checkpoint

Across 8 Phases, 5 regular checkpoints are set (0A.1 form selection / 1.5 research quality / 2.5 extraction summary / 3.5 first-screen preview / 5.5 change summary). 女娲 explicitly pauses and waits for user confirmation at each. When terms like Persona, Toolkit, "first screen," or "mode alignment" first appear, they're explained in 1-2 sentences of plain language before recommendations are made. Additionally, 1 conditional checkpoint (4.5: after 2 repair cycles still FAIL, ask user whether to accept current version for delivery). The repair cost at each checkpoint is far lower than final rework.

---

## Installation

女娲·Dual-Mode is built on the open [Agent Skills](https://agentskills.io) protocol and runs in any skills-compatible AI agent runtime.

### Method 1: Agent Install (Recommended)

Open the agent you're using (Claude Code, Codex, Cursor, OpenClaw, Hermes, CodeBuddy, Workbuddy, Gemini CLI, OpenCode, etc.) and tell it:

```
Install this skill for me: https://github.com/shallinta/nuwa-dual-mode
```

The agent will auto-clone the repo, locate the `skills/nuwa-dual-mode/` directory, and register it in the local skills system.

### Method 2: npx skills CLI Install

Use the universal CLI installer ([vercel-labs/skills](https://github.com/vercel-labs/skills), supporting 55+ runtimes):

```bash
npx skills add shallinta/nuwa-dual-mode --skill nuwa-dual-mode
```

Add runtime-specific flags like `-a claude-code` / `-a codex` / `-a cursor` / `-a openclaw` if needed.

### Method 3: ClawHub Install (OpenClaw Users)

```bash
openclaw skills install nuwa-dual-mode
```

Or just say directly in an OpenClaw conversation:

```
Install nuwa-dual-mode
```

### Method 4: Manual Install

<details>
<summary>Expand for runtime skills directories</summary>

| Runtime | Install Path |
|---|---|
| Claude Code | `~/.claude/skills/nuwa-dual-mode/` |
| Codex CLI | `~/.codex/skills/nuwa-dual-mode/` |
| Cursor | `~/.cursor/skills/nuwa-dual-mode/` |
| OpenClaw | `~/.openclaw/workspace/skills/nuwa-dual-mode/` |
| Hermes / Others | clone into the runtime's `skills/` directory |

```bash
git clone https://github.com/shallinta/nuwa-dual-mode /tmp/nuwa-dual-mode && \
cp -r /tmp/nuwa-dual-mode/skills/nuwa-dual-mode <corresponding path above> && \
rm -rf /tmp/nuwa-dual-mode
```

</details>

---

## Usage

Once installed, tell your agent any of the following:

```
# Investors / Entrepreneurs (dual-mode default, Toolkit-first)
> Distill Duan Yongping                       # Persona to chat investing philosophy, 
                                              # Toolkit to diagnose decisions with Right BPP / Stop Doing List
> Make me a dual-mode skill for Buffett       # Same category: Moat / Circle of Competence frameworks

# Thinkers / Scholars (dual-mode default, Persona-first)
> Make me a dual-mode skill for Feynman       # Persona to chat curiosity, 
                                              # Toolkit to diagnose with First Principles
> Make Luo Xiang into a perspective skill     # Case → Law → Philosophy triage

# Pure Methodology Topics (single Toolkit)
> Create a Toolkit skill for "Antifragile Decision-Making"  # Not tied to a specific person — pure domain tool

# Fictional Characters / Scenario Roleplay (single Persona recommended)
> Distill Kamisato Ayaka (single Persona)     # Game character, with parenthetical action/expression descriptions
> Make Klein into a conversation skill        # Novel protagonist

# Fictional Characters — Dual-Mode (when user explicitly requests)
> Make SpongeBob dual-mode                    # Persona to chat like him, 
                                              # Toolkit to unpack "Bikini Bottom Survival Philosophy" 
                                              # (with fictional-world disclaimer)

# Tech Evangelists / Development Philosophy
> Make Karpathy a perspective skill           # Persona to chat tech taste, 
                                              # Toolkit to teach development with Software 2.0 / vibe coding
> Distill Linus Torvalds                      # Same category: Toolkit uses "good taste" / 
                                              # "practical not pretty" to review code

# Web Novel / Genre Authors
> Distill "爱潜水的乌贼" (The Squid Who Loves Diving)  # Web novel author — Persona for creative process chat, 
                                                        # Toolkit for worldbuilding / setting review
> Make 猫腻 (Mao Ni) into a skill            # Same category: both imitate narrative rhythm 
                                              # and review long-form structure

# Historical / Classical Figures
> Distill 苏轼 (Su Shi)                        # Classical literati — auto-injected era-anchoring statement 
                                              # (when asked about smartphones, uses "time-travel explanation")
> Make me a perspective skill for 王阳明 (Wang Yangming)  # Same category — Toolkit embedded as 
                                                          # "Heart-Mind Diagnosis"

# Comedians / Pundits / Expressive Personalities
> Distill MrBeast                             # Content creator — Persona for persona simulation, 
                                              # Toolkit for attention engineering analysis
> Make 罗永浩 (Luo Yonghao) into a skill      # Pundit-type public figure — Persona for expression DNA imitation, 
                                              # Toolkit for business judgment analysis
> Distill a Li Dan-style assistant            # Expressive personality — mainly Persona for humor rhythm imitation

# Update Existing Skills
> Update Luo Xiang's skill                    # Triggers incremental update flow — only runs Agents 2/5/6
```

Not sure who to distill? Just state your confusion:

```
> I keep making bad decisions lately
```

女娲 will ask 1-2 rounds to help you locate your need dimensions, then let you **name the distillation subject yourself** — preserving your agency of choice (the choice comes from your cognition, not a pre-filtered list).

After distillation, invoke it directly:

```
> Duan, what do you think of liquor stocks?               # Persona mode
> Use Duan Yongping's method to diagnose my startup       # Toolkit mode
> Switch to Toolkit / Switch to conversation              # Mid-session dual-mode switching
> Exit                                                     # Exit Persona, restore AI identity
```

---

## What Gets Distilled

| Layer | Description | Location |
|-------|-------------|----------|
| **How they speak** | Expression DNA — sentence structure / high-frequency words / rhythm / humor style / closing habits | `shared/expression-dna.md` |
| **How they think** | Mental model split into two columns: **Part A Value Lenses (价值观镜片)** (2-5, Triple Validation) + **Part B Operational Techniques (操作招式)** (1-5, personally named + actionable + repeatedly cited) | `mode-toolkit/key-concepts.md` |
| **How they decide** | Decision heuristics (5-10 "If X, then Y" rules) | `mode-toolkit/decision-heuristics.md` |
| **How they roleplay** | Hard roleplay rules + stay-in-character response bank + Agentic Protocol | `mode-persona/role-play-rules.md` |
| **What they don't do** | Anti-patterns + tiered disclaimers by subject type (investor / medical-law-psych / celebrity / fictional / historical) | `shared/values-and-antimodes.md` |
| **How they might be used** | All intent dimensions inferred in Phase 0A — listed on first screen, kept open | SKILL.md first-screen "Use Cases" |
| **Knowing their limits** | Honesty boundaries ≥ 5 items + Timeliness Declaration (creation / cutoff / recent events / last update) | SKILL.md first screen |

### Mandatory Sections Auto-Injected by Subject Type

| Section | Trigger Condition |
|---------|-------------------|
| **Tiered Disclaimer** | Selected by subject type: investors / med-legal-psych / celebrity KOL / fictional character / historical figure / thinker — each with matching template |
| **Care Red Line** | Inferred emotional companionship probability > 0 → mandatory (triggers for nearly all persons), covers CN / EN / SG / HK / TW + universal fallback |
| **Era Anchoring Statement** | Historical / classical / deceased / isekai characters mandatory, with "time-travel explanation" for posthumous matters |
| **Topic Boundary** | Living real persons / celebrities / public figures mandatory — only based on public statements |
| **Timeliness Declaration** | Mandatory for all artifacts, all 4 fields required |

### Honesty Boundaries

Every produced skill clearly marks what it cannot do:

- Methodology threshold — "Understanding ≠ Doing." Requires personal values and cash flow alignment.
- Non-replicability — The person's capital accumulation / network / financial structure cannot be replicated by ordinary users.
- Public ≠ Private — There is always a gap between public persona and actual practice.
- Information has a cutoff — Events after the Phase 0.5 research lock-in time are not covered. Permanently visible on the first screen.
- Does not constitute investment / legal / tax / medical / psychological advice.

**A skill that doesn't tell you its boundaries is not worthy of trust.**

---

## How It Works

```
Phase 0    Entry routing (direct path / diagnostic path) + existing skill detection
Phase 0A   Need clarification + automatic intent dimension inference + local materials & fan-work inquiry
Phase 0A.1 Artifact form selection (auto-determined + user confirmation + terminology explained) ← ✓ checkpoint
Phase 0.5  Create skill 3-layer directory skeleton (shared / mode-persona / mode-toolkit)
Phase 1    6-Agent parallel research (writings / conversations / expression / external views / decisions / timeline)
Phase 1.5  Research quality summary (primary source ratio / contradictions / under-informed dimensions) ← ✓ checkpoint
Phase 2    Framework extraction (Triple Validation + fan-work/official conflict inquiry)
Phase 2.5  Extraction summary + mode alignment + first-screen negotiation ← ✓ checkpoint
Phase 3    Skill construction (inject feature matrix / Care Red Line / era anchoring / disclaimer tiers)
Phase 3.5  First-screen 30-line preview confirmation (dual-mode only) ← ✓ checkpoint
Phase 4    Quality validation (select validation suite by inferred intents + technique enumeration + Care Red Line hard gate)
Phase 4.5  Repair cycle (max 2 rounds; if still FAIL at round 2, must get user confirmation to deliver) ← ✓ conditional checkpoint
Phase 5    Dual-Agent refinement (coverage of intent completeness / mandatory section injection completeness)
Phase 5.5  Change summary confirmation ← ✓ checkpoint
Delivery   Package → upload → register as custom skill → mandatory 5-part conclusion
```

**Update flow exception**: If this is "update XX's skill" or the skill already exists locally, the incremental flow Phase U.0~U.5 is used — only running Agents 2/5/6, not re-running the full 8 Phases.

Full methodology and execution details for each Phase are in the `references/` subdirectory:

| File | Contents |
|------|----------|
| `workflow-phases.md` | Phase 0~5 complete execution manual |
| `intent-inference.md` | Automatic intent dimension inference methodology (12+ intent catalog + extrapolation) |
| `mode-detection-logic.md` | Auto-detection decision tree + user negotiation scripts (with Persona/Toolkit term explanations) |
| `dual-mode-template.md` | Dual-mode SKILL.md + 3-layer directory templates |
| `single-mode-template.md` | Single-mode skill templates (Persona / Toolkit, including fictional character-specific requirements) |
| `workflow-types.md` | Toolkit workflow sub-templates A-G + extrapolation rules |
| `checkpoint-protocol.md` | 5 regular checkpoint + Phase 4.5 conditional checkpoint protocols |
| `extraction-framework.md` | Mental model Triple Validation + fan-work/official conflict inquiry |
| `validation-tests.md` | Phase 4 validation test suites (base 6/3 + intent-selected suites + Care Red Line hard gate + automation) |
| `agentic-protocol-recipe.md` | Persona Agentic Protocol generation recipe |
| `update-existing-skill.md` | Incremental update flow (Phase U.0~U.5, only Agents 2/5/6) |
| `welcome-message.md` | First-activation welcome message template and trigger rules |

---

## Repository Structure

```
nuwa-dual-mode/
├── SKILL.md                          # 女娲·Dual-Mode core
├── README.md                         # This file (Chinese)
├── README_EN.md                      # This file (English)
├── scripts/
│   ├── download_subtitles.sh         # YouTube / Bilibili subtitle download
│   ├── srt_to_transcript.py          # SRT cleaning to plain text
│   ├── merge_research.py             # Phase 1.5 auto-generate research summary table
│   └── quality_check.py              # Phase 4 auto 6-item quality self-check (supports Part A/B split)
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

## Relationship with the Original nuwa-skill

This project is a **Dual-Mode variant fork** of [花叔 (Huashu) @alchaincyf's nuwa-skill](https://github.com/alchaincyf/nuwa-skill), not a replacement. The original's core methodology — mental model Triple Validation, 6-Agent parallel research, Expression DNA, honesty boundaries, taste code — are all inherited and carried forward. Dual-Mode extends this methodology to scenarios requiring **simultaneous first-person roleplay and third-person methodology invocation across widely diverse subject types**.

The table below only marks differences, not evaluations:

| Dimension | Differences |
|-----------|-------------|
| Artifact form | Default `-perspective` dual-mode (Persona + Toolkit coexist); also supports single `-persona` / single `-toolkit` |
| Intent identification | Proactively infers 12+ possible intent dimensions before distillation begins, all written to first-screen "Use Cases" |
| Mental model organization | Split into two columns: Part A Value Lenses (Triple Validation) + Part B Operational Techniques (personally named + actionable + must be recalled) |
| Toolkit workflows | 7 sub-templates (A-G) classified by intent + extrapolation for new designs |
| Fictional characters | Dedicated single Persona template with scenario roleplay style / parenthetical action notation / opening guidance / fan-work fusion |
| Checkpoints | 5 regular hard pauses + 1 conditional trigger; terms automatically explained in plain language on first occurrence |
| Care Red Line | Emotional companionship possibility > 0 → mandatory activation, 5-region hotlines + universal fallback, Phase 4 hard gate |
| Timeliness | Forced first-screen injection of "Timeliness Declaration" (creation / cutoff / recent events / last update — 4 fields) |
| Persona anti-fabrication | Default Agentic Protocol — specific facts require WebSearch before answering |
| Update flow | Already-distilled skills get three-way choice: overwrite / incremental / new v2. Incremental only runs Agents 2/5/6 |
| Fan-work / derivative works | Treated equally with official canon in extraction; conflicts trigger Phase 2 pause for user decision |

Usage recommendations:

- Subject is a single public-methodology figure and you want a lighter process → **use the original nuwa-skill directly**
- Subject needs Persona + Toolkit coexistence, or involves fictional characters / emotional companionship / multi-intent coverage and needs strong checkpoint guarantees → **use this project**

---

## License

MIT — Use freely, modify freely, build freely.

---

<div align="center">

MIT License · Standing on the shoulders of [花叔 Huashu](https://github.com/alchaincyf)

</div>
