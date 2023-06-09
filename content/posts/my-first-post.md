---
title: "PromQL筆記"
date: 2022-12-19T00:19:35+08:00
craft: true
---

## Background
由於Prometheus對於PromQL的說明實在太過簡陋及缺乏，
這邊想將一些自身學習的經驗做個歸納，將一些基本的語法做個解釋及說明，
並附上一些實務上的需求(會使用到多種語法)，
供大家集思廣益，
若同學們有更好的做法歡迎提出，謝謝！


## 基本語法筆記
官方截至目前原生提供的函數共有45個，簡單歸納可分為：
* 數學函數
* 統計函數
* 時間函數
* 


### abs()
### absent()
### absent_over_time()
### ceil()
### changes()
### clamp()
### clamp_max()
### clamp_min()
### day_of_month()
### day_of_week()
### day_of_year()
### days_in_month()
### delta()
### deriv()
### exp()
### floor()
### histogram_count() and histogram_sum()
### histogram_fraction()
### histogram_quantile()
### holt_winters()
### hour()
### idelta()
### increase()
### irate()
### label_join()
### label_replace()
### ln()
### log2()
### log10()
### minute()
### month()
### predict_linear()
### rate()
### resets()
### round()
### scalar()
### sgn()
### sort()
### sort_desc()
### sqrt()
### time()
### timestamp()
### vector()
### year()
### <aggregation>_over_time()

# 實務需求筆記
## 設置預設值
原生PromQL無法匹配到任意資料時，會回傳我們自訂的常數而非null(原生行為)。  

```promql
prometheus_build_info{job="NONEXISTENT-JOB"} or on() vector(0)
count(prometheus_build_info{job=~"NON-EXISTENT-JOB"}) or on() vector(0)
```

## group_left, group_right比較
## 
