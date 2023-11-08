---
title: "使用VSCode编写Keil工程代码"
date: 2023-11-06T19:37:25+08:00
draft: false
categories: ["工具"]
tags: ["VSCode", "Keil", "includ错误"]
aliases: [write_Keil_project_code_using_VSCode]
summary: "利用VSCode的Keil Assistant插件来编写Keil项目代码。"
---

# 安装软件和插件

1. 去[VSCode官网](https://code.visualstudio.com/)下载并安装 vscode；

2. 安装 vscode 插件；

    - c/c++

        <img src=assets/1.png width=40%>

    - Keil Assistant

        <img src=assets/2.png width=40%>

---

# Keil Assistant配置

设置UV4.exe的路径

<img src=assets/3.png>


---

# 使用步骤

1. 确保插件都已启用

2. 打开Keil工程

    <img src=assets/4.png>

3. 确认在工作区中打开

    <img src=assets/5.png width=70%>

4. 确认在新工作区中是否启用了插件。如果没有，就启用它们。

---

# 可能遇到的问题

## vscode检测到 #include 错误

- #include 错误截图

  <div align=center>
    <img src=assets/6.png width=70%>
  </div>

- 解决方法

  1. 按住 **<kbd>Win+R</kbd>** 打开运行框，再输入 `cmd`。

    <div align=center>
      <img src=assets/7.png width=60%>
    </div>

  2. 进入项目目录，然后输入命令 `gcc -v -E -x c++ -`

    <div align=center>
      <img src=assets/8.png width=100%>
    </div>

  3. 复制结果中的include路径

    <div align=center>
      <img src=assets/9.png width=100%>
    </div>

  4. 在 vscode 中按下 **<kbd>Ctrl+Shift+P</kbc>**，然后输入 `C/C++:EditConfigurations`，最后选择后缀为UI的那一项，打开C/C++的配置界面。

    <div align=center>
      <img src=assets/10.png width=100%>
    </div>

  5. 把之前复制的include路径粘贴到C/C++扩展设置界面的包含路径框内。

    <div align=center>
      <img src=assets/11.png width=100%>
    </div>

- 补充

  如果发现还显示**检测到 #include 错误**。**请更新 includePath**。此时，**不必慌张**，只需要在 vscode 界面上，按住 **<kbd>Ctrl+Shift+P</kbd>**，然后再在输入框输入 **`reload`**，并选择**开发人员：重新加载窗口**。加载完成之后，问题即可得到解决。