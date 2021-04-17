# OJ 上机建议

## 用项目管理你的代码

​	在答疑过程中，发现仍然有很多同学把所有题目写在一个文件里面，这是很不好的编程习惯,需要尽早改掉。还有的同学虽然一题一个文件，但文件管理混乱，典型的例子便是一堆未命名文件，无法将文件与题目对应起来。

![unnamed](https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-11-unnamed.jpg)

在这里推荐使用 spyder 项目管理每次上机的文件。具体过程如下。

1. 单击项目->新项目->新的目录。然后随便选择一个文件夹（我选择的是OJ文件夹，也推荐你们用一个专门的文件夹存储每次OJ的代码），然后为你的项目取一个名字（我取的是hw4，代表第四次作业）。然后点击创建。

   ![project](https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-12-project.jpg)

2. 此时spyder会自动打开新创建的项目，并在最左侧的项目窗格显示你刚刚新建的项目。

   <img src="https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-12-ProWindow.jpg" alt="ProWindow" style="zoom:150%;" />

3. 点击文件->新建，spyder就会自动在该项目里面新建一个Python文件，然后你就可以在该文件里面写下你的代码并保存。当你写完全部OJ题目，效果如下。

   

<img src="https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-12-ProStruct.jpg" alt="ProStruct" style="zoom: 67%;" />

t注：这些文件的命名只是一个示例，你完全可以按照自己的风格命名文件。

## 变量命名风格

​	无论是对你还是对别人而言,有一个好的变量命名风格可以使你的代码有更高的易读性。下面是一些变量命名风格的建议。

- 尽量不要使用无意义的名字，例如有些同学使用s，ss，sss为变量取名，这种毫无意义的名字不仅难读，而且你会很容易打错变量名，导致bug产生。

- 尽量避免使用中文拼音命名变量，burannnidedaimahuihezhejuhuayiyangfeijie（不如你的代码会和这句话一样费解）

  下面是一段代码示例（第四次作业第6题）

  - ```python
    shuzu=list(map(eval,input().split()))
    zuidazhisuoyin= shuzu.index(max(shuzu))
    shuzu[0],shuzu[zuidazhisuoyin]=shuzu[zuidazhisuoyin],shuzu[0]
    zuixiaozhisuoyin = shuzu.index(min(shuzu))
    shuzu[-1],shuzu[zuixiaozhisuoyin]=shuzu[zuixiaozhisuoyin],shuzu[-1]
    print(shuzu)
    ```

- 我个人习惯使用英文单词命名变量，每个单词首字母大写以区分单词。示例如下

  - ```python
    a=list(map(eval,input().split()))
    MaxIndex= a.index(max(a))
    a[0],a[MaxIndex]=a[MaxIndex],a[0]
    MinIndex = a.index(min(a))
    a[-1],a[MinIndex]=a[MinIndex],a[-1]
    print(a)
    ```

注：关于变量命名风格，可以上网查阅相关资料，但要记住适合自己的才是最好的，你也不一定要按照我的风格来。

## 注释的使用

		在恰当的位置使用注释可以使你的代码更加易读，你可以根据注释轻松的理清代码的逻辑，这里给一个示例。

```python
"""
Created on Mon Apr  5 21:42:01 2021

@author: 教教1

题目描述
输入数组，最大的与第一个元素交换，最小的与最后一个元素交换，输出数组。
输入
输入是一行，有多个整数，每个整数之间用空格隔开。
输出
输出元素交换过的列表。
"""
a=list(map(eval,input().split())) #读入一个数字列表
MaxIndex= a.index(max(a))
a[0],a[MaxIndex]=a[MaxIndex],a[0] #交换最大的和第一个元素
MinIndex = a.index(min(a))
a[-1],a[MinIndex]=a[MinIndex],a[-1]#交换最小的和最后的元素
print(a)
```

## 如何调试你的代码

​	当你们发现自己的代码被OJ平台判错的时候，除了请求助教的帮助，学会自己debug是至关重要的。然而，你们大多数人debug的方法可以用一个字概括--”看!"，就是对着代码来回看个好几遍。显然,这是一种相当低效的debug方法，尤其是在之后代码量上来的情况下，光采用“看”根本找不出bug，这时候就需要学会使用spyder的调试工具。

​	这里给出第四次作业第六题的调试过程。错误代码如下

```python
a=list(map(eval,input().split())) #读入一个数字列表
Max = max(a)
a[0],Max = Max,a[0] #交换最大的和第一个元素
Min = min(a)
a[-1],Min = Min,a[-1] #交换最小的和最后一个元素
print(a)
```



### 构造测试用例

