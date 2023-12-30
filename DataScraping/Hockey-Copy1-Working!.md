```python
from bs4 import BeautifulSoup
import requests

url = "https://www.scrapethissite.com/pages/forms/"

page = requests.get(url)

soup = BeautifulSoup(page.text, "html")
table = soup.find("table")

headers = table.find_all("th")
fheaders = [pi.text.strip() for pi in headers]

import pandas as pd
df = pd.DataFrame(columns = fheaders)

rows = table.find_all("tr")

for elem in rows[1:]:
    nrow = elem.find_all("td")
    frow = [par.text.strip() for par in nrow]
    
    length = len(df)
    df.loc[length] = frow
    
df

#df.to_csv(r'C:\Users\luqma\OneDrive - Dublin City University\2nd Yr\hockey.csv', index = False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Team Name</th>
      <th>Year</th>
      <th>Wins</th>
      <th>Losses</th>
      <th>OT Losses</th>
      <th>Win %</th>
      <th>Goals For (GF)</th>
      <th>Goals Against (GA)</th>
      <th>+ / -</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Boston Bruins</td>
      <td>1990</td>
      <td>44</td>
      <td>24</td>
      <td></td>
      <td>0.55</td>
      <td>299</td>
      <td>264</td>
      <td>35</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Buffalo Sabres</td>
      <td>1990</td>
      <td>31</td>
      <td>30</td>
      <td></td>
      <td>0.388</td>
      <td>292</td>
      <td>278</td>
      <td>14</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Calgary Flames</td>
      <td>1990</td>
      <td>46</td>
      <td>26</td>
      <td></td>
      <td>0.575</td>
      <td>344</td>
      <td>263</td>
      <td>81</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Chicago Blackhawks</td>
      <td>1990</td>
      <td>49</td>
      <td>23</td>
      <td></td>
      <td>0.613</td>
      <td>284</td>
      <td>211</td>
      <td>73</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Detroit Red Wings</td>
      <td>1990</td>
      <td>34</td>
      <td>38</td>
      <td></td>
      <td>0.425</td>
      <td>273</td>
      <td>298</td>
      <td>-25</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Edmonton Oilers</td>
      <td>1990</td>
      <td>37</td>
      <td>37</td>
      <td></td>
      <td>0.463</td>
      <td>272</td>
      <td>272</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Hartford Whalers</td>
      <td>1990</td>
      <td>31</td>
      <td>38</td>
      <td></td>
      <td>0.388</td>
      <td>238</td>
      <td>276</td>
      <td>-38</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Los Angeles Kings</td>
      <td>1990</td>
      <td>46</td>
      <td>24</td>
      <td></td>
      <td>0.575</td>
      <td>340</td>
      <td>254</td>
      <td>86</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Minnesota North Stars</td>
      <td>1990</td>
      <td>27</td>
      <td>39</td>
      <td></td>
      <td>0.338</td>
      <td>256</td>
      <td>266</td>
      <td>-10</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Montreal Canadiens</td>
      <td>1990</td>
      <td>39</td>
      <td>30</td>
      <td></td>
      <td>0.487</td>
      <td>273</td>
      <td>249</td>
      <td>24</td>
    </tr>
    <tr>
      <th>10</th>
      <td>New Jersey Devils</td>
      <td>1990</td>
      <td>32</td>
      <td>33</td>
      <td></td>
      <td>0.4</td>
      <td>272</td>
      <td>264</td>
      <td>8</td>
    </tr>
    <tr>
      <th>11</th>
      <td>New York Islanders</td>
      <td>1990</td>
      <td>25</td>
      <td>45</td>
      <td></td>
      <td>0.312</td>
      <td>223</td>
      <td>290</td>
      <td>-67</td>
    </tr>
    <tr>
      <th>12</th>
      <td>New York Rangers</td>
      <td>1990</td>
      <td>36</td>
      <td>31</td>
      <td></td>
      <td>0.45</td>
      <td>297</td>
      <td>265</td>
      <td>32</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Philadelphia Flyers</td>
      <td>1990</td>
      <td>33</td>
      <td>37</td>
      <td></td>
      <td>0.412</td>
      <td>252</td>
      <td>267</td>
      <td>-15</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Pittsburgh Penguins</td>
      <td>1990</td>
      <td>41</td>
      <td>33</td>
      <td></td>
      <td>0.512</td>
      <td>342</td>
      <td>305</td>
      <td>37</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Quebec Nordiques</td>
      <td>1990</td>
      <td>16</td>
      <td>50</td>
      <td></td>
      <td>0.2</td>
      <td>236</td>
      <td>354</td>
      <td>-118</td>
    </tr>
    <tr>
      <th>16</th>
      <td>St. Louis Blues</td>
      <td>1990</td>
      <td>47</td>
      <td>22</td>
      <td></td>
      <td>0.588</td>
      <td>310</td>
      <td>250</td>
      <td>60</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Toronto Maple Leafs</td>
      <td>1990</td>
      <td>23</td>
      <td>46</td>
      <td></td>
      <td>0.287</td>
      <td>241</td>
      <td>318</td>
      <td>-77</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Vancouver Canucks</td>
      <td>1990</td>
      <td>28</td>
      <td>43</td>
      <td></td>
      <td>0.35</td>
      <td>243</td>
      <td>315</td>
      <td>-72</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Washington Capitals</td>
      <td>1990</td>
      <td>37</td>
      <td>36</td>
      <td></td>
      <td>0.463</td>
      <td>258</td>
      <td>258</td>
      <td>0</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Winnipeg Jets</td>
      <td>1990</td>
      <td>26</td>
      <td>43</td>
      <td></td>
      <td>0.325</td>
      <td>260</td>
      <td>288</td>
      <td>-28</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Boston Bruins</td>
      <td>1991</td>
      <td>36</td>
      <td>32</td>
      <td></td>
      <td>0.45</td>
      <td>270</td>
      <td>275</td>
      <td>-5</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Buffalo Sabres</td>
      <td>1991</td>
      <td>31</td>
      <td>37</td>
      <td></td>
      <td>0.388</td>
      <td>289</td>
      <td>299</td>
      <td>-10</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Calgary Flames</td>
      <td>1991</td>
      <td>31</td>
      <td>37</td>
      <td></td>
      <td>0.388</td>
      <td>296</td>
      <td>305</td>
      <td>-9</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Chicago Blackhawks</td>
      <td>1991</td>
      <td>36</td>
      <td>29</td>
      <td></td>
      <td>0.45</td>
      <td>257</td>
      <td>236</td>
      <td>21</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(df)
```


```python

```
