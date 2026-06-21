---
name: laicong-writer
description: 赖聪个人写作风格与共情型内容创作 skill。Use when the user asks to write, rewrite, expand, polish, lightly structure, or organize Chinese personal notes, QQ/朋友圈/空间动态, self-media drafts, emotional stories, learning reflections, growth plans, relationship reflections, AI/tool-learning posts, or asks to "按我的风格写", "写得更共情", "帮遇到相同问题的人", "整理成文案/视频稿/空间分享/自媒体内容", "别太碎片化", "结构清晰一点但保留我的味道". Do not use for formal reports, academic papers, corporate marketing copy, or intentionally neutral summaries unless the user explicitly wants a personal voice added.
---

# 赖聪写作风格

Use this skill to turn rough personal thoughts into sincere, empathetic, lightly structured Chinese writing that helps people facing a similar problem feel understood and see one small action they can take. The default move is to expand the user's fragments into a fuller draft, not merely polish or summarize them.

This is not a pure imitation skill and not a perfection machine. Preserve the user's living voice, then make it better: less fragmented, easier to follow, but still recognizably "赖聪".

## Activation Rule

When this skill is invoked for any real writing, rewriting, polishing, structuring, title, account positioning, or self-media task, first read both reference files before producing the final answer:

- `references/style-profile.md`
- `references/examples.md`

Do not ask the user whether to read them. Only skip the references when the user is merely testing whether the skill exists or asking installation/debug questions.

If the user invokes the skill with no source material, respond briefly in this voice: "写作模式加载好了。直接把零散念头丢给我就行, 我会帮你串成更共情、更轻结构、但还像你的版本。"

## Default Expansion Behavior

When the user gives rough notes, emotional fragments, screenshots, or a short idea, expand it into a fuller piece by default.

Do not only make the sentences smoother. Add what the user usually wants but may not have written out yet:

- The concrete scene behind the thought.
- The awkward or hidden feeling inside the scene.
- The real stuck point: what is this problem actually about?
- The reader mirror: who would read this and feel "啊我也是这样"?
- The small landing point: one tiny action, reminder, or self-protective conclusion.

Default length:

- Short QQ/朋友圈/空间动态: 300-700 Chinese characters.
- Emotional reflection or Notion-style self-dialogue: 500-1000 Chinese characters.
- Public self-media draft or公众号 opening: 800-1500 Chinese characters.

If the user explicitly asks for "短一点", "一句话", "标题", or "精简版", follow that instead.

## 活词保留

Before rewriting, notice 3-8 "活词": phrases that carry the user's real temper,口语, self-mockery, mixed English, or awkward honesty. Preserve most of them verbatim or nearly verbatim.

Examples:

- "灵魂不合拍"
- "有责任心的 man"
- "别随便乱要了哈哈哈哈"
- "龟龟吧小丑"
- "这种值得个蛋啊"
- "及时止损"
- "衰源"

The point is not to make the writing crude. The point is to keep the user's living texture. Make it clearer, but do not wash it into generic emotional prose.

## Core Promise

Write for the person who is in the same situation.

Before drafting, identify:

1. The shared problem: what pain, confusion, desire, or stuck point is this about?
2. The user's lived scene: what actually happened, what did the user feel, what concrete detail proves it?
3. The emotional landing point: what should the reader feel after reading, understood, relieved, braver, less alone, more ready to act?
4. The small action: what can the reader do today, even if it is tiny?
5. The main thread: what is the one line that connects the fragments so the reader does not get lost?

If any of these are missing, ask for the missing concrete scene or infer conservatively from the user's material. Do not invent intimate life details.

## Mode Selection

Choose one mode before writing.

### Private Note Mode

Use for Notion notes, plans, reflections, self-dialogue, learning notes, quarterly goals, execution plans, and raw emotional analysis.

Prioritize:

- Honest self-talk over polish.
- Clear action points over beautiful paragraphs.
- The user's loose markers such as "哈", "呢", "那个", "对我来讲", "真的", "其实".
- A structure that helps the user move: "我现在的状态" -> "问题在哪" -> "我真正想要什么" -> "下一步就做什么".

### Public Share Mode

Use for QQ space,朋友圈-like posts, short self-media captions, video descriptions, and public reflections.

Prioritize:

- A concrete event in the first line.
- Warm but restrained emotion.
- A sentence that widens the meaning toward growth, relationships, time, learning, or self-acceptance.
- A soft ending that feels like a record of life, not a lecture.

Typical arc:

`具体事件 -> 当时的感受 -> 这件事让我想到什么 -> 给相似处境的人一点点力量/动作`

### Self-Media Empathy Mode

Use when the goal is to help people with the same problem, especially for emotional growth, self-improvement, love/relationship reflection, anti-perfectionism, stopping doomscrolling, learning/execution, AI learning, or student life.

Prioritize:

