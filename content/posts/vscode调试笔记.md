+++
title = 'Vscode调试笔记'
date = 2024-09-24T00:10:02+08:00
draft = true
tags = ["vscode"]
Categories = ["技术文章", "博客"]
+++
### vscode调试笔记
记录使用vscode调试的一些概念和基础，主要关于go调试，摆脱goland的第一步（太吃内存了）。
### launch.json
lacnchh.json 为调试配置文件，包括调试模式，调试的文件夹，环境，语言等。

    ```
    {
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Launch",//调试配置名
            "type": "go",
            "request": "launch",//有lanch 和attch 两种模式
            "mode": "debug",
            "program": "${fileDirname}",//在当前打开的文件开始调试，根据vscode文档可以陪不同的地方
            "env": {},
            "args": []//变量
        }
    ]
}
### attach和lanch
#### lanch
定义：在 "launch" 模式下，调试器会启动一个新的程序实例，并立即开始调试该实例。
用途：当你需要从头开始调试一个程序时，通常使用 "launch" 模式。这适用于你希望从程序的入口点开始调试，或者需要在程序启动时设置断点的情况。
#### attach 
attach"：指示调试器附加到一个已经运行的进程。
processId: 指定要附加的进程 ID。可以使用 ${command:PickProcess} 来选择进程。
port: 指定调试器连接的端口（如果适用）。
### 
