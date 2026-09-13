# Worked Examples

Four complete runs, one per article type, used to validate this skill. Each case shows
the input source and the cards produced by following `SKILL.md`.

Cases:

1. Chinese popular-science article - 科普类（中文）
2. Chinese how-to / method article - 方法类（中文）
3. English technical explainer - 技术教程类（英文，测试语言跟随）
4. Very short notice - 信息不足场景（测试减量规则）

---

## Case 1 - 中文科普：睡眠如何巩固记忆

### Input (excerpt)

> 记忆的形成大致分为编码、巩固与提取三个阶段……白天学到的信息最初以不稳定的
> 形式暂存在海马体，只有在睡眠中，海马体会把这些信息"重放"给大脑皮层，信息才会
> 逐渐转移并稳定存储于皮层，形成长期记忆。
>
> 睡眠由多个周期组成，每个周期约 90 分钟，包含非快速眼动睡眠（NREM）和快速眼动
> 睡眠（REM）。深度的慢波睡眠（NREM 第三阶段）对陈述性记忆的巩固最为重要；而 REM
> 睡眠则更多与程序性记忆和情绪记忆的整合相关。
>
> 熬夜复习往往事倍功半……睡眠不足还会影响注意力与工作记忆，使编码阶段的效率下降。

### Output

```markdown
## 知识卡片：睡眠是记忆巩固的关键环节

### 卡片 1：记忆形成的三个阶段
- **核心知识**：记忆的形成分为编码、巩固、提取三个阶段，作用各不相同。
- **简明解释**：编码在学习当下把外界信息转成神经信号；巩固让信息稳定下来；提取是
  日后回忆时调取信息。其中巩固决定信息能否长期留存。
- **自测问题**：记忆形成包含哪三个阶段？分别发生在什么时候？

### 卡片 2：睡眠通过海马体重放完成巩固
- **核心知识**：白天信息先暂存于海马体，睡眠中经"重放"转移到大脑皮层，才形成长期记忆。
- **简明解释**：编码后的信息最初并不稳定，只有在睡眠中由海马体把信息重放给皮层，
  信息才会转移并稳定存储，从而变成长期记忆。
- **自测问题**：为什么说睡眠是记忆巩固不可或缺的一环？

### 卡片 3：睡眠由约 90 分钟一个的周期构成
- **核心知识**：睡眠以约 90 分钟为一个周期，每个周期包含 NREM 与 REM 两种睡眠。
- **简明解释**：睡眠不是均匀的整体，而是在非快速眼动睡眠（NREM）和快速眼动睡眠
  （REM）之间循环。理解周期是理解两类睡眠分工的前提。
- **自测问题**：一个睡眠周期大约多长？周期内包含哪两类睡眠？

### 卡片 4：慢波睡眠与 REM 睡眠分工不同
- **核心知识**：慢波睡眠主要巩固陈述性记忆，REM 睡眠更多参与程序性记忆与情绪记忆的整合。
- **简明解释**：深度慢波睡眠属于 NREM 第三阶段，对事实、知识这类陈述性记忆最重要；
  REM 睡眠则与技能类（程序性）记忆和情绪记忆的整合相关。
- **自测问题**：陈述性记忆的巩固主要依赖哪一阶段？REM 睡眠更偏向哪类记忆？

### 卡片 5：熬夜复习得不偿失
- **核心知识**：牺牲睡眠来延长学习时间，等于砍掉记忆巩固环节，学到的东西难以留存。
- **简明解释**：熬夜挤出的时间只增加了编码机会，却失去了巩固所需的睡眠。学习后安排
  完整睡眠，第二天的回忆效果通常更好。
- **自测问题**：为什么熬夜复习的学习效果往往不好？

### 卡片 6：睡眠不足会削弱编码效率
- **核心知识**：睡眠不足会损害注意力与工作记忆，使学习当下的编码效率下降。
- **简明解释**：睡眠的影响不只在巩固阶段，它还降低第二天的注意力与工作记忆，而这两者
  正是高效编码的前提，因此会从编码和巩固两头拖累记忆。
- **自测问题**：除巩固之外，睡眠不足还会通过什么方式影响记忆？
```

