국내 교통사고 분석
===
author: 이겸, 전현민, 김강민
date: 21 12월, 2021
width: 1440
height: 900
transition: linear

<p>
  2020년도 국내 교통사고 분석 및 시각화
  <br>
     
  </br>
  지역별 교통사고 비율 / 교통사고 유형
</p>

주제를 선택하게된 이유
===
왜 다양한 주제들중 교통사고 분석을 선택했을까?
  
<font size = "10px">
* 운전면허 취득 가능
* 교통사고 비율에 대한 호기심
* 교통사고 유형에 관한 호기심

</font>













































###유형별 사고 횟수

```r
Sum_number <- accident_value %>% 
  ggplot(aes(x = reorder(large, -sum), y = sum, fill = large)) +
  geom_bar(stat = 'identity', width = 0.4)

Sum_number + scale_colour_gradient() + geom_text(aes(label=sum), vjust=1.6, color="black", position = position_dodge(0.9), size=3)
```

###차대차 종류별 사고 횟수

```r
Cartocar_b <- Cartocar %>% 
  ggplot(aes(x = reorder(middle, -number_accident), y = number_accident, fill = middle)) +
  geom_bar(stat = 'identity', width = 0.4)

Cartocar_b + scale_colour_gradient() + geom_text(aes(label=number_accident), vjust=1.6, color="black", position = position_dodge(0.9), size=3)
```

###차량단독 종류별 사고 횟수

```r
Caronly_b <- Caronly %>% 
  ggplot(aes(x = reorder(middle, -number_accident), y = number_accident, fill = middle)) +
  geom_bar(stat = 'identity', width = 0.4)

Caronly_b + scale_colour_gradient() + geom_text(aes(label=number_accident), vjust=1.6, color="black", position = position_dodge(0.9), size=3)
```

###차대사람 종류별 사고 횟수

```r
Cartopeople_b <- Cartopeople %>% 
  ggplot(aes(x = reorder(middle, -number_accident), y = number_accident, fill = middle)) +
  geom_bar(stat = 'identity', width = 0.4)

Cartopeople_b + scale_colour_gradient() + geom_text(aes(label=number_accident), vjust=1.6, color="black", position = position_dodge(0.9), size=3)
```

###철길건널목 종류별 사고 횟수

```r
CorssRail_b <- CorssRail %>% 
  ggplot(aes(x = reorder(middle, -number_accident), y = number_accident, fill = middle)) +
  geom_bar(stat = 'identity', width = 0.4)

CorssRail_b + scale_colour_gradient() + geom_text(aes(label=number_accident), vjust=1.6, color="black", position = position_dodge(0.9), size=3)
```
###유형별 사망률

```r
death_aver_b <- accident_value %>% 
  ggplot(aes(x = reorder(large, -death_aver), y = death_aver, fill = large)) +
  geom_bar(stat = 'identity', width = 0.4)

death_aver_b + scale_colour_gradient() + geom_text(aes(label=death_aver), vjust=1.6, color="black", position = position_dodge(0.9), size=3)
```

###교통량의 변화

```r
traffic_change <- traffic %>% 
  ggplot(aes(x = year, y = sum, fill = year)) +
  geom_bar(stat = 'identity', width = 1)

traffic_change + scale_colour_gradient() + geom_text(aes(label=sum), vjust=1.6, color="white", position = position_dodge(0.9), size=4)
```


지역별 교통사고 비율
===

서울의 교통사고 비율


```r
Seoul_b <- Seoul %>% 
  ggplot(aes(x = reorder(city_small, -number_accident), y = number_accident, fill = city_small)) +
  geom_bar(stat = 'identity', width = 0.4)

plot(Seoul_b)
```


```r
Seoul_b
```

## Another simple plot_ly




===================
