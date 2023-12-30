```python
from bs4 import BeautifulSoup
import requests

url = "https://www.worldometers.info/coronavirus/"

page = requests.get(url)

ye = BeautifulSoup(page.text, "html")
table = ye.find_all("table")[1]
headers = table.find_all("th")[:-7]

fheaders = [pi.text.strip() for pi in headers]
fheaders

import pandas as pd

df = pd.DataFrame(columns = fheaders)


row = table.find_all("tr")

for elem in row[1:]:
    yup = elem.find_all("td")
    frow = [nrow.text.strip() for nrow in yup]
    
    length = len(df)
    df.loc[length] = frow
    
print(df)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[4], line 27
         24     frow = [nrow.text.strip() for nrow in yup]
         26     length = len(df)
    ---> 27     df.loc[length] = frow
         29 print(df)
    

    File ~\anaconda3\Lib\site-packages\pandas\core\indexing.py:818, in _LocationIndexer.__setitem__(self, key, value)
        815 self._has_valid_setitem_indexer(key)
        817 iloc = self if self.name == "iloc" else self.obj.iloc
    --> 818 iloc._setitem_with_indexer(indexer, value, self.name)
    

    File ~\anaconda3\Lib\site-packages\pandas\core\indexing.py:1785, in _iLocIndexer._setitem_with_indexer(self, indexer, value, name)
       1782     indexer, missing = convert_missing_indexer(indexer)
       1784     if missing:
    -> 1785         self._setitem_with_indexer_missing(indexer, value)
       1786         return
       1788 if name == "loc":
       1789     # must come after setting of missing
    

    File ~\anaconda3\Lib\site-packages\pandas\core\indexing.py:2160, in _iLocIndexer._setitem_with_indexer_missing(self, indexer, value)
       2157     if is_list_like_indexer(value):
       2158         # must have conforming columns
       2159         if len(value) != len(self.obj.columns):
    -> 2160             raise ValueError("cannot set a row with mismatched columns")
       2162     value = Series(value, index=self.obj.columns, name=indexer)
       2164 if not len(self.obj):
       2165     # We will ignore the existing dtypes instead of using
       2166     #  internals.concat logic
    

    ValueError: cannot set a row with mismatched columns



```python

```


```python

```
