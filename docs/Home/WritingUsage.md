---
comments: true
---
# 写作常用语法
## 告诫/警示

### 基本语法
MKdocs支持扩展的Markdown语法，可以插入警示块，具体语法如下：
```markdown title="警示块语法"
!!! note "警示块语法"
    + 开始以`!!!`标识符，然后加一个空格，空格后面添加警示类型的标识，然后空格添加一个字符串作为标题；
    + 在下一行空四个空格，然后写警示内容；
    + 警示删除标题时，只需要将标题字符串置为空串 `""` 即可.
```

!!! note "警示块语法"
    + 开始以`!!!`标识符，然后加一个空格，空格后面添加警示类型的标识，然后空格添加一个字符串作为标题；
    + 在下一行空四个空格，然后写警示内容；
    + 警示删除标题时，只需要将标题字符串置为空串 `""` 即可.

### 可折叠块
警示块还支持可折叠功能，具体语法如下：
```markdown title="默认折叠的可折叠块"
??? note "默认折叠的可折叠块"
    + 将警示标识符 `!!!` 换成 `???` 时，警示块可以折叠起来，并且默认是折叠的，需要手动点击展开;
    + 当在警示标识符 `???` 后面添加标识符 `+` 后，折叠块变为默认展开形式，点击后折叠.
```

??? note "默认折叠的可折叠块"
    + 将警示标识符 `!!!` 换成 `???` 时，警示块可以折叠起来，并且默认是折叠的，需要手动点击展开;
    + 当在警示标识符 `???` 后面添加标识符 `+` 后，折叠块变为默认展开形式，点击后折叠.

``` markdown title="默认展开的可折叠块"
???+ note "默认展开的可折叠块"
    + 将警示标识符 `!!!` 换成 `???` 时，警示块可以折叠起来，并且默认是折叠的，需要手动点击展开;
    + 当在警示标识符 `???` 后面添加标识符 `+` 后，折叠块变为默认展开形式，点击后折叠.
```

???+ note "默认展开的可折叠块"

    + 将警示标识符 `!!!` 换成 `???` 时，警示块可以折叠起来，并且默认是折叠的，需要手动点击展开;
    + 当在警示标识符 `???` 后面添加标识符 `+` 后，折叠块变为默认展开形式，点击后折叠.

### 内联块
告诫也可以渲染为内联块（例如，用于侧边栏），使用修饰符将它们放在左侧或者右侧：
=== ":octicons-arrow-right-16: inline end"

    !!! info inline end "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
        euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
        purus auctor massa, nec semper lorem quam in massa.

    ``` markdown
    !!! info inline end "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Nulla et euismod nulla.
        Curabitur feugiat, tortor non consequat
        finibus, justo purus auctor massa, nec
        semper lorem quam in massa.
    ```

=== ":octicons-arrow-left-16: inline"

    !!! info inline "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
        euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
        purus auctor massa, nec semper lorem quam in massa.

    ``` markdown
    !!! info inline "Lorem ipsum"

        Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Nulla et euismod nulla.
        Curabitur feugiat, tortor non consequat
        finibus, justo purus auctor massa, nec
        semper lorem quam in massa.
    ```
### 警示类型
支持的警示类型总计有以下几种，标题即为其标识符：

!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! abstract

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! info

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! tip

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! success

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! question

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! warning

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! failure

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! danger

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! bug

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! example

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

!!! quote

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

## 按钮
按钮作用是将一个链接显示为按钮的样式，具体语法同 Markdown 的链接语法一样，但需要在链接后面添加一个 CSS 修饰器：
```markdown title="Button"
[课程模板](./Template.md){ .md-button }
```
[课程模板](./Template.md){ .md-button }

如果要显示填充的主按钮，请使用 `.md-button--primary` 修饰器：
```markdown title="Primary Button"
[课程模板](./Template.md){ .md-button .md-button--primary }
```
[课程模板](./Template.md){ .md-button .md-button--primary }

如果需要添加 icon 直接在链接文字部分添加即可：
```markdown title="Button with Icon"
[课程模板 :fontawesome-solid-paper-plane:](./Template.md){ .md-button }
```
[课程模板 :fontawesome-solid-paper-plane:](./Template.md){ .md-button }