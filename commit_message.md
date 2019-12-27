# Commit Message

按照以下内容，统一 Commit Message。

Angular 的 commit message 规范是目前使用最广的规范。由于本仓库只包含说明文档，所以如果按 Angular 规范来做相对来说也是比较繁琐的，而且没这个必要。仿照 Angular 规范指定一个符合我们实际情况的 commit message 规范。

## 格式：

对于文档来说，主要是 markdown 文本文件和图片（.png 和 .jpg）文件这两种，我们以 md 文件为核心。

```
<type>(<file>): <msg>
```

**注意：":" 后有空格**

### type
type 只允许是以下几个关键词。

- add：增加一个文件或在文件增加内容，如果增加文本文件同时附带有图片文件，那么在 `<file>` 处只写上文本文件名，不添加图片名。除非是单独的添加一个图片。对以下其他操作同样处理。
    - 举例：

        ```
        add(README.md README-en.md): 添加 README 文件
        add(img/p1.png): 添加 p1.png
        ```

    - `add(README.md p1.png): 添加 README p1.png文件` 这种写法不被允许，因为一般添加一个 md 文件会附带很多图片文件来说明，为简化操作不记录添加的图片文件。

- mod：修改文本文件
    - 举例：

        ```
        mod(README.md): 修改 README.md
        mod(p1.png): 更换 p1.png，在p1.png 上增加标识
        ```

    - 对于图片来说，一般更换图片算作修改
- del：删除文件
    - 举例：

        ```
        del(README.md): 删除 README.md
        del(p1.png): 删除 p1.png
        ```

### file
记录操作的文件。以空格隔开，文件过多以 `...` 来做提示。
- 举例：

    ```
    add(README.md md1.md md2.md config.txt ...): 增加一系列文件
    ```

### msg
本次 commit 的相关说明。

### 要点
- 优先级是`文本文件` > `图片文件`，有文本文件改变先记录文本文件。之后是 `add` > `mod` > `del`，按此优先级记录操作。
- 文档的操作方式较为单一，就是增、删、改。如有其他操作，请添加至此文件。
- `<msg>` 部分尽量详细，句末**没有**句号。
- 尽量将 commit message 简化到一行。
- 所有文件命名尽量不要使用中文

