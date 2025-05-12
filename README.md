# Unicode 数学符号输入

基于 [RIME](https://rime.im) 的 Unicode 数学符号输入方案。

使用以 `\` 开头的命令输入数学符号，如 `\exists` 输入 `∃`。

目前命令列表由 [Lean4 VSCode 扩展](https://github.com/leanprover/vscode-lean4/tree/master) 的命令列表改编而来。

## 安装

在 [RIME 的网站](https://rime.im) 安装合适的 RIME 输入法，并将本项目的两个 YAML 文件放在 [用户文件夹](https://github.com/rime/home/wiki/UserData) 下。在 `default.custom.yaml` 或输入法图形界面中选中“Unicode 数学符号”输入方案。

## 自定义命令

在用户文件夹中的 [unicode_math.dict.yaml](./unicode_math.dict.yaml) 中后半部分新增一行，输入以 <code>Tab</code> 隔开的输入结果和命令即可。保存后，[重新部署](https://github.com/rime/home/wiki/CustomizationGuide#%E9%87%8D%E6%96%B0%E4%BD%88%E7%BD%B2%E7%9A%84%E6%93%8D%E4%BD%9C%E6%96%B9%E6%B3%95) 输入法数据。

※注意：
- [unicode_math.schema.yaml](./unicode_math.schema.yaml) 中 `speller.initials` 一项要求命令均以反斜杠 `\` 开头。
- 不要以空格替换分隔输入结果和命令的 <code>Tab</code>。

## 开源许可

本项目与命令列表来源 Lean4 VSCode 扩展均遵循 [Apache 2.0](./LICENSE) 许可证。
