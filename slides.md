---
download: true

# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## tools-for-developer
  高效程序员的利器们

# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
---

# Tools For Developer - 高效程序员的利器们

> 工欲善其事，必先利其器！

As hackers, we spend a lot of time on our computers. So it makes sense to make that experience as fluid and frictionless as possible.


---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Table of contents

<Toc minDepth="2" maxDepth="5"></Toc>

---
transition: slide-up
level: 2
---

# Shell

- `|` operator lets you “chain” programs such that the output of one is the input of another:
``` bash
cat package.json | grep lint
ls | tail -n 3
ls | head -n 3
ls -rSl | tail -n 3 | pbcopy
pbpaste | head -n1
ll | grep nest
```
- `>` overwirte output to a file:

```bash
  curl wttr.in > test.txt
  curl cip.cc > test.txt
  cat test.txt
```

- `>>` append output to a file:

```bash
  curl wttr.in >> test.txt
  curl cip.cc >> test.txt
  cat test.txt
```

---
transition: slide-up
---

- Always try to use RegExp.

```bash
  ls -l *.json
```

- alias
```bash
➜  alias mnpm
mnpm='npm --registry=http://r.npm.sankuai.com --cache=/Users/chaofeis/.cache/mnpm --disturl=http://npm.sankuai.com/mirrors/node --userconfig=/Users/chaofeis/.mnpmrc'
➜  alias gp
gp='git push'
➜  alias gma
gma='git add . && gm'
```

<img
  v-click
  class="h-60"
  src="/images/alias.gif"
/>

---
transition: slide-up
preload: false
layout: two-cols
---

- man
  <img
    class="h-50"
    src="/images/RTFM.jpeg"
  />

  <div
    v-click
    v-motion
    :initial="{ x: 180 }"
    :enter="{ x: 0 }"
  >
    <img
      class="h-50"
      v-click
      src="/images/tldr.gif"
    />
      TL;DR
  </div>
::right::
<div>


  <ul>
    <li v-click>
      <a href="https://github.com/tldr-pages/tldr" target="_blank">
        tldr
      </a>
    </li>
  </ul>

  <img
    class="h-80"
    v-click
    :initial="{ x: 280 }"
    :enter="{ x: 0 }"
    src="/images/tldr1.svg"
  />
</div>

---
transition: slide-up
---
- oh-my-zsh
  - change directory:

| Command    | Result |
| -------- | ------- |
| folder/| 	write the folder name with / at the end |
| ..	| go back one folder (parent dir) |
| ...	| go back two folders (parent from parent dir) |
| ......	| go back five folders |
| /	| go to root |
| ~	| go to home |

  - `zsh_stats` LRU
---
transition: slide-up
---

  - `TAB` for completion
    ```bash
    ls -
    echo $
    ```
  - alias:
    ```bash
    alias | grep git
    ```
  - plugins\themes

