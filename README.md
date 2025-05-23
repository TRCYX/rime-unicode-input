# Unicode 数学符号输入

基于 [RIME](https://rime.im) 的 Unicode 数学符号输入方案。

使用命令输入数学符号，如 `\exists` 输入 `∃`。共提供命令以 `\`（默认）、`@`、`;` 开始的三个版本。

目前命令列表由 [Lean4 VSCode 扩展](https://github.com/leanprover/vscode-lean4/tree/master) 的命令列表改编而来。

## 安装

1. 在 [RIME 的网站](https://rime.im) 安装合适的 RIME 输入法。
2. 将本项目的 YAML 文件放在 [用户文件夹](https://github.com/rime/home/wiki/UserData) 下。
3. 在 `default.custom.yaml` 或输入法图形界面中选中“Unicode 数学符号”输入方案（或 `@`、`;` 的版本）。

## 自定义命令

在用户文件夹中的 [unicode_math.dict.yaml](./unicode_math.dict.yaml) 中后半部分新增一行，输入以 <code>Tab</code> 隔开的输入结果和命令即可。保存后，[重新部署](https://github.com/rime/home/wiki/CustomizationGuide#%E9%87%8D%E6%96%B0%E4%BD%88%E7%BD%B2%E7%9A%84%E6%93%8D%E4%BD%9C%E6%96%B9%E6%B3%95) 输入法数据。

命令以 `@` 开始和 `;` 的版本则对应修改 [unicode_math_at.dict.yaml](./unicode_math_at.dict.yaml) 或 [unicode_math_semi.dict.yaml](./unicode_math_semi.dict.yaml)。

※注意：
- [unicode_math.schema.yaml](./unicode_math.schema.yaml) 中 `speller.initials` 一项要求命令均以反斜杠 `\` 开始。`@` 和 `;` 开始的版本类似。
- 不要以空格替换分隔输入结果和命令的 <code>Tab</code>。

## 可能的用法

在 $\LaTeX$ 中，启用命令以 `;` 开始的版本。在 preamble 中引入相关支持 Unicode 数学输入的宏包，如下面两者之一：
```LaTeX
\usepackage{unicode-math} % 仅支持 Unicode 引擎，如 XeLaTeX 或 LuaLaTeX
\usepackage{unicode-math-input} % 也支持 pdfLaTeX
```

对于符号在上述宏包之外的情况，或需要调整某个符号的生成的具体命令，可以这么做：
```LaTeX
\usepackage{newunicodechar}
\newunicodechar{▷}{\vartriangleright} % 给出单个字符和替换的内容
```

## 开源许可

本项目与命令列表来源 Lean4 VSCode 扩展均遵循 [Apache 2.0](./LICENSE) 许可证。
