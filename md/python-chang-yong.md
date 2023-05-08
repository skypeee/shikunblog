---
title: 'python常用'
date: 2023-05-08 16:10:19
tags: []
published: true
hideInList: false
feature: 
isTop: false
---
# 命令行检索
如果你只需要快速地检查某些内容，则可以在命令行中将代码作为字符串传递
```shell
python -c "print('hi')"
```
# 命令行检索cuda是否可用
```shell
python -c "'import torch;print(torch.cuda.is_available())'"

```