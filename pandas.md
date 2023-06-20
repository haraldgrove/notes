## Example commands to filter a dataframe from Pandas

```
import numpy as np
import pandas as pd

df = pd.DataFrame({
'name':['Jane','John','Ashley','Mike','Emily','Jack','Catlin'],
'ctg':['A','A','C','B','B','C','B'],
'val':[0.43,0.67,0.40,0.91,0.99,0.02,1.00],
'val2':[1,1,7,5,8,7,3]
})
df

df[df.val > 0.5]

df[df.name > 'Jane']

df[(df.val > 0.5) & (df.val2 == 1)]

df[(df.val < 0.5) | (df.val2 == 7)]

names = ['John','Catlin','Mike']
df[df.name.isin(names)]

df[df.name.str.startswith('J')]

df[df.name.str.contains('y')]

df[~df.name.str.startswith('J')]

df.query('ctg == "B" and val > 0.5')

df.nlargest(3, 'val')

df.nsmallest(2, 'val2')

df.iloc[3:5, :] #rows 3 and 4, all columns

df.loc[3:5, :] #rows 3 and 4, all columns NB! treated as strings(?)
```