- More about changing directory
  - [j](https://github.com/wting/autojump)
  - z


---
transition: slide-up
layout: fact
---
<img
    class="w-860"
    src="https://ik.imagekit.io/light/images/blog/tmux-tips.png"
  />

---
transition: slide-up
layout: image-left
image: https://ik.imagekit.io/light/images/blog/tmux-tips.png
---


- [tmux](https://github.com/tmux/tmux/wiki)
  > tmux is a terminal multiplexer. It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal.
  - 分屏复用：`|` `-` `Space` `T`
  - 切换: `q`
  - `Ctrl-B d` detach from Tmux
  - 窗口管理：
    - `Ctrl-b c` 创建新window
    - `Ctrl-b w` 在 window 间切换
    - `Ctrl-b f` 搜索窗口
  - `Ctrl-b d` or `Ctrl-b Ctrl-z` dettach
  - tmux attach -t SESSION_ID
  - [awesome-tmux](https://github.com/rothgar/awesome-tmux)

---
transition: fade-out
preload: false
---

- `git log` + `git show COMMIT` -> [tig](https://github.com/jonas/tig)
- [serve](https://github.com/vercel/serve)
  - 变迁：python -m SimpleHTTPServer 9000 -> python3 -m http.server 3000 -> serve
  - `npm install -g serve`


<div>
  <div
    v-click
    v-motion
    :initial="{ x: 180 }"
    :enter="{ x: 0 }"
  >
    <img
      class="h-70"
      src="https://i.gifer.com/2I73.gif"
    />
      #LBNL
  </div>

  <ul>
    <li v-click>
      Ctrl + r
    </li>
  </ul>
</div>


---
transition: slide-up
level: 2
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Editor
<Toc minDepth="3" maxDepth="5"></Toc>

---
transition: slide-up
level: 3
---
## Actions

  - [Emmet](https://emmet.io/) (原Zen Coding)

  ```html {1|3-9|all}
  (div#emmet>p.bar*4>ul.nameblock>li*5.list)+footer>a[href=meituan.com]{Click me}

  <style>
    #emmet{
      m4-6
      w100p
      h100r
    }
  </style>
  ```

  - Multi Cursor
    - <kbd>Cmd + d</kbd> ： 词的多选
    - <kbd>Cmd + Click</kbd> or <kbd>鼠标中键</kbd> ：创建多个

    <!-- ![MultiCursor](/images/multi_coursor.gif) -->

    <img
      v-click
      class=""
      src="/images/multi_coursor.gif"
    />

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---
transition: slide-up
level: 3
---
- Expand Region: <kbd>Ctrl + w</kbd>
- Folding/Unfolding Block: <kbd>⌥ + ⌘ + [</kbd>/<kbd>⌥ + ⌘ + ]</kbd>
- <kbd>Ctrl + c</kbd> Parenthesis Matches / Matching Pair / Closiong Tag
- Go To Definition/References

---
transition: slide-up
level: 3
---

### Moving & Selecting
- 行内移动:
  - 按词: <kbd>Ctrl-f/b</kbd> <kbd>Meta-f/b</kbd>
  - 首尾: <kbd>Ctrl-a</kbd> <kbd>Ctrl-e</kbd>
    - 配合 <kbd>shift</kbd>
- 按行: <kbd>Ctrl-n</kbd> <kbd>Ctrl-p</kbd>
- 翻页: <kbd>Ctrl-v</kbd> <kbd>Meta-v</kbd>
- 跳到指定行: <kbd>Meta-g g</kbd>
- 文件首尾: <kbd>Command-↑</kbd> <kbd>Command-↓</kbd>
- 删除: <kbd>Ctrl-d</kbd> <kbd>Meta-d</kbd>
  - 同命令行
- 鼠标中键：多行光标和块级选择


> Vim\Emacs Mode

---
transition: fade-out
level: 3
---

## Font
-最低要求：monospace
  <img
      class="w-100"
      src="/images/font.png"
    />
- 大家的选择：
  - [ProgrammingFonts](https://github.com/ProgrammingFonts/ProgrammingFonts)
  - [best-programming-fonts](https://kinsta.com/blog/best-programming-fonts/)
- 我的选择：
<div v-click>
  <a
    target="_blank"
    href="https://github.com/tonsky/FiraCode">
    FiraCode
  </a>

  <img
    class="w-100 absolute top--3 right-10"
    src="https://github.com/tonsky/FiraCode/raw/master/extras/ligatures.png"
  />
</div>

---
level: 2
transition: slide-up
---

# Keys
- Chrome恢复关闭的标签页: <kbd>Command + Shift + T</kbd>
- 系统：
  - <kbd>Cmd + Tab</kbd>
  - <kbd>Cmd + `</kbd>
  - <kbd>Ctrl + Up</kbd> <kbd>Ctrl + Down</kbd>
- 移除粘贴板文字格式：<kbd>Command + Shift + v</kbd>

---
transition: fade-out
level: 3
---
- 神奇的 <kbd>Meta/option/Alt</kbd> 键
  - 在编辑器和命令行中的快捷跳转
- 更少的离开键盘: Vim/Emacs 习惯
- Switch <kbd>CapsLock</kbd> and <kbd>Ctrl</kbd>
<img
  v-click
  class="w-200"
  src="/images/hhkb.png"
/>

---
transition: fade-out
level: 2
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Applications & WebSites

<Toc minDepth="3" maxDepth="5"></Toc>

---
transition: slide-up
level: 3
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

## Extensions

- OneTab（配合 shortcuts）
- GoogleTranslate/Youdao
- The great suspender -> 原生支持
- 新浪微博图床
- OctoTree -> 原生支持
- 浏览器 Tab 分组
- [vimium](https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb/related?hl=en-US)
  - hjkl
  - gg G
  - HL
  - JK

---
transition: slide-up
level: 3
---

- 监听和修改请求：
  - ReRes（已下架）
  - [AppMock](https://appmock.sankuai.com/appmock/list) for 公司内客户端
  - Charles
<div
  v-click
  v-motion
  class="mr-15"
  >
  <ul>
    <li>
      <a href="https://github.com/avwo/whistle">
        whistle
      </a>
      for Web
    </li>
  </ul>
  <img
    class="w-230"
    src="/images/whistle.png"
  />
</div>

<!-- 比如 package-lock 文件页面 -->

---
transition: slide-up
level: 3
---

## Learning
- https://www.codecademy.com/
- https://www.coursera.org/courses?query=free
- https://www.freecodecamp.org/
- 网易云课堂 https://study.163.com/
- 慕课/极客时间
- 高校公开课： https://github.com/jackwener/CS-Awesome-Courses/blob/master/README.md
  - 推荐 MIT - The Missing Semester of Your CS Education https://missing.csail.mit.edu/

---
transition: slide-up
level: 4
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---
### Nodejs & JavaScript

- https://zh.javascript.info/
- https://nodeschool.io/
- https://pluralsight.com/paths/javascript-core-language
- Dr. Axel Rauschmayer https://2ality.com/
- Dan Abramov https://overreacted.io/
- Eric Elliott https://medium.com/@_ericelliott
- Wes Bos https://wesbos.com

---
transition: slide-up
level: 4
---
### CSS
- 大漠: https://www.w3cplus.com/
- 一丝: https://github.com/yisibl/share
- 张鑫旭: https://www.zhangxinxu.com/wordpress/category/css/
- https://codepen.io/trending
- https://css-tricks.com/
- CSS 游戏 by codepip：
  - https://cssgridgarden.com/
  - https://codepip.com/games/flexbox-froggy/
- Design: https://www.csszengarden.com/pages/alldesigns/

<img
  class="w-100 absolute top-15 right-10"
  src="/images/css.gif"
/>

---
transition: slide-up
level: 3
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

## Tools
- ssh-copy-id: connect to host2 without any password
- 绘流程/UML/泳道图等:
  - https://www.processon.com
  - https://excalidraw.com
  - https://app.diagrams.net
  - https://www.omnigroup.com/omnigraffle
    - 另外推荐 OmniGroup 其他软件：OmniFocus、OmniPlan等
- 脑图：
  - 百度：https://naotu.baidu.com/
  - [xMind](https://xmind.cn/)
  - [MindMaster](https://www.mindmaster.io/)

---
transition: slide-up
level: 3
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---
- 笔记：
  - The Programmer's Notebook: [Quiver](https://yliansoft.com/)
  - A note-taking tool for networked thought: [Roam](https://roamresearch.com/)
    - [我们需要什么样的双向链接，它适合你吗？](https://sspai.com/post/67996)
  - Your wiki, docs & projects. Together: [Notion](https://www.notion.so)

- 静态网站托管+FaaS：Github Pages/Netlify/Vercel/Heroku

- Bookmarklet:
  - inject scripts： add$, add_, addMoment, angularWatchCount
  - [my bookmarklets](https://github.com/chafel/bookmarklets)

---
transition: fade-out
level: 3
layout: two-cols
---

## Others
- 点对点文件传输：[MagicWormhole](https://magic-wormhole.readthedocs.io/en/latest/welcome.html)
- Hosts管理：[SwitchHosts](https://github.com/oldj/SwitchHosts)
- 量尺寸：[free ruler](https://www.macupdate.com/app/mac/7197/free-ruler)
- 工具集：[utools](https://u.tools/)
- 壁纸工具：[pap.er](https://paper.meiyuan.in/)
- 音乐：[listen1](https://listen1.github.io/listen1/)
- 粘贴工具：Paste
- 清理工具：腾讯柠檬/ccleaner
::right::
- 截图软件：snipaste
- 窗口管理工具：sizeup/Magnet
- gif录制工具：LICEcap
- 文件diff神器：Kaleidoscope
- markdown编辑器：typora
- 看板：Jira/Lean/OminiFocus/BaseCamp
- 电子书：http://jiumodiary.com
- 软件：http://xclient.info
- 番茄工作法 + [休息一下眺望远方](https://apps.apple.com/cn/app/%E4%BC%91%E6%81%AF%E4%B8%80%E4%B8%8B-%E7%BC%93%E8%A7%A3%E7%96%B2%E5%8A%B3%E6%8F%90%E9%86%92%E5%B7%A5%E5%85%B7/id1457158844?mt=12)


---
level: 2
transition: slide-up
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---
# More
- Blog：
  - CSDN\yuque\medium\juejin
  - github pages
  - wordpress
  - hugo/hexo/astro

- PPT：
  - keynote
  - slides.com
  - [reveal.js](https://github.com/hakimel/reveal.js/)
  - slidev

> #### Markdown & [MDX](https://mdxjs.com/docs/getting-started/)


---
level: 2
transition: slide-up
layout: two-cols
---
- 随便看看
  - [别人的利器生活](http://liqi.io)
  - [少数派](https://sspai.com/)
  - [程序员常用单词读音](https://github.com/shimohq/chinese-programmer-wrong-pronunciation)
  - [关于面试、文案和 Commit 启蒙](https://open.leancloud.cn/)

::right::
<div class="rainbow-text">
   谢谢大家的观看！🌹🌹🌹
</div>

<style>
@keyframes hue {
    from {
        filter: hue-rotate(0);
    }

    to {
        filter: hue-rotate(360deg);
    }
}

.rainbow-text {
    display: inline-block;
    position: relative;
    font-weight: 500;
    font-size: 100px;
    color: transparent;
    animation: hue 2s linear infinite;
    background-image: linear-gradient(to right bottom, rgb(255,0,0), rgb(255,128,0), rgb(255,255,0), rgb(0,255,0), rgb(0,255,128), rgb(0,255,255), rgb(0,128,255), rgb(0,0,255), rgb(128,0,255), rgb(255,0,255), rgb(255,0,128));
    -webkit-background-clip: text;
}
</style>
<!-- src: ./instruction.md
时长够了就忽略
https://send.firefox.com/
仓库和共建？

有知有行
小苹果

Dropzone

vssh-->