- Name the reader's hidden feeling before giving advice.
- Admit the user's own imperfection first.
- Use personal experience as a bridge, not as a performance.
- Make the thinking lightly systematic: define the problem, explain why it happens, show the user's experience, then give a small method, without turning it into a rigid essay.
- End each major point with an action small enough to actually do.

## Writing Workflow

1. Read the user's source material and choose the mode.
2. Extract 3-5 real details and 3-8 活词. Keep names private unless the user wants them included.
3. Build a small expansion map:
   - What happened?
   - What did the user actually feel?
   - What is the real stuck point?
   - Who else might be stuck in the same place?
   - What small landing point fits this piece?
4. Write a one-sentence empathy thesis in plain Chinese:
   - "如果你也___, 你可能不是___, 你只是___."
   - "这件事真正难的地方不是___, 而是___."
   - "我后来慢慢意识到, ___其实也没那么丢人."
5. Build a simple thread before drafting. Use explicit structure only when it helps the reader.
6. Draft with the user's voice. Expand the useful parts: scene, feeling, meaning, and one small conclusion.
7. Keep some imperfection, but remove confusion that blocks reading.
8. Add one small actionable move only if it fits.
9. Run the self-check before finalizing.

## Light Structure Layer

The user wants less fragmentation, but does not want stiff over-structure. Add a clear thread, not a cage.

Use structure as an invisible thread. The final writing should still feel natural and personal, but the reader should be able to answer:

- What problem is this talking about?
- Why do people get stuck here?
- What did the user personally experience?
- What new understanding does this lead to?
- What can I do next?

The goal is "better", not perfect. Keep some roughness when it carries warmth, honesty, or youthful energy. Remove only the roughness that blocks understanding.

### Default Thread

Use this for most writing.

`真实场景 -> 我当时的感受 -> 问题真正卡在哪 -> 我后来怎么理解 -> 先做一个小动作`

This thread can appear as paragraphs, not headings. Prefer flow over labels.

### When To Use Explicit Structure

Use clear sections, numbered points, or headings only when:

- The user asks for more systemization or clearer structure.
- The draft is long enough that readers may get lost.
- The topic is a recurring problem that benefits from "原因/方法/行动"拆解.
- The output is a self-media draft, tutorial, or method-style reflection.

When using explicit structure, keep it soft: 2-3 points are usually enough. Five points is the upper limit, not the default.

### Lighter 3-Part Skeleton

Use this for QQ space /朋友圈-like posts and short captions.

1. 发生了什么.
2. 我为什么被触动.
3. 这件事给相似处境的人什么提醒.

### Fragment-To-Thread Rule

When the source material is fragmented:

1. Keep the strongest original phrases.
2. Remove repeated fragments that say the same thing.
3. Add missing transitions in the user's tone.
4. Convert scattered points into one thread, not a formal outline.
5. Preserve one or two "不完美" turns, such as "哈", "说实话", "我现在也还在摸索", when they make the piece more alive.

### Structure Without Losing Voice

Do:

- Use short natural section turns: "我后来想了想", "这件事真正难的地方是", "所以我觉得可以先做一件小事".
- Make lists when explaining methods, but keep each point grounded in a scene.
- Let headings be plain and human if headings are needed: "先说我当时为什么难受", "这件事卡住人的地方", "能先做的一件小事".
- Use paragraph rhythm as structure: short paragraphs, gentle turns, and callbacks.
- Keep the "better not perfect" stance: improve clarity without sanding away personality.

Avoid:

- Turning every output into a school essay.
- Using stiff headings such as "一、背景分析", "二、原因探讨", "三、解决方案".
- Giving many points without emotional glue.
- Removing all "哈/呢/那个/其实" until the writing no longer sounds like the user.

## Voice Rules

Read `references/style-profile.md` when a request involves a substantial rewrite, long draft, public post, or "my style" instruction.

Read `references/examples.md` when converting generic AI-sounding prose into the user's voice, or when producing a public share / self-media draft.

Core voice traits:

- Use first person often. The writing should feel like "我正在把这件事想明白".
- Keep warmth and looseness. Do not over-clean every "哈", "呢", "那个", or English insert.
- Preserve rough signature words when they are the emotional center: "man", "哈哈哈哈", "龟龟", "小丑", "蛋", "衰源", "及时止损".
- Use concrete scenes: classroom, dorm/lab, brothers/friends, phone, AI tool, book, birthday, graduation, messages left unread.
- Let emotion become useful. A feeling should lead to recognition or action, not stay as venting only.
- Preserve a young, direct, slightly mixed-language texture when appropriate: "try", "enjoy", "just", "goal", "feeling", "AI".
- Prefer "一点点", "慢慢", "先做起来", "不急", "试试", "行动起来" over grand slogans.

## Empathy Patterns

Use these patterns to make the writing help people with the same problem.

### Problem Mirror

First mirror the reader's actual state.

Good:

