# Prompt Template

## 单张生图

```text
Create a 16:9 capybara illustration for creator content.

Core idea:
<用户观点或场景>

Visual direction:
- White background, clean black line art.
- Main subject: a cute but not childish capybara. It must be recognizable as a capybara before any labels are read.
- Capybara identity lock: low horizontal barrel-shaped body, body larger than head, head attached to the front of the body, small round ears placed high and slightly back, tiny dark eyes set high, long blunt muzzle, broad flat nose-mouth area, tiny paws tucked close to the body, calm low-slung posture.
- Default color mode: soft-color. Use a warm light-brown capybara body and one restrained accent color. If the user requested mono, use black line art only with no fill color.
- The capybara must perform the main action, not stand as decoration.
- Show the emotion through simple eyes, mouth line, head tilt, paw gesture, and body posture.
- Add expressive short text labels by default: one short title or punchline, plus 2-5 object/state/action labels.
- Label important objects and states so the viewer does not need to guess.
- Keep generous whitespace and one clear focal point.
- One image expresses one idea only.

Avoid:
- third-party IP, mascot identity, specific artist or brand style imitation
- childish sticker look
- dense PPT infographic
- generic cute animal instead of capybara
- not a teddy-bear round head, not hamster cheeks, not a dog/cat pointed snout, not big floppy ears, not an upright mascot body
- text blocks or long explanations
```

## Shot List

```text
先阅读内容，挑真正值得视觉化的认知锚点。不要平均配图。

文章类请求默认先规划。即使用户写了“生成插图”“合理性生成插图”，只要没有明确写“直接生成 / 现在生图 / 不要规划”，先输出 shot list，不要立即生图。

每张候选图输出：
- 放置位置或使用渠道；文章类必须具体到章节、段落后或某句之后
- 画幅
- 主题
- 核心意思
- 构图模式
- 卡皮巴拉动作
- 情绪
- 主要元素
- 建议标注
- 优先级

最后给出“下一步”，包括推荐先生成哪几张，以及用户可以直接回复的命令。
```

## 改图

```text
Keep the same core idea and capybara subject, but revise:
<用户修改要求>

Preserve:
- relaxed capybara personality
- capybara identity lock: low horizontal barrel body, small back-set ears, high tiny eyes, long blunt muzzle, broad nose-mouth area, tiny paws
- clear action
- readable short labels
- one core idea

Check:
- Does it still look like a capybara?
- If labels are hidden, is the silhouette still a capybara rather than a bear, hamster, dog, cat, or generic mascot?
- Is the image more understandable than before?
- Are the labels helping instead of cluttering?
```
