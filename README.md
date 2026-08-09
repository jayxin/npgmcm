# NPGMCM 

- LaTeX Template for National Post-Graduate Mathematical Contest in Modeling
- 全国研究生数学建模竞赛 LaTeX 模板
- 项目地址: [npgmcm](https://github.com/jayxin/npgmcm)
- 本项目在[andy123t](https://github.com/andy123t)的[GMCMthesis](https://github.com/andy123t/GMCMthesis)项目基础上修改和添加内容，并调整项目结构，使整个项目结构更清晰，方便使用和维护。在此感谢原作者[latexstudio](https://github.com/latexstudio)和[andy123t](https://github.com/andy123t)的贡献！

## 文件列表

```none
.
├── commons/ 模板
│   ├── fonts/ 不同操作系统下的字体方案定义
│   │   ├── npgmcm-font-fandol.def linux 系统
│   │   ├── npgmcm-font-mac.def Mac OS 系统
│   │   └── npgmcm-font-windows.def Windows 系统
│   ├── npgmcm.bst 参考文献渲染样式定义
│   ├── npgmcmthesis.cls 基础模板
│   └── preamble.tex 用户自定义添加宏包、命令等
├── contents/ 内容
│   ├── abstract.tex 摘要
│   ├── appendix/ 附录
│   ├── info.tex 论文基本信息
│   ├── references.bib 参考文献数据库
│   ├── references.tex 参考文献
│   └── sections/ 正文内容
├── docs/ 论文格式说明和模板等文档
│   ├── 第二十二届中国研究生数学建模竞赛论文格式规范.pdf
│   └── 第二十二届中国研究生数学建模竞赛论文模板.doc
├── figures/ 存放论文用到的图片文件
│   ├── logo.pdf 封面的 logo
│   └── title.pdf 竞赛名称
├── fonts/ 存放字体文件, 保持原位, 无需安装
│   ├── kai.ttf 楷体
│   ├── lishu.ttf 隶书
│   └── source-series/ 思源系列字体
│       ├── SourceHanSansCN-Regular.ttf 黑体
│       ├── SourceHanSerifCN-Regular.ttf 宋体
│       └── SourceHanSerifCN-SemiBold.ttf 宋体-加粗
├── .gitignore git 版本控制忽略文件
├── latexmkrc latexmk 配置文件
├── LICENSE.txt 使用许可
├── main.tex **主文档(Main document, 编译入口文件)**
└── README.md 项目说明
```

## 编译

### 本地编译

- 使用前提: 本地已装好 LaTeX 的发行版如 TeXLive
- 已测试环境:
	+ 操作系统 - Linux
	+ LaTeX 发行版 - TeXLive 2023

#### 方法1-用 xelatex 编译

需手动编译多次，引用等内容才能正确显示。

```sh
xelatex main
bibtex main
xelatex main
xelatex main
```

#### 方法2-用 latexmk 编译

自动编译多次:

```sh
latexmk main
```

清理辅助文件(`log`、`aux`等):

```sh
latexmk -c main
```

清理辅助文件(`log`、`aux`等)和 `pdf`:

```sh
latexmk -C main
```

### 在线编译

- 可使用在线的编译平台进行编译如:
	+ [TeXPage](https://texpage.com)
	+ [OverLeaf](https://overleaf.com)
- 已测试平台: TeXPage, 进行编译前需保证如下设置
	+ 编译器: `xelatex`
	+ TeXLive 版本: 2023
	+ 主文档(Main Document): main.tex

## 文档类选项说明

本项目文档类(Document Class)目前支持下面的选项:
- `draft`: 是否嵌入图片和代码, 默认嵌入。此选项目的是为了在LaTeX编辑过程中提高编译速度, 最终文档请勿包含此选项！
- 打印选项:
	* `bwprint`: 黑白打印。
	* `colorprint`: 彩色打印(默认)。
- `withoutpreface`: 最终文档不含封面, 不加此选项则默认包含。
- 操作系统选项(影响文档使用的字体, 根据您的操作系统做相应的更改):
  * `linux`: 使用本项目 `fonts/` 目录下的字体和 LaTeX 发行版自带字体
  * `windows`: 使用 Windows 操作系统的字体
  * `mac`: 使用 Mac 操作系统的字体

示例:

```latex
\documentclass[windows,bwprint,withoutpreface]{commons/npgmcmthesis}
```

这个例子使用 Windows 操作系统的字体、黑白打印、不带封面。

<!-- vim: set noet: -->
