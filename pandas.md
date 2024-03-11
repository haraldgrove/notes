## Example commands to filter a dataframe from Pandas

```
import numpy as np
import pandas as pd

df = pd.DataFrame({
'name':['Jane','John','Ashley','Mike','Emily','Jack','Catlin'],
'age_sex':['36_F','72_M','87_F','35_M','26_F','41_M','19_F'],
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

## Create new columns from combinations of other columns
```
df['c'] = df[['val','val2']].sum(axis=1)
# equivalently
df['c'] = df['val'] + df['val2']

#  where replaces the value where the condition is false
df['c'] = df[['val','val2']].prod(1).where(df['ctg']=='A', df['val'] / df['val2'])

df[['age', 'sex']] = df['age_sex'].str.split('_', n=1, expand=True)
df['sex'] = df['age_sex'].str.split('_', n=1, expand=True)[1]
df['age'] = df['age_sex'].str.split('_', n=1, expand=True)[0].astype(int)
```

```
def label(row):
    return row['ctg']+'XXX'
df['a'] = df.apply(label, axis=1)
```

```
