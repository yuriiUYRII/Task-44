import pandas as pd
import random

lst = ['robot'] * 10
lst += ['human'] * 10
random.shuffle(lst)
data = pd.DataFrame({'whoAmI': lst})
data.head()

unique_values = data['whoAmI'].unique()
one_hot_data = pd.DataFrame()
for value in unique_values:
    one_hot_data[value] = (data['whoAmI'] == value).astype(int)
one_hot_data.head()
     
human	robot
0	1	0
1	1	0
2	1	0
3	1	0
4	1	0
