前面我们分享了[Skills的安装和使用（含注意事项）](https://my.feishu.cn/docx/MUbJdNaAvoTONsxlbqCc6MMDnUf?from=from_copylink)，

那么有哪些实用的 Skills，以及怎么找到这些Skills资源？

这里分享一些实用的Skills，以及高质量的Skills资源库，都是我自己用过且在知识星球分享过的。

# 实用 Skills

## 1、Frontend-design

用来解决AI老出紫色渐变UI有奇效。

Frontend-design skill🔗：https://github.com/anthropics/claude-plugins-official/tree/main/plugins/frontend-design/skills/frontend-design

我之前专门出过一条视频分享这个Skills，感兴趣可以移步查看>>>

暂时无法在飞书文档外展示此内容

和它能力类似的另一个热门Skills是 ui-ux-pro-max-skill

ui-ux-pro-max-skill🔗：https://github.com/nextlevelbuilder/ui-ux-pro-max-skill

之前在星球分享过它俩的区别：

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MTkzZTNjYjliOWRjZDgyMTVmZjhiZjc4NzVhYjU0MWRfNFlOYVBhdmFZeDNWb1M3VThsZlJGRnNVZ1NZQ0tnTERfVG9rZW46WU1wRWJ0Rm56b0VpM1p4RXR5a2NuT09jbmVkXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

## 2、Superpower

可以用来解决AI原生Plan Mode以及一些Task工具在头脑风暴这一环节提问不够细致或精准的问题。

Superpower skills🔗：https://github.com/obra/superpowers

当然，它的优势还不止于头脑风暴，它的基本工作流程是这样的（非常值得学习的工作流）：

1. **brainstorming**：构思与设计
    

通过结构化对话将粗略想法转化为完整设计，包括探索多种方案、权衡分析、增量验证。

2. **using-git-worktrees**：环境准备
    

设计批准后创建与主仓库共享但独立的git worktrees，每个功能都在独立的分支上开发，避免不同能功能开发相互干扰。

3. **writing-plans**：制定计划
    

将工作分解为小任务，每项任务都有确切的文件路径、完整代码和验证步骤。

4. **执行开发：**两种模式（二选一，根据任务特性和个人偏好）
    
    1. **subagent-driven-development**: 在同一会话中为每个任务分派新的子代理，任务间进行代码审查；
        
    2. **executing-plans**: 在并行会话中批量执行，每批任务完成后暂停，等待人工审查，获得人工批准后再继续下一批任务（这种模型提供了更多的人工控制机会，适合需要密切监督或复杂耦合的任务场景）。
        
5. **test-driven-development**：TDD，测试驱动开发
    

强制执行RED-GREEN-REFACTOR循环：它会先编写一个会失败的测试用例，从而定义你期望的行为，运行测试并确认它确实失败，证明测试能检测到问题；接着它会编写刚好能让测试通过的最少代码，如果运行测试确认代码能正确实现功能，那就提交这个小的、经过验证的改进。**这种设计可以防止过度设计，也保证每个功能都有对应的测试**

6. **requesting-code-review：**代码审查
    

任务之间对照计划进行审查，按严重程度报告问题。

问题分为三个等级：

- **Critical** (关键)：必须修复的问题。对应处理要求：立即修复，重新审查
    
- **Important** (重要)：应该修复的问题。对应处理要求：在下一个任务前修复
    
- **Minor** (轻微)：建议改进的问题。对应处理要求：记录，稍后处理
    

7. **finishing-a-development-branch：**完成工作
    

当任务完成后激活，验证测试，根据不同情况会提供这几种选项（合并/PR/保留/丢弃），同时会清理git worktrees，避免资源浪费。

  

## 3、planning-with-files

这个Skills基于Manus的上下文工程原理，通过将文件系统作为AI的“外部工作记忆”来解决上下文窗口限制和目标漂移问题。

它用三个markdown文件来管理任务：task_plan.md记录阶段和进度，notes.md存储研究发现，最终输出交付文件[deliverable].md。

这个项目很离谱，发布短短几天就6.6k stars（当然也有借势Manus被收购的原因），现在已经10.6k stars了。

planning-with-files skill🔗：https://github.com/OthmanAdi/planning-with-files

  

## 4、Ralph-loop

ralph-loop 是 Anthropic 官方插件市场 claude-plugins-official 里的一个循环执行器（官方其实还有个同样功能的插件ralph-wiggum，来自claude-code-plugins）

ralph-loop 的核心原理很简单，就是通过 **Stop Hook机制** 拦截Claude的退出尝试，然后将相同的提示词重新喂给Claude ，让Claude Code反复执行同一个任务直到达到预设的目标和迭代次数后完成（如下图所示）。

我们只需要启动一次，它就会自动迭代，看到之前写的代码、读取git历史、修复测试失败，直到任务完成。

ralph-loop skill🔗：https://github.com/anthropics/claude-plugins-official/tree/main/plugins/ralph-loop

ralph-wiggum skill🔗：https://github.com/anthropics/claude-code/tree/main/plugins/ralph-wiggum

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OTFjMDRlNDU1MTBhMTg2NjM0MTI2YTQxNWIzOGJlZDlfSnZ5S05SV0pscmx2U1o0dXl3b0xocldvZEhxNFZJOU5fVG9rZW46WE1SaGI0ME1Db0c4Qk14ZURuaWM1YXdXbnBmXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

单独用ralph-loop可能会跑偏，所以两个Skills可以结合使用，先用planning-with-files Skills让Claude Code生成任务计划，然后再用/ralph-loop启动循环执行。

  

## 5、NotebookLM Skill

现在不止Gemini和NotebookLM打通了，Claude Code等任何支持Skills的AI工具，也都可以通过这个 **NotebookLM Skill** 实现相同的能力。

这可以用在什么场景下呢？比如AI写作，以及其它需要高质量RAG知识库的场景。

NotebookLM Skill🔗：https://github.com/PleasePrompto/notebooklm-skill

  

## 6、Obsidian Skill

原本是Obsidian CEO问大家给Obsidian写了什么好玩的Claude Skill，结果好像没有和Obsidian相关的，所以他自己下场写了三个：

Obsidian Skill🔗：https://github.com/kepano/obsidian-skills

- **Obsidian Markdown Skill**：写出Obsidian风格的Markdown文件，支持所有Obsidian特定语法扩展（wikilinks、embeds、callouts、properties等）
    
- **Obsidian Bases Skill**：把笔记变成数据库（支持表格、卡片、列表、地图等多种视图类型）
    
- **JSON Canvas Skill**：可以用Canvas无限画布来画思维导图/流程图等，非常适合用来做知识可视化
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MDU5YTJmNmMzNWVkYThhNjZmMmQ5YTI5NmViNWVkYzBfbWtoTkhCRmo2TEJoWjNxM0UzRVJzc3pFaENUaVA3a0pfVG9rZW46RVpoT2JnbXdPb0x3R2l4VzI0N2NmNkozbjdiXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

## 7、React Best Practices

这是Vercel官方发布的，将他们过去10年的React功底浓缩成了一个Skill，他们的CEO戏称“用这个Skill相当于雇佣了一个mini版的10年经验React开发者。”

更多介绍🔗：https://vercel.com/blog/introducing-react-best-practices

React Best Practices skills🔗：https://github.com/vercel-labs/agent-skills/tree/main/skills/react-best-practices

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OTI0MmM1MzgzN2VjOWE5ZGUxOTU0ZDA2MjE3NTkyOTFfbEVmdHJwTHZyZE02d05TWkozOE1NeTluWllPd0pVZW5fVG9rZW46WFYxRGJ6QWpFb2dYdWl4VFdCV2NFRU1zbjFiXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

## 8、Agent Browser

这个项目也是Vercel官方发布的，一个轻量级、交互式的浏览器控制壳层，适合一次性任务或简单自动化工作流，对比 Playwrigt MCP和Chrome DevTools MCP，Agent Browser Skill处理复杂任务更快，也更省token。

Agent Browser🔗：：https://github.com/vercel-labs/agent-browser

具有类似能力的 Skills 还有Dev Browser（需要搭配Chrome插件使用），之前在知识星球也分享过他们的区别。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YWFkNDZkYTgzZTFkNGY4NDM4YTQ2MjMxZTllNjIxNWVfOVdud0RtZXY1d0V1RkRkUXVOU1FSV21kYXpzN3FhS3BfVG9rZW46WDRBUmJZUUQybzU3Skp4Q2lSZ2NQWGNPbkpjXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

## 9、skill-creator

这个Skill来自Anthropic官方，是用来创建Skill的Skill，大家后续在[Skills的制作（含制作技巧）](https://my.feishu.cn/docx/A43ldBvRTop4exx6t2DcvPrpn8b?from=from_copylink)中会经常用到。

> 注：虽然skill-creator skill是官方给出的，但它其实也有一些瑕疵。因此开发者社区也出现了一些根据自己实际情况调整的skill-creator skill（没有好坏之分，关键看能否解决自己的问题）

https://github.com/anthropics/skills/tree/main/skills/skill-creator

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NDIxZDQwMzI0NTA0NjE4YTlmYWNiNTY4NGYzMGY0ZmNfZGZqRHh3RExHTXFqREo3ZGNTUzdXTlZ3VDdGNzZOazZfVG9rZW46VEVCZmJJY1l2b0JiOWZ4ZWRmbWNCUTlSbjNlXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

当然，实用的Skills远不止前面介绍的9个，大家可以通过接下来分享的这6个高质量资源库，快速找到自己想要使用或学习的其它Skills。

  

# 高质量 Skills 资源库

## Claude Code官方Skills库

Claude Code官方的Skills库有两个（严格来说有三个，其中一个没维护了），是他们不同时间段发布的，两者存在一些重叠的Skills：

早期的：https://github.com/anthropics/skills

最新的：https://github.com/anthropics/claude-plugins-official（我们前面介绍的Frontend-design skill和ralph-loop skill都在这个仓库）

  

## awesome-claude-skills

GitHub上awesome系列的仓库基本不会太差，这里收录了四个stars数较高的awesome-claude-skills仓库：

https://github.com/ComposioHQ/awesome-claude-skills

https://github.com/travisvn/awesome-claude-skills

https://github.com/BehiSecc/awesome-claude-skills

https://github.com/VoltAgent/awesome-claude-skills

  

## skillsmp

这个Skills网站收录了目前GitHub社区超8W+的开源Skills，应该是目前收录Skills数量最多的网站。

支持 AI 语义搜索和关键字筛选，也支持按分类浏览、按热度排序。

🔗：https://skillsmp.com

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDMyYWI3ZjYwMjRmNjNmZWFlNDI0ZWQxNzQxNGE4ODFfVVJDeXJBZGpYbVhmNHlXWTR2MFdtRFdzQnZrWjlKQXZfVG9rZW46TG1reGIyRk5Sb1Z2NHB4UEFNVWN2dXdCbm1nXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDU0ZWFhNWFiMGQ2YjNlNzUxMDE0OGViNjRkNzMzMTBfMUwwcVNhcDllc3JtdkdZdW5CQ05JdGZTT1VXenNzaFdfVG9rZW46S01aeGI5d3FXbzJ5Qll4VUd3T2NlNUZJbkpiXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

## Skill.sh

前面分享过Vercel官方的三个很实用的Skill项目：React-Best-Practices、Agent Browser以及 add-skill。

这回他们把这些项目整合起来，做了个网站：https://skills.sh/

这个网站提供的核心服务有两个：

第一，通过add skill这个库，实现在不同AI编程工具中快速安装各种Skill；

第二，提供Skills安装排行榜，分总榜和24h榜，大家可以从24h榜快速了解最近都有哪些热门Skills。之前分享的一些热门Skills，比如Vercel官方的、Anthropic官方的、@宝玉老师的、SEO相关的，基本都在榜上。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDY5NDZmYjdkMGY1YmVhM2U4M2E3NjJiZWRlYTY4NmJfWHJqR2NaWHROZVFzQURMWDBtc1p2UXpYRHJuSWRBajFfVG9rZW46U1lUemJKY0d2b3c1clN4QUFFamNRMDVmbnZZXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

## claude-scientific-skills

这个Skills资源库比较垂直，是专门科学研究的，目前包括 138 个科学Skills，涵盖生物学、化学、医学、物理学和工程等多个领域。

🔗：https://github.com/K-Dense-AI/claude-scientific-skills

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YmE4NmUzMjc3NWJlNzUxOTMzNTEyMDA1Nzk2ZjNhZTVfbnI4UGsySlR6S3Zvbm9LbDFTc29XOVFRMnRpZFVQbnJfVG9rZW46QW8yZ2JTMUlZb3hwNHR4MWN0SmNodFprbmVoXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

## @宝玉 Skills

个人开发者的Skills仓库，我个人学习比较多的就是@宝玉 老师的。

@宝玉 老师本身是Prompt、AI编程、Skills的深度实践者，这个开源仓库基本是把他日常工作流（比如文章智能插图、封面图片生成、漫画创作、公众号发布、X发布等）都公开出来了。**大家可以从他的Skills中学习Skils工作流拆解：**

🔗：https://github.com/JimLiu/baoyu-skills/tree/main/skills

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YTZiNDdjNzMwYWM3OGYxYTdlZjUxMjJmMTI1MTQyYzhfU3pzT0t1UUI4UTlGaTRwYnFoY2lXU0FjblRkWE0xNm5fVG9rZW46VDVzSWI3bXZvbzVRaUF4UTFnamNyd080bktnXzE3Njk2NzA5Njk6MTc2OTY3NDU2OV9WNA)

  

  

## awesome-moltbot-skills

这是由社区驱动整理的 Skills 库，专门用来武装 moltbot（原clawbot）的

GitHub🔗：https://github.com/VoltAgent/awesome-moltbot-skills

在线版🔗：https://clawdhub.com/skills