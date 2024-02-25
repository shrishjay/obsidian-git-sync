

|Ram|Syam|Jodu|Modhu|Nina|Tina|==Elon Musk==|
|---|---|---|---|---|---|---|
|4000|5000|6000|7000|7500|8000|10 million|

- **Mean salary** -> **1.4 million (because of the ==outliner== here elon musk)
- **Median** -> 4000 5000 6000 ==7000== 7500 8000 10 million (if the no of data is even then take the average of the two middle points)   4000 5000 6000 |==6500==| 7000 7500 8000

### Percentile :-

|Ram|Syam|Jodu|Modhu|Nina|Tina|==Elon Musk==|
|---|---|---|---|---|---|---|
|4000|5000|6000|7000|7500|8000|10 million|

- 50 percentile of the data is ==7000== i.e of Modhu (i.e 50 percent of the data is less than 7000)
- 25 % ile of the data is (25% of 7 = 1.75 (2 approx)) so 2000 **|** 3000 (we will take the average value between 2 and 3 i.e ==2500==)
- 75 % ile of the data is (75% of 7 = 5.2 (5 approx)) so we will take average value between 5 and 6 i.e ==7725==
- 100 % ile of the data is of elon musk as all the data points are less than him

## Inter Quartile Range :-

==It is the range between 25 th to 75 th percentile.==

### How to remove the outlier?

Its simple just remove the values which is/are more than 99 percentile

Percentile is used in

1. Income dataset (outlier removal)
2. In exam scores (general data analysis)

learn in detail from [https://www.statisticshowto.com/statistics-basics/](/usr/share/joplin-desktop/resources/app.asar/%5Bhttps:/www.statisticshowto.com/statistics-basics/%5D%28https:/www.statisticshowto.com/statistics-basics/%20%22statistics%20basics%22%29 "statistics basics")

### Mode :-

|Name|rob|rafiq|nina|sofia|carolina|john|david|
|---|---|---|---|---|---|---|---|
|Restaurant vote|mexican|mexican|italian|thai|italian|mexican|indian|

Mode means most frequently occuring value in a dataset

here mode is ==mexican==

``` python
import pandas as pd
import numpy as np
df = pd.read_csv("income.csv", names = ["name", "income"], skiprows = [0])
df
df.income.describe()
df.income.quantile(0)
df.income.quantile(0.25, interpolation = "higher")
df.income.quantile(0.5, interpolation = "higher")
df.income.quantile(0.75)
df.income.quantile(1)
percentile_99 = df.income.quantile(0.99)
percentile_99
df[df.income > percentile_99]
df['income'][3] = np.NaN
df.income.mean()
df_new = df.fillna(df.income.mean())
df_new
df_new = df.fillna(df.income.median())
df_new
```

