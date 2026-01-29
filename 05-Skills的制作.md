
目前Skills的制作大致可以分为两类。

一类是以Claude Code为代表的，借助skill-creator skill，在本地制作Skills（工具使用本身有一定门槛）；

一类是以扣子为代表的，全程用自然语言对话，在云端制作Skills（工具使用门槛较低，适合大部分普通人）。

# 在Claude Code中制作Skills

这里默认大家已经安装好了Claude Code，如果是初次接触Claude Code，可以直接问AI怎么安装，也可以查看我之前分享的这篇教程。

暂时无法在飞书文档外展示此内容

## 案例一：「英文博客翻译」Skill

我平常有阅读英文博客的场景，遇到好的博客会保存为中英双语两份文档。这是一个比较标准化的流程：

```Markdown
获取博客内容并保存为英文版markdown→根据英文版markdown翻译为中文→审阅译文并润色输出为中文最终版
```

所以可以考虑固化为Skill。

### 步骤一：安装skill-creator skill

用前面介绍的[Skills的安装和使用](https://my.feishu.cn/docx/MUbJdNaAvoTONsxlbqCc6MMDnUf?from=from_copylink)完成skill-creator skill的安装。

可以在插件市场里安装，也可以让AI帮你安装：

```Markdown
帮我安装 skill-creator skill，skill的项目地址是：https://github.com/anthropics/skills/tree/main/skills/skill-creator
```

  

### 步骤二：梳理需求并形成提示词

提示词其实就是对前面流程的细化，描述清楚这个Skill有什么用，主要包括四个部分

- **Skill的用途。**例如，“获取英文博客URL并将它转换为Markdown文件，同时将英文Markdown文件翻译为中文”。
    
- **Skill的触发方式。**例如，“当用户想要保存并翻译博客文章时使用”。
    
- **Skill的输出要求。**建议这部分尽可能详细，比如规定Markdown文件的命名格式，规定Markdown文件的保存位置。如果不提前规定好，AI就会自己发散去输出，比如将Markdown文件保存到 .claude/skills 的目录下（别问我为什么知道，问就是踩过坑）
    
- **Skill的所需资源**（非必需，具体看你要制作的Skill的类型）。其实就是前面讲到的Skill资源层，你可以提供Skill所需的脚本、参考文档或资源文件。比如我后面会提供润色prompt和术语表
    

```Markdown
我要创建一个「英文博客翻译」Skill，这个Skill可以获取任意英文博客URL并将它转换为Markdown文件保存在本地，同时支持将英文Markdown文件翻译为中文保存在同一目录下。

1、核心流程：
步骤一：获取英文博客内容并保存为英文版Markdown（用python脚本固定）
步骤二：根据英文版Markdown翻译为中文（将翻译prompt固定）
步骤三：审阅译文并润色输出为中文最终版（将润色prompt和术语表固定，稍后提供）

2、输出文件：一份英文版Markdown，一份中文版Markdown

3、输出文件要求：保存的Markdown文件按域名组织，例如：

<项目根目录>/
└── <domain>/
    └── <blog>.md
    └── <中译-blog>.md

- <domain>：即站点名，如github.com、mp.weixin.qq.com
- 英文版Markdown文件命名：<blog>，从页面标题（首选）或 URL 路径中提取信息，转换为 kebab-case 格式，2-6 个单词
- 中文版Markdown命名：<中译-blog>，即在英文版Markdown文件命名前加上  中译- 进行连接

4、触发时机：当用户想要保存并翻译博客文章时使用。
```

  

### 步骤三：用skill-creator skill创建新Skill

输入步骤二的提示词，Claude Code就会调用skill-creator skill帮你创建Skill；

> 注：我在这个过程中遇到Claude Code没有调用skill-creator skill而是调用了superpower skill的情况，这也是目前Skill的局限性之一，如果你的Skill描述不够精准，会存在调用错误的情况。
> 
> ![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OGU2ZTEwNGFkMTk0Y2I5MzA1ZDA2NzI5ODM1NjZiYjJfWXZXSTJRenpiYzlqMXUyMGtKRWtTOXZBN1ZHVk5wZVpfVG9rZW46VzZmN2JnN2NVb0VrSDV4RDFFeWNxWG53bnVCXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)
> 
> 关于Skill的局限，有单独一节详细展开>>>[Skills的局限与应对](https://my.feishu.cn/docx/YXCQd37kxotfzqxjNNGczWXGnZ3?from=from_copylink)

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=N2Q4YzRlOGYzY2NlMjExNGJlZDFmYTA4YzhlYTQxYjlfakJtbDRST1FvOHZPZmVuUFJDSmw4SFlvY3RJbDlmVENfVG9rZW46UHlLd2JVMHU5b3hjY2l4dUFycmNKWW9xblRnXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

### 步骤四：测试并迭代Skill

当Skill创建完成后，就可以测试生成的Skill是否符合要求。Skill测试通常建议关注以下两个问题：

- **是否稳定触发**：验证Skill的触发条件，是否能在预期的场景中稳定触发。
    
- **是否稳定执行**：检查Skill的处理流程，查看是否有跳过或遗漏执行的步骤、最终输出的结果是否符合要求。 可以多找几个不同的案例来测试，尽可能覆盖一些没考虑到的边界情况。
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YjcyYjViZmZlZGU0MjEwOTM0Mzg5ODc1YmRjZDViYzhfN2NGbERpaEFpVWtZYzlQRm1OeHYwWXo1VGhibU1tc2JfVG9rZW46R2dQaGJ1dU9hb0xWVWF4QUpHbGNlSGlObmxnXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

### 步骤五：创建 Plugin 并上传新 Skill

如果你想要将自定义的 Skill 分享出去，除了直接分享本地文件，还可以通过创建 Marketplace 和 Plugin 的方式实现。

对于非开发者，如果看官方文档（https://code.claude.com/docs/en/plugins）去创建，可能会觉得很头大。没关系，可以直接把文档发给 AI ，让AI帮我们创建：

```Markdown
https://code.claude.com/docs/en/plugins,请根据官方文档创建marketplace和plugin并将extension-icon skill打包进去
```

通过 Marketplace 和 Plugin 分享的 Skills 有个好处，就是当你更新 Skills 后，那些安装了你的 Skills 的用户，就可以通过 Marketplace 进行更新。

  

## 案例二：「Chrome插件图标」Skill

我之前还分享过另一个案例，就是用Claude Code开发「Chrome插件图标」Skill，解决AI开发Chrome浏览器插件不配置图标，以及SVG图标转格式的问题。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YTA3YzM5MjY0MTc4NzRjYWE1YWZlOTM1NDg3MjlmZTNfdXJNTG5MNXJ3UmtXY01raHZYTHlhSWdrV2J2UnVINzhfVG9rZW46VFZOTWJrbWY2b3RjU1F4M0JvMWM4Ym9xbmZOXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

如果你有现成的SVG图标，这个Skills就会调用Python脚本，直接将SVG图标转为Chrome浏览器所需的四种标准尺寸（16×16、32×32、48×48、128×128）的PNG图标；

如果你没有现成的SVG图标，这个Skills就会先从Iconify图标库搜索符合要求的SVG图标并下载下来，然后再调用Python脚本将SVG图标转为四种尺寸的PNG。

对这个案例感兴趣的精神股东可以移步查看：

- 文字版：https://mp.weixin.qq.com/s/7VUIzD0tnkImN8atADEGRg
    
- 视频版：
    

暂时无法在飞书文档外展示此内容

注：不同于案例一，案例二的制作方法是先进行脚本验证，然后再用skill-creator skill将脚本打包进Skill。

  

### 实践思考

在这个案例中，它的标准流程可以拆分为三步：

1. **图标搜索**：根据输入的关键词（如 "beer"），在iconfont、font awesom等主流图标库查找图标；
    
2. **图标下载**：自动下载第一个匹配结果的 SVG 文件；
    
3. **图标格式处理**：将 SVG 转换为 Chrome 插件要求的 4 种 PNG 尺寸。
    

虽然这三步都可以用一个脚本来实现，但对于已经有 SVG 图标只想转格式的场景，我就没法用这个脚本来实现 SVG 图标转 PNG 了。

所以这时候更好的选择，是搜索和下载图标用一个脚本实现，SVG格式转化用另一个脚本实现。**这就是 Skills 制作中比较推荐的“原子组合”方法。**

  

  

# 在扣子中制作 Skills

## 案例一：「中英文混合排版优化」Skill

这个案例是通过提示词一次性生成Skill。

我有个写作场景是这样的，需要在【英文/数字】和中文之间保留1个半角空格，如果手动操作半角空格非常重复低效，这种场景完全可以通过 Skill 来解决。

### 步骤一：梳理需求并形成 Skill 提示词

1. 在 [扣子编程](https://code.coze.cn/) 首页，选择「技能」选项卡
    

> 注：可以直接打开扣子编程，也可以在扣子「技能商店」点击「创建技能」快速跳转扣子编程

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OWUyYTZlZDViYjIyMzRmNmU2ZGJjMTgxNmNhNjgwNDBfaXUwSU1RdnA0ZU1NUGVUVnJOaHc0c0tYNTV3RUpLbzhfVG9rZW46THJ4ZmJQNWVab2ZGQ2R4Yk5vZGNLaGNvblBiXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

2. 在对话框输入我们的Skill提示词
    

比如我想制作一个用于「中英文混合文本排版优化」的Skill，对应的提示词是这样的：

```Plain
我想创建一个[中英文内容排版]的 Skill，用于[优化用户上传的、包含中英文内容的文章排版]，当用户提及[帮我优化中英文内容排版]时，就会调用这个 Skill，输出优化后的文章排版，文章排版遵循【英文/数字】和中文之间需要保留1个半角空格
```

当然，你也可以写得更详细，这直接决定Skill的逻辑、交互效果和稳定性。

和前面的介绍一样，Skill提示词一般会包括四个部分：

- **Skill的用途。**例如，“用于优化用户上传的、包含中英文内容的文章排版”。
    
- **Skill的触发方式。**例如，“当用户提及「帮我优化中英文内容排版」时，就会调用这个 Skill”。
    
- **Skill的输出要求。**例如“输出优化后的文章排版，文章排版遵循【英文/数字】和中文之间需要保留1个半角空格”。
    
- **Skill的所需资源**（非必需，具体看你要制作的Skill的类型）。其实就是前面讲到的Skill资源层，你可以提供Skill所需的脚本、参考文档或资源文件。
    

  

接着扣子编程就会开启云端的沙盒环境，调用各种工具来制作Skills；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2U1YmQ2MzQ4ODE3NzcxMjkzOWRlMWRiODlmMmU1MmNfTU01T1Zlc29GSGhQTjJ1bmF3RWZSMXYxVTVZdXpNdzRfVG9rZW46TFdBSmJobmtVb3NtRkl4djc3TGN2TUxqbkloXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

### 步骤二：测试并迭代Skill

Skills制作完成后，接着就可以测试生成的Skill是否符合要求。

扣子编程的Skill开发页面的右侧是调试区，比如我这里就是上传一份本地文档，来检验中英文混合文本的排版优化情况。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDFkZTM2MGJjZjhiMWMzNDhiNWQzNTNlMjc2Y2YxNzNfSTY0M2l6N0R4QkIyaTJoU01VVFhXWEZIMDc0TDhNdXVfVG9rZW46WDVzRWJySDB1b21sYkR4Mjc0emNTZlpIbk1nXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

Skill测试通常建议关注以下两个问题：

- **是否稳定触发**：验证Skill的触发条件，是否能在预期的场景中稳定触发。如果扣子调用了Skill，对话区域会展示“完成技能加载”的提示。
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MmRlNzY0ZGZiY2IwMjAwODE1NDVkY2ZiYmEyNTFhNWRfTGRuek5oR1Aza1ZwQzNJMjhsbmVuSjlNSElET3QzTWNfVG9rZW46REZTZGJyUTZTb00zT1V4SlR4S2N1cDBvblFmXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

如果没有触发，你可以和扣子继续对话让它约束触发条件，或者自行编辑 SKILL.md 的 description 部分，明确说明Skill的触发条件。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ODRhZWE1NjU0YjkxM2EzNzkxNzcwZDE0OGVmNWIwNGRfODd5bUFqSEtpS0U3TkUwbjhJd3RXVnI5bHFVMmNHU3RfVG9rZW46TVVramJhME93bzBIRFp4RmRGaGNhc3BKbmg1XzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

- **是否稳定执行**：检查Skill的处理流程，查看是否有跳过或遗漏执行的步骤、最终输出的结果是否符合要求。 可以多找几个不同的案例来测试，尽可能覆盖一些没考虑到的边界情况。
    

> 注：扣子Skill的每次修改都会记录版本号，如果你觉得这次修改不满意，可以点击「回到该版本」实现回滚
> 
> ![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OTg1YjE0Njg4ODk2NTNjZWE0NDA5ODIwZTYwOTJkYjNfb3NoT2JMMXRyVmFyVnJBUkpnTEREaHQ0MEJwdUE2UFFfVG9rZW46SWkwVWJCMXRpb1NZTUV4bnF3dGNDVE15bk1iXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

### 步骤三：部署Skill

完成Skill的开发与调试之后，你需要部署Skill，才能在扣子对话中使用。

在Skill的开发页面右上角点击「部署」，根据页面提示确认技能的部署配置之后，单击「开始部署」即可。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZGFhNmI4Nzc5MDE0YzllOTMzZWRjNGY3MDJkMzAxMjJfVUNPSTkwTTVCNllPeFJ2Wkh3empMQXZGbDZJcVVyWXBfVG9rZW46SHNYU2I5V3pib29jMFB4d0V0SmNpWXlSbm9lXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

等个十几秒，就会看到部署成功的提示。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ODY0NjU3NzBkYjVlNDBlMTk2NmRhN2ZhYTc0OTU5Y2JfRllseUg4UTYzaVpETm5BZDEyUmJhYzNmR21CeU53cHNfVG9rZW46TEhrbmJkWFdYb2hEYVJ4cDhpNWNCV2FHbmNiXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

## 案例二：「英文博客翻译」Skill

不同于案例一，这个案例是我和扣子进行了多轮对话，最后得到了一个符合要求的产物。

由于这个流程是比较固定的、输出格式明确、有令人满意的样例，所以可以将它制作为一个技能，相当于“可复用的操作说明书”，方便后续在类似场景中直接复用。

### 步骤一：多轮对话得到符合要求的产物

1. 在 [扣子](https://www.coze.cn/) 首页，输入初始任务需求。
    

> 注意：这里用的是扣子，而不是扣子编程。我之前误以为在扣子编程中也能跑，结果我把提示词输进去，它给我返回了个翻译工具站。

```Markdown
将这篇英文博客翻译为中文：https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills
```

由于最开始还不太清楚自己想要的译文规范，所以提示词会写得很简单。我想看到第一轮翻译结果后再调整。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OTJiZjg5NzEzMDA4YjQ1ZWE1OTllMzI5YjA2NTU4NGJfZ3lHaUk3VzZJcG9pVjA5YkozZkk1eGdyTVloVHF6emhfVG9rZW46R3ZvSmJaTENPb3RMY1V4Q29vS2NPOFlwbjFiXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

2. 根据第一轮翻译结果，给出优化任务（要求译后审校，同时给到参考的术语翻译表）。
    

```Markdown
进行译后审校：对照原文与译文进行批判性评估，提供具体改进建议。最终译文的语体风格应符合中国大陆简体中文的口语化表达习惯。审校需关注： 
1. 准确性：修正增译、误译、漏译及未翻译内容 
2. 流畅性：遵循中文语法、拼写与标点规范，消除冗余重复 
3. 风格适配：保持与原文风格的契合度，兼顾文化语境转换 
4. 术语统一：确保术语一致性并符合专业领域特征，中文习语需采用对等表达  

翻译时请严格遵循以下术语对应关系： 
- AGI -> 通用人工智能 
- LLM/Large Language Model -> 大语言模型 
- Transformer -> Transformer 
- Token -> Token 
- Generative AI -> 生成式 AI 
- AI Agent -> AI 智能体 - prompt -> 提示词 
- zero-shot -> 零样本学习 
- few-shot -> 少样本学习 
- multi-modal -> 多模态 
- fine-tuning -> 微调 
- Agent Skills -> Agent Skills 
- Skills -> Skills
```

然后扣子会给到一份译后审校报告。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=N2MxNjMxZTIzOWQ4YWE4MzRkZmE2MzlmOGY4NGY3MWFfOG9HS3hvMXcwVExQYXd5VmtnOERQcXlSZnRlUElaQlRfVG9rZW46U3RHeGJ6Zld3bzRRN3F4RllVRGNkVTZKbk9mXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

3. 根据第二轮翻译结果，进行最后一轮润色。
    

```Markdown
进行译稿润色：综合前两步成果，对译文进行精细化打磨
```

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MjBlZmE2ODA1NDRmNjVmNWRjYWQxYjM4YzA3ODg5NTNfQURxdE5RTkRVMUtoQk5ZaGVFRlJxdDY5WVFVMmpKNkdfVG9rZW46SmFmd2JjQnpIb1Z2eHh4ZGNWU2MzZjM4bldnXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

当你觉得这轮的译稿符合要求的话，就可以进入步骤二。

  

### 步骤二：将扣子对话固化为Skill

1. 输入下面这段生成Skill的提示词，扣子就会把生成Skill的任务移交给扣子编程；
    

```Markdown
帮我将以上处理流程制作为技能，已生成的产物可作为风格、格式的参考。
```

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NzFlNGYyZDY5ZjgwNTViNzQ0NGYxODhmYzljZmM3ZjhfSXAxRWFLdGZuamMyT3JsY2VOZUtVYTN5aU9VQWpyYU5fVG9rZW46T2JaOGJrRWFhb3JPUHR4S29GdWNMSDR4bnpkXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

2. 扣子编程会将前面的多轮对话总结为一段详细的提示词，然后在云端的沙盒环境自动跑任务；
    

> 注意：这里的提示词相比之前多轮对话的内容，是存在信息缺失的

```Markdown
我想要创建一个能够完成翻译、译后审校和译稿润色全流程的skill。这个skill需要有以下功能:
(1)接收英文技术博客URL作为输入,获取完整内容并进行初步翻译;
(2)对照原文对译文进行批判性审校,识别准确性、流畅性、风格适配和术语统一问题;
(3)根据审校结果对译文进行精细化打磨,使其符合中国大陆简体中文的口语化表达习惯。

我对输入的要求包括英文技术博客URL(必需)和术语对应关系(可选),我希望输出格式包含原始译文、审校报告和润色后的最终译文。

标准化工作流程:
第一步,获取英文博客内容并进行初步翻译;
第二步,对照原文进行译后审校,生成包含具体改进建议的审校报告;
第三步,根据审校报告对译文进行润色,生成符合口语化表达习惯的最终译文。

我特别强调需要严格遵循给定的术语对应关系,确保术语一致性。
```

最后扣子编程会给到你一个打包后的 Skill。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjY4MmUxNDEwOTM5OWZlY2M5YWViOGY3OTQxY2NhOTFfWjFFc3FidW40OGFMNHNpSzcyWlhvN1VPa0FLOFZmRklfVG9rZW46SWNWM2JGRThEb1A4MmR4aW9uaGNwTmVlblpnXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZGVjYmJhYzlhNDQzZmIxZmM3MWEyZjI0MjQ0MjZlMjdfNXpmUmkyZzNLeWtwajRQYkFCcWczTzQwVFR4bkVOa1VfVG9rZW46S1pKZGI5YW5Gb1ZCZDJ4emw2TWNUcjNCbmpkXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

  

### 步骤三：测试并迭代Skill

这一步是最后一步，测试生成的Skill是否符合要求。

右侧是调试区，比如我这里就是输入一篇新的英文技术博客，来检验翻译流程和结果。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MGE2M2RjZDEyNjBlNTJjNmZhMDgyN2NlZDU2NWNhNDlfcFdMMGJOMVJoNklsdE1wbWF1VG1wNnp4eFlNQXhzNHZfVG9rZW46Q2N1b2JVOUhJb3hrNDF4RVNzYWNLWHUwbnZoXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

完成测试后就可以部署上线了，流程和案例一一样，这里就不做赘述。

  

> 注：如果你想要将自己制作的扣子技能上架到「技能商店」，官方文档有非常详细的介绍，这里不做赘述。
> 
> 暂时无法在飞书文档外展示此内容

  

  

# Skill制作最佳实践

这里整理的最佳实践，大部分来自[Anthropic官方：Skills制作最佳实践](https://my.feishu.cn/docx/PW2MdTU1pon4stxI8ILcqaimnBf?from=from_copylink)，更详细的内容可以移步原文档查看。

## 核心原则

- **简洁是关键**：只添加 AI 原本不了解的上下文。
    
- **设定适当的自由度**：根据任务的脆弱性和可变性调整具体程度。
    

  

## Skills结构

- **SKILL.md-name**：尽量采用动名词形式，比如`processing-pdfs`、`writing-documentation`，避免名称含糊不清，如`helper` 、`documents` ；
    
- **SKILL.md-descriptions**：要包括Skills的功能和触发条件/使用时机。这样Agent才知道什么时候选择这个Skill
    
- **SKILL.md-渐进式披露原则**：将 SKILL.md 正文控制在 500 行以内。接近这个限制时，将内容拆分为单独的文件
    
- **Skills-资源层**：资源层应保持在 SKILL.md 的一级目录 。所有资源层文件都应直接链接到 SKILL.md，以确保Agent在需要时能够读取完整的文件。
    
- **Skills-资源层**：对于超过 100 行的资源层文件，请在顶部添加目录。这样即使在预览部分读取结果时，Claude 也能看到所有可用信息。
    

  

## 工作流和反馈循环

- 将复杂的操作分解成清晰的、循序渐进的步骤。对于特别复杂的流程，提供一份清单，Agent 可以将其复制到回复中，并在执行过程中逐项勾选。
    
- 实施反馈回路。使用“运行验证器 → 修复错误 → 重复”这种反馈循环模式，能显著提高输出质量。
    

  

## 双Agent开发Skills

核心思路就是，使用Agent A来创建Skills，然后在Agent B中测试这个Skills。将你在Agent B观察到的一些问题反馈给Agent A进行迭代优化。

  

## 有效的Skills清单

在分享Skills之前，验证：

### 核心质量

- Description具体并包含关键术语
    
- Description包括Skills的功能和使用时机
    
- SKILL.md 正文在 500 行以下
    
- 更多详情放在单独的文件中（如果需要）
    
- 没有时效性信息（或在"旧模式"部分中）
    
- 整个Skills中术语一致
    
- 示例要具体，不要抽象
    
- 文件引用是一层深度
    
- 适当使用渐进式披露
    
- 工作流有清晰的步骤
    

### 代码和脚本

- 脚本是用来解决问题的，而不是推卸给 Claude
    
- 错误处理机制清晰明确且有帮助
    
- 没有"神秘常量"（所有值都合理化）
    
- 说明文档中列出了所需的软件包，并已确认可用
    
- 脚本有清晰的文档
    
- 不使用 Windows 风格的路径（全部为正斜杠）
    
- 关键操作的验证/验证步骤
    
- 包含针对质量关键任务的反馈回路
    

  

### 测试

- 至少创建了三份评估报告
    
- 使用 Haiku、Sonnet 和 Opus 进行了测试
    
- 使用真实使用场景进行了测试
    
- 团队反馈意见已纳入考虑（如适用）
    

  

# 什么任务值得做成Skills？

Anthropic在官方博客中有回答过这个问题。

官方博客：[Skills explained: How Skills compares to prompts, Projects, MCP, and subagents | Claude](https://claude.com/blog/skills-explained)

> 当你需要 Claude 持续高效地执行特定任务时，请选择Skills。Skills非常适合以下情况：
> 
> - 组织工作流程 ：品牌指南、合规流程、文档模板
>     
> - 专业领域： Excel 公式、PDF 处理、数据分析
>     
> - 个人偏好： 笔记系统、编码模式、研究方法
>     

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=Yjc1MDIxZGMzZTJjMDNkYWExMTg5ZjZmY2U5ODA0YTZfUnU0cXlhQm9iWExRSEtkb0pLT3hRS2ZzcXBqNFNlakRfVG9rZW46UklqMmJaYTRObzYzQkl4NnJFbGNZeXVJbmtjXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

为了更细致地回答这个问题，我抓取了 skills.sh 安装排行榜 Top 100 的Skill，基于SKILL.md内容，对它们的任务类型分布进行了分析。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YjU5NGFlMTliZDgzMDVmOTQ5MWMwNDk4OWU3MjE0NzNfOGdsTXNmZmtKaDU5M1Q2VmZna3RRNlNlalRqMWpBWUxfVG9rZW46SElycGJMWlJHbzJBRTF4UkFyRGNsNUlkbmpjXzE3Njk2NzEwODg6MTc2OTY3NDY4OF9WNA)

然后我发现目前大家安装比较多的Skills的类型分布是这样的（注：左侧是Skills类型，右侧是对应的Skills数量）：

1. 增长/营销（SEO/CRO/投放/定价/增长策略）：23
    
2. 软件工程：前端/全栈 UI 与最佳实践：19
    
3. 内容生产（图文/幻灯片/图片/媒体处理/社媒分发）：17
    
4. 工程方法论（计划/执行/协作/评审/调试等流程）：13
    
5. 文档与办公（PDF/DOCX/PPTX/XLSX/文档协作）：8
    
6. Agent 工程（MCP/工具链/浏览器自动化等元技能）：5
    
7. 软件工程：移动开发（Expo/RN/iOS/Android）：4
    
8. 软件工程：DevOps/发布/CI/CD/依赖维护：4
    
9. 软件工程：后端/API/数据与数据库：4
    
10. 沟通与管理（会议/汇报/内部沟通）：2
    
11. 软件工程：测试/质量保障/验证（偏测试方法）：1
    

  

它们大致可以分为三类任务（这三类任务彼此可以重叠）：

- **“高频处理+有可复用流程”的任务**：这类任务目标明确，执行步骤固定，可通过标准化流程或脚本反复、高效地完成。例如，代码审查、自动化测试、CI/CD构建、SEO审计等。
    
- **“强模板化产出”的任务**：这类任务产出物的格式和风格有固定要求，核心在于将内容高效地适配到预设的模板中。例如社媒配图、PPT制作、品牌设计、报告/周报等。
    
- **“多模块/多流程组合”的任务**：这类任务本身比较复杂，需要串联或并联多个独立模块或子流程来完成。例如社媒文章的发布（收集资料+选题分析+学习文风+正文写作+配图智能插入）等。
    

  

这三类任务，也可以作为三条标准，来判断任务是否值得做成Skills。

当然，更简单的判断标准是：**这是一次性任务，还是需要反复做的任务？**

  

如果只是一次性任务，没必要做成 Skill——Skill 的核心价值在于复用。

  

如果是需要反复做的任务，建议按这个流程走：

1. **手动跑通，沉淀标准：** 先手动执行几次，厘清固定步骤，识别潜在卡点，并明确高质量输出的标准。
    
2. **示范教学，封装 Skill：** 新建会话，在支持 Skills 的 Agent 中完整演示一遍任务。确认无误后，指示 Agent 将刚才的操作链封装为 Skill，以便复用。
    
3. **循环使用，持续迭代：** 后续直接调用 Skill 执行任务。每次完成后校验输出，针对不满意之处指令 Agent 调整并更新 Skill。
    

**简单来说，**Skill 的本质是“可复用的最佳实践”。先跑通流程，再固化为Skill，最后在实战中不断打磨。