Result: 6 cards, no fabricated content, every card covers one point. Case 5 and case 6
look close but are distinct (losing consolidation vs. weakening encoding), so they stay
separate. No source-provided example existed for Case 4, so a self-test question was used
instead of inventing one.

---

## Case 2 - 中文方法类：番茄工作法

### Input (excerpt)

> 把工作时间切成 25 分钟的专注时段，称为一个"番茄钟"；每段结束后休息 5 分钟；连续
> 完成四个番茄钟后，进行一次 15 到 30 分钟的较长休息。
>
> 它把"要不要继续工作"转化成了"只需专注 25 分钟"这样一个小而具体的承诺，降低了开始
> 工作的心理门槛；固定时长的短休息能缓解持续专注带来的疲劳。
>
> 原则：一个番茄钟内不可分割，被打断应作废重来或记录下来稍后处理；休息时间不用于
> 处理工作事务；一项任务超过四个番茄钟应拆解成更小的子任务。
>
> 它对需要长时间连续投入、进入心流状态的深度工作并不友好，更适合任务零散、容易
> 拖延、需要频繁切换的日常事务。

### Output

```markdown
## 知识卡片：番茄工作法：用固定节奏管理注意力

### 卡片 1：番茄工作法的基本节奏
- **核心知识**：25 分钟专注为 1 个番茄钟，钟后休息 5 分钟，每完成 4 个番茄钟进行
  15-30 分钟长休息。
- **简明解释**：这套固定节奏把工作时间切成可预期的单元，专注与休息交替进行，是整个
  方法最基础的规则。
- **例子 / 自测问题**：连续工作 4 个番茄钟后，应休息多久？

### 卡片 2：有效原因是降低开始工作的门槛
- **核心知识**：它把"要不要继续工作"转化为"只需专注 25 分钟"，降低了开始的心理门槛。
- **简明解释**：面对任务时，决定是否继续会持续消耗意志力；而承诺一个短小、具体的
  时段则让开始变得容易，从而更容易进入工作状态。
- **自测问题**：为什么把时间切成 25 分钟反而更容易开始工作？

### 卡片 3：短休息维持注意力稳定
- **核心知识**：固定时长的短休息能缓解持续专注的疲劳，让注意力在整日内保持稳定。
- **简明解释**：长时间不间断地工作会使注意力衰减；按固定间隔插入休息，可把疲劳及时
  释放，使后续时段的专注质量不下降。
- **自测问题**：短休息在番茄工作法中的作用是什么？

### 卡片 4：一个番茄钟不可分割
- **核心知识**：一个番茄钟内不可分割，中途被打断时应作废该番茄钟重来，或记录下来稍后处理。
- **简明解释**：番茄钟的价值来自完整、不被打断的专注时段，因此打断会直接破坏该时段，
  必须作废或记录后再处理，而不能"续着用"。
- **例子 / 自测问题**：专注到第 10 分钟被电话打断，按番茄工作法应如何处理？

### 卡片 5：任务超过四个番茄钟要拆解
- **核心知识**：一项任务若需要超过四个番茄钟，应把它拆解成更小的子任务。
- **简明解释**：无法在四个番茄钟内完成，通常说明任务颗粒度过大；拆解后每个子任务都能
  获得完整反馈，进度也更可控。
- **例子 / 自测问题**：为什么要把超过四个番茄钟的任务拆解？

### 卡片 6：适用边界：不适合长时间深度工作
- **核心知识**：番茄工作法对需要长时间连续投入、进入心流状态的深度工作并不友好。
- **简明解释**：频繁的定时打断可能破坏思路，因此它更适合任务零散、容易拖延、需要频繁
  切换的日常事务，而不是需要长时段沉浸的深度任务。
- **例子 / 自测问题**：哪类工作不适合使用番茄工作法？为什么？
```

Result: 6 cards. The source's three "原则" were tested for independence: the
indivisible-timer rule and the >4-timer split rule each stand alone, so they became
separate cards; the "休息时间不处理工作事务" rule was dropped as it repeats the
rest concept and carries little independent knowledge.

---

## Case 3 - English technical explainer: Git branches and merges

### Input (excerpt)

