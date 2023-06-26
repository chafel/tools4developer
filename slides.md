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

<div class="flex justify-center h-20 mt-10">
<a class="h-20 mr-1" href="https://twitter.com/chaofeis" target="_blank" aria-label="Twitter" data-v-42e0901a="">
<svg preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24" width="1.2em" height="1.2em" data-v-42e0901a=""><path fill="currentColor" d="M22.162 5.656a8.384 8.384 0 0 1-2.402.658A4.196 4.196 0 0 0 21.6 4c-.82.488-1.719.83-2.656 1.015a4.182 4.182 0 0 0-7.126 3.814a11.874 11.874 0 0 1-8.62-4.37a4.168 4.168 0 0 0-.566 2.103c0 1.45.738 2.731 1.86 3.481a4.168 4.168 0 0 1-1.894-.523v.052a4.185 4.185 0 0 0 3.355 4.101a4.21 4.21 0 0 1-1.89.072A4.185 4.185 0 0 0 7.97 16.65a8.394 8.394 0 0 1-6.191 1.732a11.83 11.83 0 0 0 6.41 1.88c7.693 0 11.9-6.373 11.9-11.9c0-.18-.005-.362-.013-.54a8.496 8.496 0 0 0 2.087-2.165z"></path></svg></a>
<a class="h-20" href="https://github.com/chafel/tools4developer" target="_blank" aria-label="View GitHub Repo" data-v-42e0901a=""><svg preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24" width="1.2em" height="1.2em" data-v-42e0901a=""><path fill="currentColor" d="M12 2C6.475 2 2 6.475 2 12a9.994 9.994 0 0 0 6.838 9.488c.5.087.687-.213.687-.476c0-.237-.013-1.024-.013-1.862c-2.512.463-3.162-.612-3.362-1.175c-.113-.288-.6-1.175-1.025-1.413c-.35-.187-.85-.65-.013-.662c.788-.013 1.35.725 1.538 1.025c.9 1.512 2.338 1.087 2.912.825c.088-.65.35-1.087.638-1.337c-2.225-.25-4.55-1.113-4.55-4.938c0-1.088.387-1.987 1.025-2.688c-.1-.25-.45-1.275.1-2.65c0 0 .837-.262 2.75 1.026a9.28 9.28 0 0 1 2.5-.338c.85 0 1.7.112 2.5.337c1.912-1.3 2.75-1.024 2.75-1.024c.55 1.375.2 2.4.1 2.65c.637.7 1.025 1.587 1.025 2.687c0 3.838-2.337 4.688-4.562 4.938c.362.312.675.912.675 1.85c0 1.337-.013 2.412-.013 2.75c0 .262.188.574.688.474A10.016 10.016 0 0 0 22 12c0-5.525-4.475-10-10-10z"></path></svg></a>
</div>


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

- `xargs` xargs translates arguments to commands. This effectively means you can run one command per argument, or forward all arguments to one command .
``` bash
cd ~/work/base
ls | code
ls | xargs code -
ls | xargs code
ls | xargs -L1 code
```

---
transition: slide-up
---

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

  - `zsh_stats` Frequency statistic
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
  - [z](https://github.com/agkozak/zsh-z)


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
- [Highlight cursor column](https://marketplace.visualstudio.com/items?itemName=freakone.cursoruler)
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

- OneTab（配合快捷键如`Cmd + e`快捷关闭后保存）
- GoogleTranslate/Youdao
- The great suspender -> 原生支持
- 新浪微博图床
- OctoTree -> 原生支持
- 浏览器 Tab 分组
- [vimium](https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb/related?hl=en-US)
  - jk: 快捷滚动
  - gg G: 页面收尾
  - HL: 前进后退
  - JK: 标签页切换

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
- [CodeCademy](https://www.codecademy.com/)
- [Coursera](https://www.coursera.org/courses?query=free)
- [FreeCodeCamp](https://www.freecodecamp.org/)
- [网易云课堂](https://study.163.com/)
- 慕课/极客时间
- [高校公开课](https://github.com/jackwener/CS-Awesome-Courses/blob/master/README.md)
  - 推荐 MIT 的 [The Missing Semester of Your CS Education](https://missing.csail.mit.edu/)
<img
  class="h-40 absolute top-20 right-40"
  src="/images/learning.webp"
/>
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
- [大漠](https://www.w3cplus.com/)
- [一丝](https://github.com/yisibl/share)
- [张鑫旭](https://www.zhangxinxu.com/wordpress/category/css/)
- https://codepen.io/trending
- https://css-tricks.com/
- CSS 游戏 by codepip：
  - [grid 农场](https://cssgridgarden.com/)
  - [flexbox 青蛙](https://codepip.com/games/flexbox-froggy/)
- Design: [csszengarden](https://www.csszengarden.com/pages/alldesigns/)/[dribble](https://dribbble.com/tags/configuration%20panel)/[站酷](https://www.zcool.com.cn/)

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
- [Warp](https://app.warp.dev/referral/PX6PXZ): 带 AI 的命令行终端
- ssh-copy-id: connect to hosts without any password
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
level: 3
layout: two-cols
---

- [Alfred](https://www.alfredapp.com/)
  - Features:
    - Quick Search
    - Clipboard History
  - Workflows:
    - 快捷操作：Finder ↔️ Iterm, div
    - API文档快查，如 mdn, httpcode
    - 快捷展示：Colors, ip
    - More:
      - [awesome-alfred-workflows](https://github.com/alfred-workflows/awesome-alfred-workflows)
      - [alfred-workflows-that-i-cant-live-without](https://pawelgrzybek.com/alfred-workflows-that-i-cant-live-without)

::right::

<img
  class="w-60"
  src="/images/alfred.jpeg"
/>
<img
  v-click
  class="w-100 mt--30"
  src="/images/div.gif"
/>
<img
  v-click
  class="w-100 mt--40"
  src="/images/mdn.gif"
/>
<img
  v-click
  class="w-40 mt--40 ml--70"
  src="/images/cantwait.gif"
/>

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

<Transform :scale="0.8">
<hr class="mt-5 mb-5"/>
Follow me on Twitter:
<Tweet id="1667062534954942466" />
</Transform>

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
