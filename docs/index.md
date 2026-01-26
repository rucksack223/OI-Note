# Getting Started

## 欢迎来到 OI-Note！

**OI-Note** 致力于成为一个 OI 的笔记网站，让同学们复习 OI 时更加方便。

**OI-Note** 是相较于 [OI Wiki](https://oi-wiki.org) 更加亲近的站点，它不高深，甚至有时不严谨，但它一定能让你理解透彻知识。我们欢迎你来贡献页面，让 **OI-Note** 更加完善。

实际上，你可以将 **OI-Note** 看作 OI Wiki 的补充页面。

## 如何贡献

请确保在提交贡献前，修改的页面能正常在自行部署的 **OI-Note** 中正常工作。

### 方法一

提建议，即通过 Issue。提交 Issue 时请保证你提出的问题还没有人提出过。

### 方法二

提交 commit，这适用于你只想要修改单个页面的情况。

在 Github 仓库中，打开你想要编辑的文件，点击笔图标（Edit this file），修改文件。修改后，点击绿色的 Commit changes... 按钮，在弹出的界面中编辑 Extended description，需详细说明修改的内容。最后点击绿色的 Commit changes 按钮，提交 commit。

或者提交 Pull request，这适用于添加新页面和大范围修改的情况。

首先，fork 仓库，在 fork 后的仓库中提交你修改的内容，然后创建 Pull request，等待 review。

review 过后，你的提交将被合并到仓库中。

## 支持的语法

本站点支持基本 Markdown 的所有语法、$\LaTeX$（使用 $\KaTeX$ 渲染）的大部分语法、提示框和一些 Markdown 拓展语法。下面是一些语法的示例。

!!! info "信息"

    由于 Mkdocs 限制，任何不相同的部分之间必须存在空行，例如列表中每一项和每一项中的内容、提示框的标题和提示框中的内容之间都必须存在空行。

- Latex

    $$
    x_{1,2} = \frac{-b \pm \sqrt{\Delta}}{2a}
    $$
    源代码：
    ```
    $$
    x_{1,2} = \frac{-b \pm \sqrt{\Delta}}{2a}
    $$
    ```

- 提示框

    !!! note "提示框示例"

        这是普通的 note 提示框。

        !!! note "内嵌提示框"

            可以发现，可以嵌套提示框。
    
    !!! note ""

        提示框可以没有标题。
    
    ??? note "点击试试"

        提示框可以折叠。
    
    ???+ note "点击试试"

        可折叠提示框也可以默认打开。
    
    源代码：
    ```
    !!! note "提示框示例"

        这是普通的 note 提示框。

        !!! note "内嵌提示框"

            可以发现，可以嵌套提示框。
    
    !!! note ""

        提示框可以没有标题。
    
    ??? note "点击试试"

        提示框可以折叠。
    
    ???+ note "点击试试"

        可折叠提示框也可以默认打开。
    ```

    !!! warning "警告"

        提示框内的内容一定要在同一缩进内，否则可能会排版错误。

    除此之外，替换 `!!!`，`???` 或 `???+` 后的文本可以替换样式。支持的文本：
    
    - note
    - abstract
    - info
    - tip
    - success
    - question
    - warning
    - failure
    - danger
    - bug
    - example
    - quote

- 代码块

    目前支持显示标题、行号和高亮行。

    在代码语言一行后加入 `title="<你想要的标题>"` 可以显示标题。

    ```` cpp title="标题示例"
    ``` cpp title="标题示例"
    int cnt = 0;
    for(int i = 1; i <= n; i++)
        cnt++;
    ```
    ````

    ``` cpp title="标题示例"
    int cnt = 0;
    for(int i = 1; i <= n; i++)
        cnt++;
    ```

    !!! info "信息"

        一般不使用 title，而是使用提示框和普通代码框的组合，本节使用仅是为了演示。

    在代码语言一行后加入 `linenums="1"` 可以显示行号，从 1 开始。

    ```` cpp title="行号示例"
    ``` cpp linenums="1"
    int cnt = 0;
    for(int i = 1; i <= n; i++)
        cnt++;
    ```
    ````

    ``` cpp linenums="1"
    int cnt = 0;
    for(int i = 1; i <= n; i++)
        cnt++;
    ```

    在代码语言一行后加入 `hl_lines="<x>"` 可以显示高亮行，字符串 x 中为几个行号或几个用 `-` 隔开的范围，范围间用 **空格** 隔开。

    ```` cpp title="高亮行示例"
    ``` cpp hl_lines="1 4-5"
    int cnt = 0;
    for(int i = 1; i <= n; i++)
        cnt++;
    std::cout << cnt;
    cnt++;
    ```
    ````

    ``` cpp hl_lines="1 4-5"
    int cnt = 0;
    for(int i = 1; i <= n; i++)
        cnt++;
    std::cout << cnt;
    cnt++;
    ```