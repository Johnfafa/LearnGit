# hello world
## hello world
### hello world
段落  
两个空格+换行是段落  
*斜体字*  
**粗体字**  
***又粗又斜体***  
***

~~删除线~~ 两个波浪线  
<u>下划线</u>  
这是一个脚注的例子[^1]   
[^1]: 这里是脚注  
***  

行内代码(`markdown`)

1. 列表
2. 列表2
3. 列表3  

+ +列表
    * *嵌套列表
    * *嵌套列表2
        - -再嵌套

> 区块
> > 嵌套区块
> > > 再嵌套区块

> 区块+列表
> 1. 列表
> 2. 列表2

```c#
using system.io
console.writeline("hello world");
```
***  
链接地址啦啦  [百度](https://www.baidu.com)
<https://www.baidu.com>
链接地址啦啦啦需要空出一行，并需要开头两个空格 [baidu][2]  

  [2]: https://www.baidu.com/

***
#####表格要撑开才看的清楚左右中间对齐 :--   --:   :--:
| 表格1ddd | 表格2fff | 表格3ggg|
| :-----| ----: | :----: |
| 表格 | 表格 | 表格|
| 表格 | 表格 | 表格|

###高级应用

```mermaid
%% 时序图例子,-> 直线，-->虚线，->>实线箭头
  sequenceDiagram
    participant 张三
    participant 李四
    张三->王五: 王五你好吗？
    loop 健康检查
        王五->王五: 与疾病战斗
    end
    Note right of 王五: 合理 食物 <br/>看医生...
    李四-->>张三: 很好!
    王五->李四: 你怎么样?
    李四-->王五: 很好!
```