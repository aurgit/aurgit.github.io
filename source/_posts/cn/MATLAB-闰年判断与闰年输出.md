---
title: MATLAB 闰年判断与闰年输出
author: ezhq
top: false
cover: false
toc: true
mathjax: false
reprintPolicy: cc_by_nc_sa
lang: en
comments: true
date: 2016-09-19 12:00:00
img: https://res.cloudinary.com/imgcave/image/upload/v1592660290/Img/BlogCover/matlab_bqgy7t.png
coverImg: https://res.cloudinary.com/imgcave/image/upload/v1592660290/Img/BlogCover/matlab_bqgy7t.png
password:
summary: 关于MATLAB，关于闰年
categories:
- Dev
tags:
- Dev
- MATLAB
keywords:
updated: 2017-03-09 12:00:00
---

### 代码  
[下列代码仅供参考](https://res.cloudinary.com/imgcave/raw/upload/v1592660511/Img/BlogCover/RunNian_ezhq_avsjgh.m)  

```matlab
%RunNian1900-2016_ezhq
function leapyear
for year = 1900:2016
  sign = 0;
  a = rem(year,400);
  b = rem(year,4);
  c = rem(year,100);
  if a == 0
    sign = sign + 1;
  end
  if b == 0
    sign = sign + 1;
  end
  if c == 0
    sign = sign - 1;
  end
  if sign == 1
    fprintf('%4d \n',year)
  end
end
```
  
### 运行结果  
运行结果截图  
![运行结果截图](https://res.cloudinary.com/imgcave/image/upload/v1592660504/Img/BlogCover/RunNian_ezhq_c2mv6d.jpg) 
