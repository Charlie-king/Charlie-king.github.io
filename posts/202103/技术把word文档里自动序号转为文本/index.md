# 把word文档里自动序号转为文本


<!--more-->

如何把word文档里自动序号转为文本，直接可以复制出来，这里提供一种方法。

## 宏命令处理
（别有恐惧心理，不难）
1. 打开word文档，按下快捷键Alt+F8，在“宏名”栏中输入dao“编号转换为文本”，这是给它起个名字，然后点击“创建”

2. 在新打开的窗口上，你会看到光标在闪烁，把下面这4行内容复制粘贴到此
```
Dim kgslist As List
For Each kgslist In ActiveDocument.Lists
kgslist.ConvertNumbersToText
Next
```
3. 然后按下快捷键Alt+Q（或者，点击左上角“文件”——“关闭并返回到Microsoft Word”），回到word界面。

4. 光标定位在除了自动编号以外的任意位置，然后按下Alt+F8，选中“编号转换为文本”（选中后底色为蓝色），再点击“运行”。
这就完成了，自动编号就成了可以编辑的文本（真实的文字）了。


---

> 作者: Kingpo  
> URL: https://zhjin.eu.org/posts/202103/%E6%8A%80%E6%9C%AF%E6%8A%8Aword%E6%96%87%E6%A1%A3%E9%87%8C%E8%87%AA%E5%8A%A8%E5%BA%8F%E5%8F%B7%E8%BD%AC%E4%B8%BA%E6%96%87%E6%9C%AC/  