> A Git branch is simply a movable pointer to a commit... it only writes a 41-byte file
> containing the hash of the commit the branch points to... The special pointer HEAD
> tells Git which branch you currently have checked out... A fast-forward merge happens
> when the target branch has not diverged... A three-way merge is required when both
> branches have new commits since they diverged... Conflicts occur when both branches
> change the same part of the same file... deleting a branch only removes the pointer.

### Output

```markdown
## Knowledge Cards: How Git Branches and Merges Work

### Card 1: A branch is only a movable pointer
- **Core knowledge**: A branch is a movable pointer to a commit, not a copy of files.
- **Explanation**: Creating a branch writes only a 41-byte file holding a commit hash,
  which is why branching is nearly instantaneous even in very large repositories. The
  files themselves are shared, not duplicated.
- **Self-test**: Does creating a branch copy your project files? Why or why not?

### Card 2: HEAD marks the current branch
- **Core knowledge**: HEAD is the pointer telling Git which branch is currently checked out.
- **Explanation**: HEAD follows the checked-out branch, so it always marks where the next
  commit will be attached. It is the only thing Git needs to know to place new work.
- **Self-test**: What does HEAD indicate, and what does it determine about your next commit?

### Card 3: Committing moves the branch pointer forward
- **Core knowledge**: A commit creates a new commit object and automatically advances the current branch pointer.
- **Explanation**: Because a branch is just a pointer, saving work does not rewrite files;
  Git adds a commit and slides the pointer to it, with HEAD following along.
- **Self-test**: What happens to the branch pointer when you commit?

### Card 4: Fast-forward merge vs. three-way merge
- **Core knowledge**: A fast-forward merge only moves the pointer, while a three-way merge creates a merge commit with two parents.
- **Explanation**: Fast-forward applies when the target branch never diverged, giving a
  linear history with no merge commit. When both branches have new commits, Git compares
  both tips against their common ancestor and records a merge commit.
- **Self-test**: What condition forces a three-way merge instead of a fast-forward?

### Card 5: Conflict handling
- **Core knowledge**: A conflict occurs when both branches change the same part of the same file, and Git cannot resolve it automatically.
- **Explanation**: Git marks the conflicting region and pauses the merge because it cannot
  guess which version is correct. The developer resolves it manually, stages the files,
  and commits - blindly accepting one side is risky since both changes may be needed.
- **Self-test**: Why does Git stop the merge on a conflict instead of choosing a side?

### Card 6: Deleting a branch removes only the pointer
- **Core knowledge**: Deleting a branch removes the pointer, not the commits.
- **Explanation**: The commits stay reachable through other branches or the reflog until
  Git's garbage collector decides they are unreachable, typically after a grace period of
  about 30 days. This is why deleted branches can usually be recovered.
- **Self-test**: Why can a mistakenly deleted branch usually be restored?
```

Result: 6 cards. Output language follows the English source. No merge of Card 2 and
Card 3: one defines HEAD, the other describes what committing does, which are separately
useful points.

---

## Case 4 - Very short notice (reduced-count rule)

### Input

```markdown
# 新版本发布通知

本次 2.4.0 版本将于 3 月 18 日发布。该版本修复了登录页在移动端偶发白屏的问题，并将
最低支持的系统版本提升到 iOS 15。
```

### Output

```markdown
## 知识卡片：2.4.0 版本发布信息

> 原文信息不足以支撑 5 张卡片，以下为 2 张核心卡片。

### 卡片 1：2.4.0 于 3 月 18 日发布并修复移动端登录白屏
- **核心知识**：2.4.0 版本于 3 月 18 日发布，修复了登录页在移动端偶发白屏的问题。
- **简明解释**：本次发布的主要变更之一针对移动端登录页的偶发白屏缺陷，属于问题修复，
  不涉及新功能。
- **自测问题**：2.4.0 修复了哪个具体问题？

### 卡片 2：最低支持系统版本提升至 iOS 15
- **核心知识**：2.4.0 将最低支持的系统版本提升到 iOS 15。
- **简明解释**：这是本次发布的另一项变更，意味着低于 iOS 15 的设备将不再被支持，
  升级前需要确认设备系统版本。
- **自测问题**：升级到 2.4.0 后，iOS 15 以下的设备还能使用吗？
```

Result: 2 cards plus an explicit note, instead of padding to 5. The skill's job here is
to stay honest about how little the source supports.
