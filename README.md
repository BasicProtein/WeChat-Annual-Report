# WeChat-Annual-Report

微信年度报告
**[抖音ID：dy1mn2hw9tcgv  [昵称：BasicProtein] 点击跳转](https://v.douyin.com/iNDvkKwC/)**




# **一、前言**

## **序言：**

- 本项目复现难度并不高，如果你有一定的计算机基础，最快只要10-20min就可以成功复现
- 如果你是计算机小白，也不用担心，代码好多地方我也写了注释，大概需要20-50min完成复现
- 如果你想创新，可以在我的基础上根据自己的喜好做出个性化创作，祝大家顺利！

## **硬件准备：**

1.**电脑一台：**Windows或Mac OS均可以（Windows要求WIN10及以上）；

2.**手机一部：**含有微信聊天记录（IOS&Android&Harmony OS均可）；



应各位粉丝的要求，我拖了好久的时间，终于写完了这篇教程。可能做不到事无巨细，但是各位的问题我一定悉数解答，不留余地。

大家如果有问题，可以搜索获得解答，也可以直接在抖音评论区或者私信提问。
**[抖音ID：dy1mn2hw9tcgv  [昵称：BasicProtein] 点击跳转](https://v.douyin.com/iNDvkKwC/)**
本项目的所有工具以及本教程文档我会同步到个人Github仓库，欢迎关注！
[**Github ID：BasicProtein 点击跳转**](https://github.com/BasicProtein/WeChat-Annual-Report)

# **二、提取聊天记录**

早在2023年末，Github上就有一些开源项目获取微信的聊天记录，本项目选择使用的是留痕。

## **工具下载**

**[Github - WeChatMsg](https://github.com/LC044/WeChatMsg)**

部分网友可能无法打开链接，在这里我提供一下静态直链的地址：

**[MemoTrace-1.1.1.exe 点击即可下载](https://cloud.ananas.chaoxing.com/view/fileviewDownload?objectId=8040f072b942b5af1913ba21571276b8)**

如果以上地址都失效了，可以去作者的微信公众号寻找：

![image-20240215175639631](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/8c48e1ba-6742-4920-a1ed-a536feaca6bc)

![image-20240215183416026](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/f9dc182b-3c8a-4174-936b-8705b44f348a)

**注：如果需要做后面的数据可视化，这里的WeChatMsg请务必下载1.0.2及以后的版本，否则导出的聊天记录可能无法正常使用！截止2024年1月12日，1.0.2以及1.0.3的留痕导出的聊天记录可用。**

## **效果图展示**

我下载之后便尝鲜了，下面附上效果图：

![01](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/e2a242ed-165d-4846-80ed-ee3600a2c886)

![02](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/9b6b1aff-4ee4-4914-b0a9-3e2263eac8d4)

![03](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/1f7139a3-18ee-42fe-8ded-6f2f8ec0f1ce)

![04](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/4430a3a4-bd4d-49e2-90ec-8ce21c3ed78a)

![05](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/0dd7a02c-4e8f-4298-b602-55eb7300f50c)

![06](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/2dc50fcd-39e2-4130-b865-3b266a62fea4)

![image-20240215182959465](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/38513532-92ea-400e-9055-ae2968c593c3)

![image-20240215183053378](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/480bbd44-5481-4959-943c-42b03652c892)

![image-20240215183112035](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/f2fc3355-6a2b-4cf9-8fcc-b73109781caf)

![image-20240215183128524](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/5dea79be-cc63-4547-b719-c8aac17f293a)

> 如果你想实现的是以上的效果图，那么教程到此结束！

以上只是简单地做了一些数据分析，我觉得还不够细致，也不足够个性化。23年12月份我成功地获取了微信地加密聊天数据，奈何当时不会分析，于是寒假我便从0开始学习Python，如今终于可以对这些聊天数据做一些统计学分析。


# **三、解析聊天记录**

留痕的作者能力十分出众，以至于他的工具WeChatMsg可以一键破解并保存数据库到本地，同时支持批量导出csv、txt、word、html等多种格式，功能十分强大。

## **1.导出CSV数据表**

前面下载好的WeChatMsg工具，直接右击以管理员身份运行，加载时间取决于电脑配置（笔者使用的是LEGION拯救者Y7000P，耗时大概0.76s，如果一次不行，请多尝试几次）

**注：如果需要做后面的数据可视化，这里的WeChatMsg请务必下载1.0.2及以后的版本，否则导出的聊天记录可能无法正常使用！截止2024年1月12日，1.0.2以及1.0.3的留痕导出的聊天记录可用。**

![image-20240215190531227](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/057e92ab-425d-4724-8a1a-bcbd67df0729)

<p align="center">用WeChatMsg导出csv文件</p>

## **2.配置Python环境**

推荐工具：

- PyCharm
- VSCode
- Jyputer
- Colab

选择一个即可，在本项目中，我选择的是Colab。下面我将会贴出一些代码，不一定准确，仅供参考。

![image-20240215203136813](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/95ac81eb-de61-40d0-819d-a415cc821402)

数据处理的过程绝大部分是基于Python代码，所以Python环境必不可少。安装Python的过程我直接引用其他作者的帖子，非常详细：

[全网最详细的Python安装教程（Windows）](https://zhuanlan.zhihu.com/p/344887837)

[Jupyter Notebook中使用pandas统计分析基础](https://blog.csdn.net/junleon/article/details/120698578)

这些软件下好时，一般会缺少一些扩展库，直接运行代码会报错，我们可以根据报错信息安装对应的缺少模块。

常用命令如下：`pip install xxx`，xxx为缺失的模块名称

**代码移植说明**：
我的代码里面，在你们复现时主要需要修改一些文件路径：

```python
# 读取数据集
`df = pd.read_csv(r"/content/drive/My Drive/fj_utf8.csv", sep=',')`
```

这段代码涉及的路径需要修改成你存储CSV数据集的路径

## **3.前置代码解析**

（1）先导入需要的库

```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import time
import matplotlib

from matplotlib.font_manager import *#如果想在图上显示中文，需导入这个包
from matplotlib import cm
from datetime import datetime
from scipy.stats import boxcox
```

（2）读取数据集

这里代码中的`“r"/content/drive/My Drive/fj_utf8.csv", sep=','"`替换成你的CSV数据集文件存储目录。

```
# 读取数据集
df = pd.read_csv(r"/content/drive/My Drive/fj_utf8.csv", sep=',')
# 查看前10行的数据
df.head(10)
```

![image-20240215204159959](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/d0ffe619-de86-4b64-887a-55d6541a12ac)

在这份结果中，我们可以大致了解一下：原始数据一共12列，8w+行，说明我们俩在近6个月里共发出这么多消息，我觉得应该算挺多的了吧？但我感觉我很沉默寡言。

# **四、数据预处理**

数据预处理在数据分析中的主要目的是剔除无效数据，减少结果的偶然性，在本项目中，由于工具作者已经把数据集里面的Unix Time转换成了日期时间，因此数据预处理可做可不做。

## **去除无用信息**：

数据集的后三列，以及'Status'这一列都是NaN（非数值），属于无用数据，直接可以剔除掉。

```python
# 去掉'Status'和'Remark','NickName','Sender'，因为它们只有一个类。

df = df.drop(['Status', 'Remark', 'NickName', 'Sender'], axis=1)
# 查看前2行的数据
df.head(2)
```

## **补充说明：**

这里附上信息类型的声明：其中，Type表示的是消息的类型：

> \# Type = 10000 撤回、拍一拍、添加好友等系统消息
>
> \# Type = 1 文本消息
>
> \# Type = 3 图片消息
>
> \# Type = 34 语音消息
>
> \# Type = 43 视频消息
>
> \# Type = 47 emoji
>
> \# Type = 48 定位
>
> \# Type = 49 /
>
> \# Type = 50 通话
>
> \# IsSender中为1的是我发的消息，为0的是对方发的消息

# **五、数据分析**

## **1.聊天数据统计**

根据刚刚的“消息类型说明”我们可以得出双方消息发送量的对比，从而得出我们的性格状态。

```python
# 读取数据集
df = pd.read_csv(r"/content/drive/My Drive/fj_utf8.csv", sep=',')
# 查看前10行的数据
df.head(10)
```

![image-20240217222933251](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/33c83afd-b0d6-4f6a-aaff-c08da434c0bd)

根据以上处理过的数据集，我们可以得出：4月的聊天最多，7月最少。

## **2.每月消息数量趋势**

根据预处理后的数据集，我们可以得到每月发送的消息数量。

```python
df2['month'] = pd.to_datetime(df2['StrTime']).dt.month

month_counts = df2['month'].value_counts().sort_index()

scaled_sizes = month_counts * 0.08

# 绘制散点图
plt.figure(facecolor='white')

plt.title('Figure 1: Monthly Trends in Message Counts', fontname='Times New Roman',fontsize=22)

plt.xlabel('Month', fontname='Times New Roman',fontsize=20)
plt.ylabel('Messages', fontname='Times New Roman',fontsize=20)
plt.xticks(range(1, 13), fontname='Times New Roman',fontsize=15)
plt.yticks(fontname='Times New Roman',fontsize=15)

plt.scatter(month_counts.index, month_counts.values, color='#80BCBD', marker='o',s=scaled_sizes)

plt.grid(True, linestyle='solid', linewidth=1, color='lightgrey',axis='y')

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('chat_month.png',dpi=100)
plt.show()
```

![下载1](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/b947fb58-4f00-4da2-882e-0aca9ee3db55)

## **3.双方消息数量趋势**

接下来我们细化一下双方发送的消息数量，同时可以得出极值是多少。以此绘制折线统计图，得出双方消息数量趋势。

```python
df2['month_bobo'] = pd.to_datetime(df2[df2['IsSender'] == 1]['StrTime']).dt.month
df2['month_pupu'] = pd.to_datetime(df2[df2['IsSender'] == 0]['StrTime']).dt.month

labels = ['PUPU', 'BOBO']
colors = ['#FFC0D9', '#8ACDD7']

month_counts_bobo = df2['month_bobo'].value_counts().sort_index()
month_counts_pupu = df2['month_pupu'].value_counts().sort_index()

# 找到PUPU和BOBO每个月的最大值和对应的月份
max_bobo = month_counts_bobo.max()
max_month_bobo = month_counts_bobo.idxmax()

max_pupu = month_counts_pupu.max()
max_month_pupu = month_counts_pupu.idxmax()

month_counts_pupu.plot(kind='line', marker='o', label='PUPU',color='#FFC0D9')
month_counts_bobo.plot(kind='line', marker='o', label='BOBO',color='#8ACDD7')

# 在最高点上添加标签
plt.annotate(f'Max: {max_pupu}', xy=(max_month_pupu, max_pupu), xytext=(max_month_pupu + 0.5, max_pupu + 10),
             arrowprops=dict(facecolor='black', arrowstyle='->'),
             fontsize=18,fontname='Times New Roman')

plt.annotate(f'Max: {max_bobo}', xy=(max_month_bobo, max_bobo), xytext=(max_month_bobo + 0.4, max_bobo + 10),
             arrowprops=dict(facecolor='black', arrowstyle='->'),
             fontsize=18,fontname='Times New Roman')

plt.title('Figure 2: Trends in Monthly Message Counts', fontname='Times New Roman',fontsize=22)

plt.xlabel('Month', fontname='Times New Roman',fontsize=20)
plt.ylabel('Messages', fontname='Times New Roman',fontsize=20)
plt.xticks(range(1, 13), fontname='Times New Roman',fontsize=15)
plt.yticks(fontname='Times New Roman',fontsize=15)

plt.grid(True, linestyle='solid', linewidth=0.5, color='lightgrey')

font_prop = FontProperties(family='Times New Roman')
plt.legend(labels, loc="best",prop=font_prop)

plt.tight_layout()  # 优化布局，确保标签和标题不重叠

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('chat_plot.png',dpi=100)
plt.show()
```

![下载2](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/ba86f360-0b1b-4af7-a421-7d4ae72128d9)

## **4.饼图绘制**

饼图可以主观的看到双方交流次数的差异。

```python
value_counts = df2['IsSender'].value_counts()

# 计算百分比
percentages = 100. * value_counts / value_counts.sum()

# 创建饼图
labels = ['PUPU', 'BOBO']
colors = ['#FFC0D9', '#8ACDD7']
explode = (0.1, 0)  # 突出显示第一个切片

plt.figure(figsize=(8, 8))

# 定义格式化函数，用于在饼图内部显示数据
def func(pct, allvals):
    absolute = int(pct/100.*np.sum(allvals))
    return f"{pct:.1f}%\n({absolute:d})"

plt.pie(value_counts, explode=explode, labels=labels, colors=colors,
        autopct=lambda pct: func(pct, value_counts), shadow=True, startangle=80, textprops={'style':'italic' , 'fontsize': 18})

plt.title('Figure 3: Distribution of Messages: PUPU vs. BOBO', fontname='Times New Roman',fontsize=22)
font_prop = FontProperties(family='Times New Roman')
plt.legend(labels, loc="best",prop=font_prop)
plt.axis('equal')  # 使饼图保持圆形

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('chat_pie',dpi=100)
plt.show()
```

![下载3](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/2303774d-b5f9-44b2-bb77-cba5cbbb1b61)

竟然多了2.2%，更多信息自行挖掘！

## **5.周内消息分布**

周内消息分布可以得出在一周内哪一天交流最多，哪一天交流最少，由此分析你们之间的交流情况。

```python
dates = pd.to_datetime(df2['StrTime'])
weekdays = dates.dt.day_name()

weekday_counts = weekdays.value_counts()

# 绘制饼图

colors = ['#FF90BC', '#FFC0D9', '#F9F9E0', '#8ACDD7', '#EEE7DA', '#88AB8E', '#AFC8AD']
explode = (0.1, 0, 0, 0, 0, 0, 0)  # 突出显示第一个切片
plt.figure(figsize=(8, 8))

plt.pie(weekday_counts, explode=explode, labels=weekday_counts.index, colors=colors, autopct='%1.1f%%', shadow=True, startangle=90,textprops={'fontsize': 18})
plt.title('Figure 4: The Distribution of Messages during the Week', fontname='Times New Roman',fontsize=22)
font_prop = FontProperties(family='Times New Roman')
plt.legend(labels=weekday_counts.index, loc="best",prop=font_prop)
plt.axis('equal')  # 使饼图保持圆形

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('chat_pie_2',dpi=100)
plt.show()
```

![下载4](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/27c41fcd-8d51-43ed-a629-03fbf3ef601c)

## **6.双方日内消息分布**

将一天划分为24小时，以此统计每小时的消息数量。

```python
df2['hour'] = pd.to_datetime(df2['StrTime']).dt.hour

plt.title('Figure 5: The Distribution of Messages throughout the Day', fontname='Times New Roman',fontsize=18)
plt.xlabel('Time', fontname='Times New Roman',fontsize=18)
plt.ylabel('Number of messages', fontname='Times New Roman',fontsize=18)

sns.set_style('darkgrid')#设置图片为深色背景且有网格线

sns.histplot(df2['hour'],bins=24,kde=True, color='lightcoral')

plt.xticks(np.arange(0, 25, 1.0), fontname='Times New Roman',fontsize=15)
plt.yticks(fontname='Times New Roman',fontsize=15)

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('chat_time.png',dpi=100)
plt.show()
```

![下载5](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/4bfd21b9-5b60-4c08-85d3-c8550992b4f3)

## **7.我方日内消息分布**

刚刚分析双方日内消息分布，接下来逐一分析我方与对方日内消息分布，先是我方消息分布。

```python
df2['hour'] = pd.to_datetime(df2[df2['IsSender'] == 0]['StrTime']).dt.hour

plt.title('Figure 6: The Distribution of Messages throughout the Day (PUPU)', fontname='Times New Roman',fontsize=18)
plt.xlabel('Time', fontname='Times New Roman',fontsize=18)
plt.ylabel('Number of messages', fontname='Times New Roman',fontsize=18)

sns.set_style('darkgrid')#设置图片为深色背景且有网格线
sns.histplot(df2['hour'],bins=24,kde=True, color='#DC84F3')

plt.xticks(np.arange(0, 25, 1.0),fontname='Times New Roman', fontsize=15)
plt.yticks(fontname='Times New Roman',fontsize=15)

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('chat_time_pupu.png',dpi=100)
plt.show()
```

![下载6](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/81e1c1d2-cb4f-4f8d-bedc-8e3be4094a27)

## **8.对方日内消息分布**

再是对方日内消息分布。

```python
df2['hour'] = pd.to_datetime(df2[df2['IsSender'] == 1]['StrTime']).dt.hour

plt.title('Figure 7: The Distribution of Messages throughout the Day (BOBO)', fontname='Times New Roman',fontsize=18)
plt.xlabel('Time', fontname='Times New Roman',fontsize=18)
plt.ylabel('Number of messages', fontname='Times New Roman',fontsize=18)

sns.set_style('white')#设置图片为深色背景且有网格线
sns.histplot(df2['hour'],bins=24,kde=True, color='#80BCBD')

plt.xticks(np.arange(0, 25, 1.0), fontname='Times New Roman',fontsize=15)
plt.yticks(fontname='Times New Roman',fontsize=15)

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('chat_time_bobo.png',dpi=100)
plt.show()
```

![下载7](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/93f47b77-6d01-43f0-8e9c-94bfb854ed57)

## **9.月度消息分布**

刚刚分析了日内消息分布，再来分析月度消息分布。绘制折线统计图由此得到每一天的消息数量。

```python
import matplotlib.pyplot as plt
from matplotlib.font_manager import FontProperties
import pandas as pd

# 假设 df2 已经定义并包含 'StrTime' 列
# 将 'StrTime' 列转换为 datetime 类型，并设置为索引
df2['Date'] = pd.to_datetime(df2['StrTime'])
df2.set_index('Date', inplace=True)

# 创建一个包含每月统计数据的字典
monthly_counts = {}

# 对2023年2月到7月的 DataFrame 进行处理
for month in range(2, 8):
    month_str = f'2023-{month:02d}'
    month_df = df2.loc[month_str]

    # 按每天统计数量
    daily_count = month_df.resample('D').size()

    # 存储在字典中
    monthly_counts[month_str] = daily_count

# 绘制折线图
plt.figure(figsize=(12, 8))

# 更新标题和标签
labels = ['2023-02', '2023-03', '2023-04', '2023-05', '2023-06', '2023-07']
colors = ['#88AB8E', '#FF9843', '#3468C0', '#D63484', '#402B3A', '#6A4C93']

for idx, (month, count_data) in enumerate(monthly_counts.items()):
    plt.plot(count_data.index.day, count_data.values, marker='o', linestyle='-', color=colors[idx], label=month)

    # 找到最大值和对应的索引
    max_value = count_data.max()
    max_day = count_data.idxmax().day  # 获取最大值对应的日期

    # 在图上标注最大值
    plt.annotate(f'Max: {max_value}', xy=(max_day, max_value), xytext=(max_day + 1.2, max_value + 1),
                 arrowprops=dict(facecolor='black', arrowstyle='->'),
                 fontsize=18, fontname='Times New Roman')

plt.title('Figure: The Number of Messages Distributed Each Month from February 2023 to July 2023', fontname='Times New Roman', fontsize=22)
plt.xlabel('Day', fontname='Times New Roman', fontsize=20)
plt.ylabel('Messages', fontname='Times New Roman', fontsize=20)
plt.xticks(range(1, 32), fontname='Times New Roman', fontsize=15)  # 设置x轴标签
plt.yticks(fontname='Times New Roman', fontsize=15)
font_prop = FontProperties(family='Times New Roman')
plt.legend(labels, loc="best", prop=font_prop)
plt.grid(True, linestyle='solid', linewidth=0.5, color='lightgrey')  # 添加网格线

plt.tight_layout()

fig = plt.gcf()
fig.set_size_inches(15, 8)
fig.savefig('chat_plot_2.png', dpi=100)
plt.show()
```

![下载8](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/3983800b-8f97-40f7-a71f-c9b1ffe6870c)

## **10.总体热力图分析**

接着，我们可以用热力图看看聊天分布的趋势，
同样很直观，颜色越深代表聊天的消息越多。
我们可以按照天数，把每一天的聊天记录作为热力图的一行画出，稍微有些紧凑。

```python
df2['Date'] = pd.to_datetime(df2['StrTime']).dt.date

# 统计每天的聊天数目
daily_counts = df2['Date'].value_counts().reset_index()
daily_counts.columns = ['Date', 'Chat_Count']

# 为了制作热力图，我们可能需要将日期进行重塑以创建一个矩阵。
# 使用pivot_table创建矩阵
heatmap_data = daily_counts.pivot_table(index='Date', values='Chat_Count', aggfunc='sum')

# 使用seaborn绘制热力图
plt.figure(figsize=(14, 10))
sns.heatmap(heatmap_data, cmap="Reds",linewidths=0.5, linecolor='gray',xticklabels=False)

plt.title('Figure 9: Chat Counts Heatmap', fontname='Times New Roman',fontsize=22)
plt.ylabel('Date', fontname='Times New Roman',fontsize=20)
plt.yticks(fontname='Times New Roman')

plt.tight_layout()

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('heatmap_1.png',dpi=100)
plt.show()
```

![下载9](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/06d952f7-bd8f-4893-82b7-9fbd7ec02b8c)

## **11.月度热力图分析**

刚刚绘制的热力图唯一的缺点可能就是不够直观，有一点点紧凑，所以我们可以继续改进，按月划分，然后把热力图的每一列作为月份，把热力图的每一行作为每一月的天数，画出改进后的热力图，这样更加清晰：

```python
df2['Date'] = pd.to_datetime(df2['StrTime'])
df2['Month'] = df2['Date'].dt.month  # 提取月份

# 使用pivot_table创建矩阵，按月份和日期
heatmap_data = df2.pivot_table(index=df2['Date'].dt.day, columns='Month', values='StrTime', aggfunc='count')

# 使用seaborn绘制热力图
sns.heatmap(heatmap_data, cmap="GnBu", linewidths=0.5, linecolor='gray')

plt.title('Figure 10: Chat Counts Heatmap by Month', fontname='Times New Roman',fontsize=22)
plt.xlabel('Month', fontname='Times New Roman',fontsize=20)
plt.ylabel('Day of Month', fontname='Times New Roman',fontsize=20)
plt.xticks(fontname='Times New Roman',fontsize=15)  # 设置x轴标签
plt.yticks(fontname='Times New Roman',fontsize=15)
plt.tight_layout()

fig = plt.gcf()
fig.set_size_inches(15,8)
fig.savefig('heatmap_2.png',dpi=100)
plt.show()
```

![下载10](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/354aad2c-0466-430d-836f-e84cb906c403)

## **12.词云图分析**

在大样本分析中，对于不规则数据类型适合用词云图。
整体思路是：
（1）导入扩展库
（2）引入停用词列表
（3）传入背景图

```python
import numpy as np 
import pandas as pd 
import seaborn as sns
import matplotlib.pyplot as plt
import matplotlib
import chardet
import jieba

from PIL import Image
from collections import Counter
from wordcloud import WordCloud, STOPWORDS, ImageColorGenerator # 词云库
from matplotlib.font_manager import * # 如果想在图上显示中文，需导入这个包
from matplotlib import cm

# 更改了文件路径
df = pd.read_csv(r"/content/drive/My Drive/fj_utf8.csv", sep=',')

# 使用指定的中文字体路径创建词云对象
font_path = 'C:/Windows/Fonts/msyh.ttc'  # 假设你已经下载了微软雅黑字体并知道其路径

# 筛选满足 Type == 1 且 IsSender == 1 的 StrContent
bobo_content = df[(df['Type'] == 1) & (df['IsSender'] == 1)]['StrContent']

# 指定保存的txt文件路径和名称
output_file_path = 'bobo_content.txt'

# 将筛选后的内容保存到txt文件中
bobo_content.to_csv(output_file_path, index=False, header=False, sep='\t')

with open('bobo_content.txt', 'r', encoding='utf-8') as file:
    bobo_text = file.read()

# 加载中文停用词
stopwords_path = "stopwords_cn.txt"
with open(stopwords_path, 'r', encoding='utf-8') as f:
    stopwords_list = [line.strip() for line in f.readlines()]

# 将筛选后的内容分词
bobo_words = jieba.cut(bobo_text)

# 定义词云形状
mask_image_path = "heart_shape.png" # 加载词云图的形状
mask_image = np.array(Image.open(mask_image_path))
img_colors = ImageColorGenerator(mask_image)

# 定义词云参数
wordcloud = WordCloud(
    font_path=font_path,
    min_font_size = 4,
    max_font_size = 100,
    margin = 2,
    scale = 2,
    random_state = 42,
    width=800,
    height=800,
    background_color='white',
    stopwords=stopwords_list,
    mask=mask_image,  # 使用自定义的图片作为词云的形状
    colormap='pink'   # 使用粉色调色板
).generate(' '.join([word for word in bobo_words if word not in stopwords_list]))

wordcloud.recolor(color_func=img_colors)

# 保存生成的词云图片
output_image_path = "bobo_wordcloud.png"
wordcloud.to_file(output_image_path)

# 显示词云
plt.figure(figsize=(40, 40))
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis("off")
plt.show()
```

运行结果这里就不展示了，哈哈哈哈~

# **六、总结**

- 由于我刚刚系统地学习了Python，某些代码片段地结构运用地不是非常得当，在这里诚恳地向大家道歉，也欢迎大家地批评指正。

- 如果大家在复现地过程中遇到了各种各样地问题，建议大家优先百度一下，如果无果可直接在评论区或者私信联系我，知无不言言无不尽。
- 后续如果有时间再更新情感分析之类的模块。
- 谢谢大家的支持！

# **附录**

大家如果有问题，可以搜索获得解答，也可以直接在抖音评论区或者私信提问。
**[抖音ID：dy1mn2hw9tcgv  [昵称：BasicProtein] 点击跳转](https://v.douyin.com/iNDvkKwC/)**
本项目的所有工具以及本教程文档我会同步到个人Github仓库，欢迎关注！
[**Github ID：BasicProtein 点击跳转**](https://github.com/BasicProtein/WeChat-Annual-Report)

![image-20240215175639631](https://github.com/BasicProtein/WeChat-Annual-Report/assets/158468609/515258a7-f040-4cf8-abde-c21163540ed7)

