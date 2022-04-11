# Aqua插件 一 定时提醒1.0

```python
萌新开发的第一个作品, 因为确实有定时提醒的需求, 又不太喜欢闹钟, 就做了这个. 已经有帮到自己和室友很多.
分享给大家, 希望大家能够喜欢, 第一次开发, 水平有限, 欢迎大家批评和建议^
```

```python
TODO
	支持模糊语句 √
	支持任务自动存储, 防止丢失任务 √
    支持汉语数字 (暂时只实现了如"九千九百九十九时50m20S后提醒我手冲"之类的"后"字句)(详情见正则表达式)
	查询任务 √
    删改任务 √
    支持定期任务 在做了...
    ...
```

## 安装插件

![](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/0.png)

## 添加任务

### 一 无命令触发

```python
时间 + 提醒我|[和对跟]我说 + 事件
# 因为无需命令, 为了防止误触发, 所以 提醒我|[和对跟]我说 是必须的
```

![](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/11.png)

![](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/12.png?raw=true)

```python
# 正则表达式 (如下)
```

![image-20220410111148046](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/15.png)

### 二 有命令触发

```python
宣告
时间 + 提醒我|[和对跟]我说 + 事件
# 因为有命令, 不容易误触发, 所以 提醒我|[和对跟]我说 可有可无
```

![image-20220410165236419](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/23.png?raw=true)

```python
# 正则表达式如下
```

![image-20220410111624013](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/25.png?raw=true)

## 查询任务

```python
支持语句:
    契约查询
    查询契约
	最近有什么事吗
    最近有什么事吗?
正则: "(最近有什么事吗\??)|(契约查询)|(查询契约)"
```

![read_tasks0](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/read_tasks0.png)

## 删除任务

```python
支持语句:
    不用提醒我契约13了
	删除13
    忘记13
	忘记契约13
    ...
正则: "(忘记|不用提醒我|删除)(契约)?(?P<task_id>\d+)吧?了?"
```

![delete_task0](https://github.com/Luciferation/Image/blob/master/Image/ImageOfScheduledTask/delete_task0.png)