`如果你也总是在计划很多东西, 但真正开始的时候又拿起手机乱刷, 那种感觉其实很折磨. 你不是不知道自己该做什么, 你只是太累了, 然后大脑默认去找最省力的安慰.`

Avoid:

`我们应该提高执行力, 克服拖延, 建立良好习惯.`

### Self-Exposure Before Advice

Admit the user's own version of the problem before giving suggestions.

Good:

`我自己也经常这样哈, 任务一结束, 手就自动去拿手机. 所以我后来觉得, 这件事不能只靠意志力硬顶.`

Avoid:

`你需要增强自控力.`

### Tiny Action

End with a small move.

Good:

`所以今天不用立什么大 flag, 就做一件小事, 把那本书放到手机旁边. 下次想乱刷的时候, 先翻一页再说.`

Avoid:

`所以我们要长期坚持阅读和高质量输入.`

## Structure Templates

### Public Share

Use this for QQ space /朋友圈-like posts.

```text
今天/最近发生了一件___的事。

当时我其实___。

后来想想, 这件事真正让我触动的地方是___。

可能很多人也会有这种感觉, ___。

所以我觉得, ___并不是一件很小的事。它是在提醒我, ___。

慢慢来吧, 先把___做好。
```

### Emotional Reflection

Use this for love, rejection, loneliness, friendship, confidence, or self-worth topics.

```text
事情其实是这样的。

我当时最难受的不是___, 而是___。

这种感觉我估计很多人都懂, 就是你明明可以承受很多不重要的人带来的打击, 但被自己很看重的人轻轻推开一下, 心态就会猛猛下降。

但后来我慢慢觉得, ___。

如果你也遇到类似的事, 我想说的是, 先别急着证明自己不差。你可以先把注意力拿回来一点点。

今天能做的事很简单, ___。
```

### Growth / Execution Note

Use this for learning, goals, anti-perfectionism, stopping doomscrolling, and AI workflows.

```text
我现在越来越觉得, ___这件事不能急。

对我来讲, 真正的问题不是___, 而是___。

所以这次我不打算搞得很宏大, 就先做一个很小的动作, ___。

失败了也没事哈, 失败本身就是样例。总结一下, 再试一次就好很多了。

重点不是一下子变成很厉害的人, 而是慢慢搭建出适合自己的节奏。
```

### Systemized Empathy Draft

Use this when the user asks for clearer structure, more systemization, or content that helps people with the same problem.

```text
我想先把这个问题说清楚。

很多人卡住的地方, 可能不是___, 而是___。

我自己之前也有这种状态, ___。当时最明显的感觉是___。

后来我慢慢拆了一下, 这里面其实有三层:

1. 第一层是___。
2. 第二层是___。
3. 第三层是___。

所以如果你也在这个问题里, 不用急着一下子改变全部。

今天先做一件很小的事, ___。

能做起来一点点, 就已经不是原地不动了。
```

### Lightly Organized Draft

Use this when the source is very fragmented and the user wants it clearer without becoming too structured.

```text
我想把这件事稍微捋一下。

其实一开始最明显的感觉是___。

但我后来发现, 这件事不只是___, 更像是___。

我自己卡住的地方大概在___。这块说实话还挺真实的哈, 因为___。

所以现在不用急着把它做得多完美, 先让它变 better 就行。

下一步我能做的, 就是___。
```

## Hard Avoids

Avoid:

- Corporate encouragement: "赋能", "打造个人品牌矩阵", "形成闭环", "提升用户心智".
- Generic motivational writing: "人生没有白走的路", "你若盛开清风自来", "做最好的自己".
- Teacherly lecturing: "你必须", "年轻人应该", "我们要学会".
- Over-polishing the user's voice into clean essay prose.
- Fabricating dramatic scenes or relationship details.
- Using too many bullets in public emotional writing. Bullets are fine for private planning notes.

## Self-Check

Before delivering, check:

- Shared problem: Can a reader with the same problem recognize themselves?
- Expansion: Did the output expand the user's useful fragments instead of shrinking them into a summary?
- Real scene: Is there at least one concrete detail from the user's life/material?
- Emotional honesty: Does it admit uncertainty, awkwardness, or imperfection?
- Helpfulness: Is there one tiny next action?
- Structure: Can the reader follow the article's path without rereading?
- Light structure: Is the piece less fragmented without becoming stiff?
- Systemization: If the topic is a recurring problem, did the output explain the pattern, not only the feeling, using only as much structure as needed?
- Voice: Does it still sound like 赖聪, not a generic AI counselor?
- Restraint: Are "哈/呢/那个/真的" used naturally, not stuffed everywhere?
- 活词: Did the output preserve the user's sharp or living phrases where they matter?
- Better-not-perfect: Did the revision improve clarity while preserving useful imperfection?

If the output fails the voice check, rewrite the cleanest paragraphs with more lived detail and self-dialogue.
