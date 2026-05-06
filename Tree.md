tree (Unix command)

---

# 🧩 ① 基本调用结构

```text id="base"
tree [options] [directory ...]
```

👉 意思：

* options = 参数
* directory = 你要看的目录

---

# 🧩 ② 单字母参数（核心）

这些是 `[-acdfghilnpqrstuvxACDFJQNSUX]` 里的每个：

---

## ✔ `-a`

显示所有文件（包括隐藏文件）

---

## ✔ `-c`

按文件最近变化时间排序（ctime）

---

## ✔ `-d`

只显示目录

---

## ✔ `-f`

显示完整路径（不是树名）

---

## ✔ `-g`

显示文件所属组（group）

---

## ✔ `-h`

显示人类可读大小（KB/MB）

---

## ✔ `-i`

不画树形线（纯缩进列表）

---

## ✔ `-l`

不跟随符号链接（避免死循环）

---

## ✔ `-n`

禁用颜色输出

---

## ✔ `-p`

显示权限（chmod 那种）

---

## ✔ `-q`

用 ? 替代不可打印字符

---

## ✔ `-r`

反向排序

---

## ✔ `-s`

显示文件大小（bytes）

---

## ✔ `-t`

按修改时间排序

---

## ✔ `-u`

显示 owner（用户）

---

## ✔ `-v`

自然排序（1,2,10）

---

## ✔ `-x`

不跨文件系统（只看当前磁盘）

---

# 🧩 ③ 大写扩展参数

---

## ✔ `-A`

使用 ANSI 绘图（更漂亮树线）

---

## ✔ `-C`

彩色输出

---

## ✔ `-D`

显示最后修改时间

---

## ✔ `-F`

在目录后加 `/`

---

## ✔ `-J`

输出 JSON 格式

---

## ✔ `-Q`

文件名加引号

---

## ✔ `-N`

不转义非 ASCII 字符

---

## ✔ `-S`

显示文件类型符号（*/@等）

---

## ✔ `-U`

不排序（按文件系统顺序）

---

## ✔ `-X`

输出 XML

---

---

# 🧩 ④ 层级与结构控制

---

## ✔ `-L level`

限制目录深度

```bash id="lvl"
tree -L 2
```

---

## ✔ `-R`

递归展开（通常默认就是）

---

# 🧩 ⑤ HTML / Web 输出

---

## ✔ `-H baseHREF`

生成 HTML 树，并指定 base URL

---

## ✔ `-T title`

HTML 页面标题

---

## ✔ `-o filename`

输出到文件

```bash id="out"
tree -o out.txt
```

---

# 🧩 ⑥ 过滤类

---

## ✔ `-P pattern`

只显示匹配文件

```bash id="patt"
tree -P "*.js"
```

---

## ✔ `-I pattern`

排除匹配文件

```bash id="ign"
tree -I "node_modules"
```

---

## ✔ `--gitignore`

自动读取 `.gitignore` 排除内容

---

## ✔ `--gitfile=file`

用指定 gitignore 文件

---

## ✔ `--ignore-case`

忽略大小写匹配

---

# 🧩 ⑦ 排序控制

---

## ✔ `--sort=name`

按名称排序（默认）

---

## ✔ `--dirsfirst`

文件夹优先

---

## ✔ `--filesfirst`

文件优先

---

## ✔ `--filelimit=#`

超过数量就折叠

---

# 🧩 ⑧ 显示增强

---

## ✔ `--inodes`

显示 inode（文件系统ID）

---

## ✔ `--device`

显示设备号

---

## ✔ `--si`

用 1000 进制（KB/MB）

---

## ✔ `--du`

显示磁盘占用

---

## ✔ `--prune`

隐藏空目录

---

## ✔ `--charset=X`

设置字符集（ASCII / UTF-8）

---

## ✔ `--timefmt=format`

自定义时间格式

---

# 🧩 ⑨ 输出结构控制（高级）

---

## ✔ `--fromfile`

从文件读取结构

---

## ✔ `--fromtabfile`

从 tab 文件读取

---

## ✔ `--fflinks`

保留文件链接关系

---

## ✔ `--info`

显示额外信息

---

## ✔ `--infofile=file`

从文件读取信息

---

## ✔ `--noreport`

不显示底部统计

---

## ✔ `--hyperlink`

输出可点击链接（终端支持时）

---

## ✔ `--scheme=schema`

URL schema（用于 HTML）

---

## ✔ `--authority=host`

HTML host 设置

---

## ✔ `--opt-toggle`

切换优化模式

---

# 🧩 ⑩ 系统级命令

---

## ✔ `--version`

显示版本

---

## ✔ `--help`

显示帮助（你现在看到的就是这个）

---

## ✔ `--`

结束参数解析（后面全部当路径）

```bash id="end"
tree -- -a
```

---

# 🧠 总结（真正重点）

你这段其实是：

```text id="sum"
tree = 一个“文件系统可视化工具 + 过滤器 + HTML/JSON输出工具 + 排序工具”
```

---

# ⚡ 如果你要真正会用，只需要 5 个：

```bash id="core"
tree -L 2
tree -a
tree -I node_modules
tree -h
tree --dirsfirst
```

---