​	通常情况下你们在通过老师提供的测试用例之后，提交却被OJ平台判错。这是因为老师提供的测试用例覆盖的情况很少，你们需要自己构造新的测试用例以覆盖其他情形。例如，在货币兑换那道题，老师只提供了美元转人名币的测试用例，你们需要自己构造人名币转美元的用例以检测你们的代码。

​	当然，如果连老师提供的测试用例都通过不了，就暂时不需要构造新的测试用例了。

​	在你发现测试用例运行结果错误之后，便可以使用spyder的调试工具调试你们的代码。

​	这里直接使用老师提供的测试用例，运行结果如下

![res](https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-13-res.jpg)

​	发现运行结果错误，开始进行调试。

### spyder调试工具

​	先简单介绍一下调试工具，更详细的使用说明请查阅spyder官方文档和其他相关资料。

#### 断点

​	通过在对应代码最左侧单机鼠标左键，便可在该代码处打上断点。这样在以调试模式运行文件的时候，程序会在执行到断点处自动停止。

​	例如，我们左击2行和第3行，便在这两行成功打上了断点。

![breakPoint](https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-13-breakPoint.jpg)

#### 变量资源管理器

​	在变量资源管理器中可以查看程序当前状态所有变量的值。（由于此处未运行程序，所以没有任何显示）

![varView](https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-13-varView.jpg)

#### 调试工具栏

![debugTool](https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-13-debugTool.jpg)

​	在spyder调试工具栏中共有六个调试工具，分别为

- 调试文件：以调试的方式运行该文件
- 运行当前行：执行当前行的代码
- 步入当前行的函数或方法：暂不需要掌握
- 执行当前函数或方法返回：暂不需要掌握
- 继续运行直到下一断点：一直运行代码，直到遇到断点才停止运行，如果之后没有断点，便运行到代码结束。
- 停止调试：退出调试模式

#### ipdb

如果说前面的是图像界面的调试工具,ipdb就是命令行形式的调试工具。本着能用图像界面就不用命令行的原则（其实就是懒），此处不再详细解释，感兴趣的同学请自学查找相关资料。

### 调试过程

1. 点击调试文件按钮，进入调试模式，在输入数据后程序自动执行到第一个断点处。可以看到程序停在了第二行，变量资源管理器中显示了a的值为[1,2,3,7,9,8]，代码执行正确。

   注：由于第二行之后的代码未执行，变量Max和Min还未生成，所以在变量资源管理器中查看不了它们的值。

   <img src="https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-13-debug1.jpg" alt="debug1" style="zoom: 50%;" />

2. 点击继续运行直到下一断点，程序停在了第三行。

   可以看到变量Max已生成，并且值为9,确实是数组的最大值,程序到目前为止执行正确。

   

   <img src="https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-14-debug2.jpg" alt="debug2" style="zoom: 67%;" />

   

3. 运行当前行，程序执行了第三行并停在了下一行。我们预计执行完该行代码后，列表a的值应为[9,2,3,7,1,8]。但在变量资源管理器中看到列表a的值为[9,2,3,7,9,8]，另外变量Max的值却变成了1。我们发现程序出错了。

   <img src="https://gitee.com/kangkangxka/pic-bed/raw/master/Python/04-17-11-14-debug3.jpg" alt="debug3" style="zoom:67%;" />

   分析原因发现我们交换的是变量Max和列表第一个元素，而不是列表最大的元素和第一个元素发生交换。

4. 点击停止调试，退出调试模式，修改代码为

   ```python
   a=list(map(eval,input().split())) #读入一个数字列表
   MaxIndex= a.index(max(a))
   a[0],a[MaxIndex]=a[MaxIndex],a[0]#交换最大的和第一个元素
   MinIndex = a.index(min(a))
   a[-1],a[MinIndex]=a[MinIndex],a[-1]#交换最小的和最后一个元素
   print(a)
   ```

   再次运行文件，发现运行结果正确。

## 其他一些小技巧

### 批量注释代码

当你发现代码错误的时候，最好不要直接删掉原来的代码。因为你后面可能会发现之前的代码其实大体是正确的，但要改回来的时候只能重新写一遍。推荐的方式是使用ctrl+1注释掉错误的代码，并在下面写上更改后的代码。

```python
a=list(map(eval,input().split())) #读入一个数字列表
# Max = max(a)
# a[0],Max = Max,a[0] #交换最大的和第一个元素
# Min = min(a)
# a[-1],Min = Min,a[-1] #交换最小的和最后一个元素

MaxIndex= a.index(max(a))
a[0],a[MaxIndex]=a[MaxIndex],a[0] #交换最大的和第一个元素
MinIndex = a.index(min(a))
a[-1],a[MinIndex]=a[MinIndex],a[-1] #交换最小的和最好一个元素

print(a)
```