前面介绍了目前 [支持Skills的工具（持续更新ing）](https://my.feishu.cn/wiki/Amrlw53CdiDIBjkcynUcAcxpnRb?from=from_copylink)，由于工具形态的不同，Skills的安装和使用方法也有所不同。

  

# Skills的五种安装方法

## 方法一：通过插件市场安装（适合Claude Code、Coze）

### Claude Code安装Skills

以 frontend-design skill 在Claude Code的安装为例，之前有专门的文章分享过>>>，本次教程主要根据插件市场的最新界面进行了配图替换。

#### **步骤一：添加官方 Plugin Marketplace**

Plugins 是 Claude Code 推出的插件系统，它可以将 MCP Servers、上下文文件、自定义 Slashs，以及 Skills 打包成一个简单软件包。

它一般是通过 Plugin Marketplace 来统一管理，官方自己也推出了自己的 Plugin Marketplace，这里要安装介绍的 frontend-design skills 就是其中的一个 Plugin。

添加官方 Plugin Marketplace 的方法也很简单，在 Claude Code 输入 /plugin；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NmUxOWZjYmVhNDE0OTlmN2EzNTA0NTRmZGMyMDQ5NzFfNURpMWR5cFdYc2liRlhyYmRqUk5hZGNWRG5Scm9hV2RfVG9rZW46WjhmWmJZNk9Lb0VWUU14aTBLaWMzZTVibmJnXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

在打开的列表中选择 Add marketplace；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NTE0NzkzYjIxOGJlZTU4ZjdmMmI4NTY3ZmZmMTY5YjBfMHp0QVg2ZjFMNGtUc0hTWXo0WE1GdmIxckNOa2ZETU9fVG9rZW46VHdRMWJSSzg2bzhhNE54ZzVWdGM5MENmbkhiXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

接着输入 anthropics/claude-plugin-official（就是官方 Plugin Marketplace 的 GitHub 仓库地址，其它插件市场的添加同理）；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NmM0MzlmOTZmNjNjMGNmMmE0ZDM5ZGQxODZmNjczOWFfaGdXQUV4aTR5OWRhZ2RMZERLbW1iN0ZDcktlWTFDVkdfVG9rZW46VUxSRWJPZG8wb1NwaHh4dW9HNWM4Y01EbkRmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

Claude Code就会将**官方的 Plugin Marketplace** 添加进来。

因为我之前安装过，所以这里会提示“已安装”。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MTRjOWI4Yjc1MDU2NzE3MGEzMGU0NWM4MWYwNWM1NTBfdko0OUNOWHY3NUp5dWd2UENTbXJLWFFQWkp3UXE3cDdfVG9rZW46V3RvR2JzcWJIbzRMUnJ4UTJlRWNuRFFkblBoXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

#### **步骤二：安装 frontend-design skills**

回到 Plugins 管理面板，在 Marketplaces 选项下选择刚才安装的 claude-plugin-official；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=N2M2MjFlNzQyNDVmZGJkMDM1MTAyYjIxMDNkN2IzZThfVkRaT0NJNDV4aEswSkMyd1dDTTNjV244R2lXTkhlY1RfVG9rZW46QW5ISWI5Ymo5bzdVTzZ4UVBTamNIVnd1blg2XzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

在打开的 claude-plugin-official 界面中，选择 Browser plugins；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YzBiZjdhZjE3MDkyMmM5YjYwODY2YjRjYjc0MjNiOTNfeTB1cUtzS3BpUUdkZ1M0ZEJzWG5DZGdQdFE0dDd5SlBfVG9rZW46WkFGbGJ5UHRTb1RQbzl4MmFHdWNQcndCbm5kXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

接着你就会看到 plugins 列表，选择其中的 frontend-design 即可；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZmU4MDE1ZGQxNTIyY2EzODJmNGIzYzg0NTE2ZGY2MzFfeDZuaXNjbUs1TmF3THhlY1NOaFhMa2dHd2xwQU1vRTlfVG9rZW46Um5mS2JuSGR1b2tEbGd4aUpXYWNCUHpKblNnXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

在这里，你可以看到 frontend-design Skill 的简单介绍，同时你可以选择 Skill 的安装范围，有三种：

- 用户范围：对全局生效
    
- 项目范围：对当前项目（所有人使用）生效
    
- 本地范围：仅对当前项目（自己使用）生效
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OTZhNDkxYWRiYWJlMTIxZGRjN2UzNTAxYjQ2YzVlOTRfdjFNOER6Wk5rZmJkdzV3YUluMjVRY2VhTDZheW5BMzhfVG9rZW46U1JEMWJWVWNob1pGZUV4cHlvS2Npc1JobmVjXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

安装成功后，你就可以在 Installed 选项下看到刚才的 Skill。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MzliYTBiZDk5ZDZlN2Q4N2UyNTFmMzVmNzE3OWQ3ZDBfcTF3Uk1Gb0xHcnVjbHlOS21ZMVBPWUx1cTBuejdZOElfVG9rZW46RndJaGJDbEFOb3k3dGZ4SEFsOGM3Z0x2bm9nXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

  

### 扣子（Coze）安装Skills

扣子在2.0版本中推出了Agent Skills，以及搭配使用的「技能商店」。以「新年绘本」Skill 在扣子中的安装为例。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=Mzc4NGEwYmM1YzE5OWViZWQ5ZjFlMjljZjc2ZTQ3OGZfN2FPSGFRUHpmZFg4akdrRVRNY2EwWWpQajFLblVWNGdfVG9rZW46WUlDZmJqRDZ0b2lPV2J4UkZFWmNFMkJrbmhkXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

大家在「技能商店」中找到「新年绘本」Skill 并点击，就可以看到如下图所示的 Skill 弹窗，点击「安装」即可；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2E4Njc4ZjY0Zjg3N2U0OGZiMThlMzZkNDZmZmRlOThfTHF6M0J3T05seDE3bGEwUXhmdnA2Z2RWS2pCUzlidUhfVG9rZW46WkxrVWIyUVZqbzd2VlJ4eHNjVmNTZXRXbmpiXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

安装成功后，Skill 弹窗的「安装」就会变成「使用」，同时「新年绘本」Skill 会出现在「我的技能」。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OGJkYjdiNTc0ODMxZDE4YTU0MGFjZTZhZWRlN2NkODBfQjZJck8yWk9xTEdjNXZocm9Bb1p2ak9SeU5Ic1k1WDZfVG9rZW46UjJaOWJ5QXV3bzhDNmx4T09ET2NiZTJSbkRjXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ODk4NDNjZjAxN2Y4MTlmODE5NjI2M2I4OWEyYmJmNjJfdkRPcmFZSmg1UHJka1IxN0tPakJLY1NrSlkzWEJ5T3ZfVG9rZW46VGJCSWJhaVZrb0dhZnV4czY5ZWNiTFlhbm5jXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

> 注：扣子的Skill安装是在云端的，所以就没有所谓的全局范围安装还是项目范围安装的区分。

  

## 方法二：手动安装（适合IDE、CLI）

大部分Agent工具没有类似Claude Code的「插件市场」或扣子的「技能商店」，它们一般就需要手动安装。

这里的手动安装指的是广义范围的，包括你从GitHub仓库、本地文件夹，以及压缩的Skill文件包（.skill）安装Skills等。有些还需要自己手动创建Skills目录（不同工具的Skill目录有所不同，具体可以移步查看看 [支持Skills的工具（持续更新ing）](https://my.feishu.cn/wiki/Amrlw53CdiDIBjkcynUcAcxpnRb?from=from_copylink)）进行安装。

如果选择手动安装的话，建议初学者用IDE来实现，因为可以非常清晰地了解Skill目录，一般不会出错。

以 frontend-design skill 在Cursor的安装为例，其它 IDE/CLI 同理。

### 项目范围安装

#### 步骤一：创建Skills目录

用Cursor打开你的某个项目，在根目录新建 .claude 文件夹，接着在 .claude 文件夹下创建 skills 文件夹，如下图所示：

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZGQxM2Y4NDYxZDMyMmU3Yjc4NjA1MzM5NjI0MjBkMWNfbllseFJYaWxwYVpwQkt1MWFKanh0ekdLaHZYSmdhWXBfVG9rZW46QlZjTmJXaFdZb3FTQ0Z4NktMZ2N0ZmdqblFkXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

这里的目录路径，就是前面介绍的 Skills 路径，每个工具的 Skills 路径各不相同。

|   |   |   |
|---|---|---|
|工具|全局（用户级）路径|项目级路径|
|Claude Code|~/.claude/skills/|.claude/skills/|
|Codex|~/.codex/skills/|.codex/skills/|
|Gemini CLI|~/.gemini/skills/|.gemini/skills/|
|Opencode|~/.config/opencode/skill/ 或 ~/.claude/skills/|.opencode/skill/ 或 .claude/skills/|
|AMP|~/.config/agents/skills/ 或 ~/.claude/skills/|.agents/skills/ 或 .claude/skills/|
|CodyBuddy|~/.codebuddy/skills/|.codebuddy/skills/|
|Antigravity|~/.gemini/antigravity/skills/|.agent/skills/|
|VS Code|~/.copilot/skills/ 或 ~/.claude/skills/|.github/skills/ 或 .claude/skills/|
|Cursor|~/.cursor/skills/ 或 ~/.claude/skills/|.cursor/skills/ 或 .claude/skills/|
|Windsurf|~/.codeium/windsurf/skills/|.windsurf/skills/|
|Kilo|~/.kilocode/skills/|.kilocode/skills/|
|Trae|~/.trae/skills/|.trae/skills/|
|Factory|~/.factory/skills/|.factory/skills/|
|Goose|~/.config/goose/skills/ 或 ~/.config/agent/skills/ 或 ~/.claude/skills/|.goose/skills/ 或 .agent/skills/ 或 .claude/skills/|

  

#### 步骤二：下载具体的Skills并拖到步骤一的目录下

很多项目会同时包含多个Skills的，比如 frontend-design Skill 所在的 anthropic/skills 项目（https://github.com/anthropics/skills）中就包含了16个Skills。

如果你不考虑内存占用等问题，最简单粗暴的方法就是将整个项目下载下来（点击下图的「Download ZIP」按钮），

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MzdhN2Q4NDg2OWZkZGJmMTFjODIxZTE4MzU1MTYzNzRfdElKZzRRbTJFdW1UbUlNMmt4ekIzUjBocUxpdnJ3UldfVG9rZW46RDhYQWIyMUtkb1lCVFF4V0x5T2NvMzV2bm1lXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

解压缩后将 frontend-design 整个文件夹拖到步骤一创建的 skills 文件夹下。注意层级关系即可。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjFjYTQxNDMyZTE5MGFiZmExNzk0NGM5NTNiZTcxMWNfeFZoS1JsdkVsdERwVElXd2UxbWxRMENjZnJzOWxWa0JfVG9rZW46U2oyRGJlZUpPb0xlcnB4b3JOSWNHcFlPbjhlXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

但如果你只想下载 frontend-design 这个skill的文件夹，可以使用下面两种方法：

  

**方法一：使用 DownGit 在线工具**

这种方法无需安装任何软件，适合偶尔使用的用户。

1. 访问 DownGit 网站（https://downgit.github.io/）。
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MDM0M2RhM2M0NGMzOWFjM2FjZDkyMTRmZDZmYjA5MDlfOGozbXJzakZDakRndGZuRXdWMEhoaXBiNThOQkhvSzdfVG9rZW46UUxEYmJiVWJ2b2dvVU94SVk4WGN6aHhRblNlXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

2. 将 GitHub 上文件夹的页面链接粘贴到输入框中。
    

比如 frontend-design skill 文件夹的链接是>>>https://github.com/anthropics/skills/tree/main/skills/frontend-design

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MTc4ZWM3ZTk1NmM4MzUyOTMyMDVhNGY5MzhhMWVmZDNfMDJhRUI1cEJYS0RST2xmV0lkdlJKeG4weWxqeWhhSFFfVG9rZW46TVM1RGJrbUdHbzJJYW14YXBIRGNqSUlPbnlmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

就复制粘贴到 DownGit 网站的输入框中。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MjJiMGZmY2UzNjA3MzJlODMyMzY1MDI4MTgyZDI3ZWNfa3VYUERaRElxeTJkQ2R2WFJvUGtGTk1mejlVcWwwbTZfVG9rZW46RzFpMGJqRnZvbzVxUmp4MXNWTmNKMnlRbmFmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

3. 点击 **Download** 按钮，即可获得该文件夹的 ZIP 压缩包
    

  

**方法二：使用 GitZip 浏览器扩展**

适合需要频繁下载的用户，支持批量选择。

1. 在 Chrome / Firefox 等浏览器中安装 [GitZip for GitHub](https://chromewebstore.google.com/detail/gitzip-for-github/ffabmkklhbepgcgfonabamgnfafbdlkn?hl=en) 插件。
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YjA4ODE3ZWM1OWExZjE4Y2U2NzhjZDU5ZWQzZWExYWNfSk9DSFRoS3F6cnhybm53c3BCU2tHS1N6VkFLblRUeW9fVG9rZW46SmJsdWJvcmN0bzdqakJ4a2F3TGNVSjhlblZkXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

2. 在目标文件夹右键菜单中依次点击「GitZip Download-Current Folder」，即可完成下载
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MGZmNjdhNDg5OTllODA2OGRjNzcyZGNkMzdlOTcxZTVfV2syNkRpMld1dXd0RUplRkVHYmcyV0s0czhIYklGdXJfVG9rZW46VTJZVWJlY1Rwb1EyTk94SmxrNmNja3lUbnNjXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

需要注意的是，GitZip插件下载的Skill文件夹的命名是带GitHub项目路径的，在实际使用时需要去掉前面的路径，只保留Skill名。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YzkzMjljMWMxODdlYzNjYmNhYmM5YWMwOTliOGViYTNfNXFFZ0hnSk1nSnl6cVU0bXpuUEV4WWZlS2pEbjRTaDhfVG9rZW46QllMN2I2aUFmb2FBWkR4WlJoQmNVcU9RbldmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

当然，如果你熟悉命令行的话，也可以用SVN进行安装。这里就不做展开。

  

### 全局范围安装

全局范围安装和项目范围安装的核心流程是一致的，区别在于怎么找到Skills在不同工具中的全局路径。

一种方法是让 AI 帮我们找（但这种不一定在每个Agent工具中都100%有效），如下图所示：

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDZiM2VhN2Y2YmFlNWIxMGQyZTNjYjdiMDAwYTZiOTlfUDBkNThaUXhJVVhwRjFCRDB2Z1VRRkZzZ1lYZGpScmxfVG9rZW46QW5ramJNdFY1b2ZUMFF4bjJKMWNMclZGbnViXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

另一种方法就是根据前面给到大家的Skills的全局路径去找。

比如Codex Skills 的全局路径是 `~/.codex/skills/`，它代表当前用户的**主目录**。在 Windows 和 macOS 系统中，这个主目录的具体位置不同，因此完整路径也不同。

在 macOS 中，`~`指向 `/Users/<你的用户名>`。对应路径的完整形式为：

```Plain
/Users/<你的用户名>/.codex/skills/
```

比如我的用户名为 caicai，那么完整路径就是：

```Plain
/Users/caicai/.codex/skills/
```

由于文件名以点（`.`）开头的文件在 Windows、macOS 和 Linux 中默认都是隐藏的，需要先让它们显示出来，后面才能添加Skills文件。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YWI0N2FkMzk3ZmFiYzNkOWE2YjQzMjQ0YmVkZjk0MjhfbDBaSnRBenR4cHAyeVBEeHp0NmRqS3dBNFNIZlF0aWtfVG9rZW46SmlPMmJJanpQb3V6R294SVAwM2N4VkxUblFoXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

比如我要找到Codex Skills的全局路径，就需要先打开 /User/caicai/，接着按快捷键 `Command + Shift + .`（英文句号），隐藏文件就会以半透明形式显示，再次按相同快捷键即可隐藏。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZWJkOWMxZmIzNWNkMzI5YTNmNDZkNDAyNWQ5M2M1MGJfRm9CZEZpejdyTjZxamZIWHN2elkzeTRNUjZva29Hd2hfVG9rZW46T3ZKUmJJSTNHb29menF4OFJ6VmNNaDl0blBoXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

在 Windows 中，`~`则通常指向 `C:\Users\<你的用户名>`。对应路径的完整形式为：

```Plain
C:\Users<你的用户名>.codex\skills\
```

比如我的用户名是 CaiCai，对应的完整路径就是：

```Plain
C:\Users\CaiCai.codex\skills\
```

不同于Mac，在 Windows 中查看隐藏文件和文件夹是通过**文件资源管理器**快速显示：

1. 打开任意文件夹，点击顶部菜单栏的“查看”选项卡
    
2. 在“显示/隐藏”区域勾选“隐藏的项目”
    
3. 隐藏文件会以半透明图标显示，再次取消勾选即可隐藏
    

  

注：Codex CLI 通过 $skill-installer Skill 从官方仓库（https://github.com/openai/skills）安装 Skills的方法，也属于这种手动安装，而非从插件市场安装。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZWJjMTZjNjVjMjdiNjM1NTA5Nzg5MzcwYmZhM2FkYzdfbkc3RWswaWFLbk9PUnJvNVhac012MmpTMkpXM1hxQndfVG9rZW46Rnd0TGI5WTh2b0F1WDR4VUdHQ2M3WnM1bndmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

## 方法三：通过第三方工具安装（适合IDE、CLI）

现在越来越多AI编程工具支持Skills了，但它们每个的安装路径都千差万别。

如果你不想费劲记住这些安装路径，可以用 Vercel 官方出品的这个 add-skill 项目来解决这个问题。

add-skill 🔗：https://github.com/vercel-labs/add-skill

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=N2RjM2Y0YjExNDJkMzBiODM3NmI1YTM1MzZmYWU3NDBfaDUyVUJrYzRZUDlLc3hrNG5kenBETVNUdUpRRVVXVkFfVG9rZW46UEZ6MGJVZk94b2FJaGF4d25GS2NUdDVZbjBkXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

它支持指定Skill安装的AI编程工具，几乎支持目前所有常见的AI编程工具。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDdjN2MxNDY2OGU3YzRjODcyMmY1NjJiNmY0OTAxYzRfVnJUZTdTUFc1UHlMY3g1RFV0anlwbFVUb1hMcEVDY0VfVG9rZW46QllueGJFak1Tb3RMbDh4allUVGN4MG1Bbm5mXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

还支持指定Skills生效范围（全局/项目），支持指定具体仓库（或仓库内的具体Skill）进行安装；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NjNmNzc4OTRlYWRlMDQ2NjkwZDVhZTJjNWUwZjhiZjhfVGs1MWlURkFweUpJeDdQN0ZkdkphT3Q5Qmdad0Y5WmJfVG9rZW46WTJNM2JxdG1Qb09UOGl4M0lCZ2NkblJ3bmdjXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

如果你平时也CC-Swtich进行模型管理，那么也可以试试用它进行Skills快捷管理（不过目前v3.9.1版本只支持Claude Code和Codex的Skills管理）。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NDgyYjMwMDBhNjhkMDliZjk4ZDExZDkxMGYwN2U1NjJfZkFKb3ZWVjVuOFV2TTVpenJzOTNRUFZWbmtjQmNUR1JfVG9rZW46U2NyWmJMMkRVb0JyYm94R0szMmM4dGg3bm1oXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

点击右上角这个🔧icon即可进行Skills管理界面。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NThhNzUzN2Y4OWVlNjU1ZmIxMzUyMzVmMjEwNTJiMThfQlVUYmhnQWdjNGVyd3F1TVViRjJIS1NpRmVXZGJ0OEhfVG9rZW46WVZMVGI1TGxYb3VnMGp4Q1M3M2NkUFdnblNoXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=N2E2YzY5YzY5MDBmNGY5OGZhZmRiOTJlMmFlYzA3NzVfVnVtazl4WDBCNllwMndsMDQxamRSMkRZS0NadnJ5dHhfVG9rZW46RGoycmJuV0Mxb2Nqalp4SXJkemN2Vk1YbktmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

## 方法四：让 AI 帮忙安装（适合大部分工具）

当然，如果你不想自己动手安装Skills，也可以把活丢给AI（不一定每次都会成功，目前测试下来Claude Code最稳定）。

给AI的提示词可以是这样的：

```Plain
帮我安装 {skill-name}，skill的项目地址是：{skill项目地址}
```

我个人建议初学者都用方法二跑一遍，这样会对于Skills有更深的了解。

  

  

## 方法五：上传Skill文件包安装（适合Claude、扣子编程）

这种方法目前只适合Claude和扣子编程，只需要将打包好的Skill文件上传到对应工具即可。

- **Claude**
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=NDY0YmNjMmU3NGYzZjY4YmVjMzk2NGEzMjkxZTNhZGFfRXVpU3NCWEtzbmV1YmdkN051Y3p6UEc4b2Q4MDVyRWRfVG9rZW46RWRZbGI1ZXFHb1pwNXZ4Z3FROWM4MjRobnVlXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

- **扣子编程**
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTE2NDg0ZWQ2ZmJiNTUzZjM4OTg1ZDY0NGI4MjI0YzNfVG9zYTlPT1BHSENzaTdySnkyQnczWTYzRUYzb05POGlfVG9rZW46SDFLeWJuMEp5b0RVSm94THlYemNmVVJIbnNoXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

# Skills的两种使用方法

如果你是通过IDE工具、或网页端工具（如Coze）安装Skills，安装成功后无需退出工具重启即可生效。

但如果你是通过CLI工具安装Skills，在安装成功后，一般需要重启CLI才能使用之前安装的Skills。

注：Claude Code除外，因为它在v2.10版本中上线了 Skills 自动热重载功能。简单来说，就是安装Skills后无需重启Claude Code就能生效

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=N2NhNTlhN2Y1YTFiMjIyNDBmOWM1NmJmMjA5MzgyNWFfTzVNM3Joek5CRmpqNTVkNDJmM3YyYXJTbEhGdXpDV0VfVG9rZW46VVRqemIxZFRPb1lwWkd4RXp6NWNFV0xBbjFkXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

## 方法一：Agent自动加载

我们在[Agent Skills概念拆解](https://my.feishu.cn/docx/WzWIdW3z0oks8XxaqmlcE8Gon7u?from=from_copylink)中介绍过，Skills是被设计为按需自动加载的。

以 frontend-design skills 为例，当我们的提示词涉及前端 UI，AI 就会进行意图判断并自动加载相关的 Skills。

这是理想的情况。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YjZhMDBkYTVkODhlNTNhNTRiY2M1YWQ3MWEwNmM4OWRfR3EyU25mODJIcHJienVxRThEOFdTQzltZDZmcU84MGFfVG9rZW46SGFNQWJmcEVib3QwTHR4RG5VZmNXTU5LbldmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

为什么说这是理想的情况？

因为如果你之前频繁使用过 Skills，那么你会遇到这样的情况：**Agent 有时候压根不管你配置的 Skills，直接按照自己的理解开始干活。**

这不是个例，很多开发者都遇到过。我之前分享过OpenSkills，当时就有不少精神股东留言说这些工具没有自主调用 Skills。

暂时无法在飞书文档外展示此内容

怎么解决这种问题呢？

两种方案。

一种是通过 Hook 强制调用 Skills。另一种就是用户自己手动加载Skills。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDkzZDM0Zjk3MTYyOGFjNjNkNDllYWQ4YTdmMzJmYjlfa1BzS3IwcmY1Q0wxV2xKUmMyTlVmemJRaHdndmtsNVBfVG9rZW46TmNZa2JjWEZFb0lNeFh4VWVpWWNpbjhQbklmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

Skills+Hooks的组合方案不是我想出来的，最早由国外大神 Scott Spence 提出。他之前也碰到同样的问题，于是搭了个测试框架，跑了 200 多次测试，找出了两套方案，把激活成功率从最初的 20% 提升到了 80-84%。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MTNjYzc3MWU0OTE4ZGRkZjE2MjVjOTE1Yjg4ODQ4OGRfdE9LUjV5czk1NHFiS3psQXVtblBqc1hySXpWZFRQTXpfVG9rZW46U3R3SWJuZ1Bib2ZKeTV4MDBmZGNHZnA5bnZnXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

这是他之前分享过的博客>>>

https://scottspence.com/posts/how-to-make-claude-code-skills-activate-reliably

整个流程具体是这样的：

1. 在你的项目中创建 `.claude/hooks/skill-forced-eval-hook.sh` （或者在 `~/.claude/hooks/` 下全局创建
    
2. 将这段强制执行脚本复制到`skill-forced-eval-hook.sh`里
    

```Plain
Step 1 - EVALUATE: For each skill, state YES/NO with reason
Step 2 - ACTIVATE: Use Skill() tool NOW
Step 3 - IMPLEMENT: Only after activation

CRITICAL: The evaluation is WORTHLESS unless you ACTIVATE the skills.
```

3. 让这段脚本可执行： `chmod +x skill-forced-eval-hook.sh`
    
4. 添加到 `.claude/settings.json`
    

```JSON
{
  "hooks": {
    "UserPromptSubmit": [
      {
        "hooks": [
            {
              "type": "command",
              "command": ".claude/hooks/skill-forced-eval-hook.sh"
            }
          ]
        }
     ]
  }
}
```

  

## 方法二：用户手动加载

我们可以在提示词中注明要调用 skill 的名称，这种方法在大部分工具都通用，比如：

```Plain
用frontend-design skills,生成一个简洁的博客网站,单HTML文件
```

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OTRlOWE3ZjJiOWY0MGI4OTBiM2UxODY5NjUxNWNiM2NfTWhxcGhxMzFJa1F0dTlxY0tWYjFrdkU1SWcyb1NJcDlfVG9rZW46S1FGY2JDZHV3bzRYMG54QlFrYmNYT3V3bkhiXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

在Claude Code和Cursor中，我们还可以通过 / {skill-name} 的快捷命令指定Skills；

- Claude Code
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MjYxNjI1Nzc5ODI2YTEwOWI3NWEwNjY2MDU0YmM1MzlfTTJrREk2dnltZTNjdUhHa0VIaTNta1c0dzRweXVHOVJfVG9rZW46VmhFVGJlbk9Tb3U2SEd4UzFMQ2M0a2M1bnJjXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=OTFiY2Y2NTg1NTBiYWQ2NDhjMDI2MDFhODgyY2E2MWRfWk8zMVhyeDJxelBoTzZoUXF4NVRXaDZRRXczdllHekxfVG9rZW46Vk9CUGJvOVpzb045OHd4Vlo2TGN4VVNibnlkXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

- Cursor
    

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2FkOTE1ZTExMWU2YzNkN2NhMzdhOTBhNTQ2ZGQ3ZGFfN2FUWWNLanhrdkl2M214ZDNodEh2MUxLT0lSNHBIU0NfVG9rZW46WGFoemJzd1Zmb3RYTEd4dTFBWGNrekdBblFmXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

在Codex中，则可以通过 $ {skill-name} 的快捷命令指定Skills；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=N2E4OGNjOGEyOTQ4MzgyOGRkODMxZjQ2OWY5NjZiYzdfTklDOHVQU0wySjZ5OUtKVU5MZXZRZm9mZFFDMnFneW1fVG9rZW46SjZ3R2JXb3d5bzhzbVV4eWJvc2NzSFN6bm5jXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

在扣子中，则是通过 @ 快速选中自己要调用的Skills。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=ODg1OTFmNGVhM2UwY2ViZDhiNmMzNDM3NWZmMGZkMDZfb2VlMWpMMUVmVXhMWUxpc2RNcUI4OTJsQ2l0TTJXNk1fVG9rZW46SW11VWJ5azJvb3hjZ1R4Vkx1WmNUZ0U4bndiXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

其它工具中的快捷指定方式就不一一罗列了。

  

  

# Skills的两种卸载方法

虽然Skills的安装方法很多，但卸载方法就比较简单了。

## 方法一：通过插件市场卸载（适合Claude Code）

在Claude Code中输入 /plugin 快捷指令，在打开的管理窗口中选择「Installed」，我们就能看到自己安装的所有 Plugins；

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MGY3YTVjM2JjMzZiMTY5NzQzZjZiMGQwYzNmNmEwZDlfUHlBM3JOd2x2SlNWMldmTW5LcEJsSUU0OW43a0FHajBfVG9rZW46Szg0NWJFUFk1bzA0YTB4UEt5dGNyejJtbndlXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

选中你要卸载的Skills，然后Enter进入详情操作窗口，你可以在这里禁用、更新或卸载它。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=MzJiZjgxZGQxYWI1ZDI1OWIzNWU4MGNlYTM2NWU3ZjhfczFwOElrcUh4UGRtRTdoemFDMXZwQ1RxbVd0QzZUSnVfVG9rZW46SWN4SmI5VUNyb0VVdHJ4N2dKV2NLa0JNbm1lXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

注意：大家平常可能会遇到一种特殊情况：就是你已经安装过某个Skills，在「Markerplaces」中查看显示已安装，但在「Installed」不显示，也无法使用。

这时候可以卸载掉对应的Markerplaces，同时去到这个路径>>>/Users/caicai/.claude/plugins/installed_plugins.json，删除这个installed_plugins.json文件（具体文件如下图所示）

文件删除后，相当于重置已安装的Plugins，后面重新安装Skills时，会重新生成installed_plugins.json文件。

![](https://my.feishu.cn/space/api/box/stream/download/asynccode/?code=YmJhMjBhYTJjNjEzOGY2MTQwNjgwMDQwMzM0MTY0Mjhfc2dzMk5veXVrZEltajRvaUVYbktRcWFPZXV0ZUVzN1JfVG9rZW46UVV0TmJhOHJYb2o1bnl4THR2UGNZSExOblRlXzE3Njk2NjgyNjI6MTc2OTY3MTg2Ml9WNA)

  

## 方法二：手动删除 Skills（通用）

这种就是字面上的意思，找到你前面安装好的Skills，直接删除即可。

删除后可以用 /skills list 或让 AI 帮你列出当前可用的 Skills 来判断是否删除干净。