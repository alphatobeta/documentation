# 用LaTeX处理PDF文件

主要用途：
- 插入PDF
- 分割PDF

## 安装命令
```
tlmgr install pdfpages
```
[pdfpages](https://ctan.org/pkg/pdfpages)是插入pdf的LaTeX包。

## 例子
```LaTeX
\documentclass[a4paper]{ctexart}
\usepackage{pdfpages}

\begin{document}


\includepdfset{pagecommand={\thispagestyle{plain}}}
\includepdf[pages={1,4-643}]{book.pdf}

\end{document}
```

## 常用参数
```
\includepdfset{pagecommand={\thispagestyle{plain}}}
```
这行代码是插入页码，默认插入的PDF没有标注页码。

`pages`是控制页数范围。

页码组合的常见类型：
- 零散页码，`pages={3,5,6,12}`
- 连续类型，`pages={2-10}`
- 中间插入空页， `pages={1,{},6-12,100}`
- 插入全部页码，`pages=- `
- 逆序插入全部页码` pages=last-1`

## 协议
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />本<span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" rel="dct:type">作品</span>由<span xmlns:cc="http://creativecommons.org/ns#" property="cc:attributionName">Cheng Jun</span>采用<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">知识共享署名-相同方式共享 4.0 国际许可协议</a>进行许可。
