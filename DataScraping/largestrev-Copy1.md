```python
from bs4 import BeautifulSoup
import requests

url = "https://en.wikipedia.org/wiki/List_of_countries_and_dependencies_by_area"

page = requests.get(url)
ok = BeautifulSoup(page.text, "html")
table = ok.find_all("table")[1]
wt = table.find_all("th")
wtt = [elem.text.strip() for elem in wt]

import pandas as pd

df = pd.DataFrame(columns = wtt)
df
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
      <th></th>
      <th>Country / dependency</th>
      <th>Totalin  km2 (mi2)</th>
      <th>Landin  km2 (mi2)</th>
      <th>Waterin  km2 (mi2)</th>
      <th>%water</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
herro = table.find_all("tr")

#for yp in herro:
 #   found = yp.find_all("td")
  #  jel = [lip.text.strip() for lip in found]
   # print(jel)
```


```python

```


```python

```


```python

```


```python



```


```python

```


```python

```


```python

```


```python
from bs4 import BeautifulSoup
import requests

url = "https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue"

page = requests.get(url)
ok = BeautifulSoup(page.text, "html")
table = ok.find("table", class_ = "wikitable sortable")

wth = table.find_all("th")
wwth = [elem.text.strip() for elem in wth]
print(wwth)

```

    ['Rank', 'Name', 'Industry', 'Revenue (USD millions)', 'Revenue growth', 'Employees', 'Headquarters']
    


```python
 import pandas as pd    
```


```python
df = pd.DataFrame(columns = wwth)
df
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
      <th>Rank</th>
      <th>Name</th>
      <th>Industry</th>
      <th>Revenue (USD millions)</th>
      <th>Revenue growth</th>
      <th>Employees</th>
      <th>Headquarters</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python

```


```python

```


```python
import pandas as pde

df = pd.DataFrame(columns = wwth)
df

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
      <th>Rank</th>
      <th>Name</th>
      <th>Industry</th>
      <th>Revenue (USD millions)</th>
      <th>Revenue growth</th>
      <th>Employees</th>
      <th>Headquarters</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
jk = table.find_all("tr")

for step in jk[1:]:
    ik = step.find_all("td")
    lime = [now.text.strip() for now in ik]    
     
        #explanation using pandas

    length = len(df)    #checks the length of index(df) each time it loops
    df.loc[length] = lime    #the length (using loc) is then used to acccess the last row and add "lime"  

df

#df.to_csv(r'C:\Users\luqma\OneDrive - Dublin City University\2nd Yr\fixed.csv', index = False)
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
      <th>Rank</th>
      <th>Name</th>
      <th>Industry</th>
      <th>Revenue (USD millions)</th>
      <th>Revenue growth</th>
      <th>Employees</th>
      <th>Headquarters</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Walmart</td>
      <td>Retail</td>
      <td>611,289</td>
      <td>6.7%</td>
      <td>2,100,000</td>
      <td>Bentonville, Arkansas</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Amazon</td>
      <td>Retail and cloud computing</td>
      <td>513,983</td>
      <td>9.4%</td>
      <td>1,540,000</td>
      <td>Seattle, Washington</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>ExxonMobil</td>
      <td>Petroleum industry</td>
      <td>413,680</td>
      <td>44.8%</td>
      <td>62,000</td>
      <td>Spring, Texas</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Apple</td>
      <td>Electronics industry</td>
      <td>394,328</td>
      <td>7.8%</td>
      <td>164,000</td>
      <td>Cupertino, California</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>UnitedHealth Group</td>
      <td>Healthcare</td>
      <td>324,162</td>
      <td>12.7%</td>
      <td>400,000</td>
      <td>Minnetonka, Minnesota</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>195</th>
      <td>96</td>
      <td>Best Buy</td>
      <td>Retail</td>
      <td>46,298</td>
      <td>10.6%</td>
      <td>71,100</td>
      <td>Richfield, Minnesota</td>
    </tr>
    <tr>
      <th>196</th>
      <td>97</td>
      <td>Bristol-Myers Squibb</td>
      <td>Pharmaceutical industry</td>
      <td>46,159</td>
      <td>0.5%</td>
      <td>34,300</td>
      <td>New York City, New York</td>
    </tr>
    <tr>
      <th>197</th>
      <td>98</td>
      <td>United Airlines</td>
      <td>Airline</td>
      <td>44,955</td>
      <td>82.5%</td>
      <td>92,795</td>
      <td>Chicago, Illinois</td>
    </tr>
    <tr>
      <th>198</th>
      <td>99</td>
      <td>Thermo Fisher Scientific</td>
      <td>Laboratory instruments</td>
      <td>44,915</td>
      <td>14.5%</td>
      <td>130,000</td>
      <td>Waltham, Massachusetts</td>
    </tr>
    <tr>
      <th>199</th>
      <td>100</td>
      <td>Qualcomm</td>
      <td>Technology</td>
      <td>44,200</td>
      <td>31.7%</td>
      <td>51,000</td>
      <td>San Diego, California</td>
    </tr>
  </tbody>
</table>
<p>200 rows × 7 columns</p>
</div>




```python
print(df.head)
```

    <bound method NDFrame.head of     Rank                      Name                    Industry  \
    0      1                   Walmart                      Retail   
    1      2                    Amazon  Retail and cloud computing   
    2      3                ExxonMobil          Petroleum industry   
    3      4                     Apple        Electronics industry   
    4      5        UnitedHealth Group                  Healthcare   
    ..   ...                       ...                         ...   
    195   96                  Best Buy                      Retail   
    196   97      Bristol-Myers Squibb     Pharmaceutical industry   
    197   98           United Airlines                     Airline   
    198   99  Thermo Fisher Scientific      Laboratory instruments   
    199  100                  Qualcomm                  Technology   
    
        Revenue (USD millions) Revenue growth  Employees             Headquarters  
    0                  611,289           6.7%  2,100,000    Bentonville, Arkansas  
    1                  513,983           9.4%  1,540,000      Seattle, Washington  
    2                  413,680          44.8%     62,000            Spring, Texas  
    3                  394,328           7.8%    164,000    Cupertino, California  
    4                  324,162          12.7%    400,000    Minnetonka, Minnesota  
    ..                     ...            ...        ...                      ...  
    195                 46,298          10.6%     71,100     Richfield, Minnesota  
    196                 46,159           0.5%     34,300  New York City, New York  
    197                 44,955          82.5%     92,795        Chicago, Illinois  
    198                 44,915          14.5%    130,000   Waltham, Massachusetts  
    199                 44,200          31.7%     51,000    San Diego, California  
    
    [200 rows x 7 columns]>
    


```python
lmao = table.find_all("tr")

for yu in lmao:
    yu = yu.find_all("td")
    ist = [op.text.strip() for op in yu]    
    print(ist)
```

    []
    ['1', 'Walmart', 'Retail', '611,289', '6.7%', '2,100,000', 'Bentonville, Arkansas']
    ['2', 'Amazon', 'Retail and cloud computing', '513,983', '9.4%', '1,540,000', 'Seattle, Washington']
    ['3', 'ExxonMobil', 'Petroleum industry', '413,680', '44.8%', '62,000', 'Spring, Texas']
    ['4', 'Apple', 'Electronics industry', '394,328', '7.8%', '164,000', 'Cupertino, California']
    ['5', 'UnitedHealth Group', 'Healthcare', '324,162', '12.7%', '400,000', 'Minnetonka, Minnesota']
    ['6', 'CVS Health', 'Healthcare', '322,467', '10.4%', '259,500', 'Woonsocket, Rhode Island']
    ['7', 'Berkshire Hathaway', 'Conglomerate', '302,089', '9.4%', '383,000', 'Omaha, Nebraska']
    ['8', 'Alphabet', 'Technology and Cloud Computing', '282,836', '9.8%', '156,000', 'Mountain View, California']
    ['9', 'McKesson Corporation', 'Health', '276,711', '4.8%', '48,500', 'Irving, Texas']
    ['10', 'Chevron Corporation', 'Petroleum industry', '246,252', '51.6%', '43,846', 'San Ramon, California']
    ['11', 'AmerisourceBergen', 'Pharmaceutical industry', '238,587', '11.5%', '41,500', 'Chesterbrook, Pennsylvania']
    ['12', 'Costco', 'Retail', '226,954', '15.8%', '304,000', 'Issaquah, Washington']
    ['13', 'Microsoft', 'Technology and Cloud Computing', '198,270', '18.0%', '221,000', 'Redmond, Washington']
    ['14', 'Cardinal Health', 'Healthcare', '181,364', '11.6%', '46,035', 'Dublin, Ohio']
    ['15', 'Cigna', 'Health Insurance', '180,516', '3.7%', '70,231', 'Bloomfield, Connecticut']
    ['16', 'Marathon Petroleum', 'Petroleum industry', '180,012', '27.6%', '17,800', 'Findlay, Ohio']
    ['17', 'Phillips 66', 'Petroleum industry', '175,702', '53.0%', '13,000', 'Houston, Texas']
    ['18', 'Valero Energy', 'Petroleum industry', '171,189', '58.0%', '9,743', 'San Antonio, Texas']
    ['19', 'Ford Motor Company', 'Automotive industry', '158,057', '15.9%', '173,000', 'Dearborn, Michigan']
    ['20', 'The Home Depot', 'Retail', '157,403', '4.1%', '471,600', 'Atlanta, Georgia']
    ['21', 'General Motors', 'Automotive industry', '156,735', '23.4%', '167,000', 'Detroit, Michigan']
    ['22', 'Elevance Health', 'Healthcare', '156,595', '13.0%', '102,200', 'Indianapolis, Indiana']
    ['23', 'JPMorgan Chase', 'Financial services', '154,792', '21.7%', '293,723', 'New York City, New York']
    ['24', 'Kroger', 'Retail', '148,258', '7.5%', '430,000', 'Cincinnati, Ohio']
    ['25', 'Centene', 'Healthcare', '144,547', '14.7%', '74,300', 'St. Louis, Missouri']
    ['26', 'Verizon Communications', 'Telecommunications', '136,835', '2.4%', '117,100', 'New York City, New York']
    ['27', 'Walgreens Boots Alliance', 'Pharmaceutical industry', '132,703', '10.7%', '262,500', 'Deerfield, Illinois']
    ['28', 'Fannie Mae', 'Financials', '121,596', '19.7%', '8,000', 'Washington, D.C.']
    ['29', 'Comcast', 'Telecommunications', '121,427', '4.3%', '186,000', 'Philadelphia, Pennsylvania']
    ['30', 'AT&T', 'Conglomerate and Telecomunications', '120,741', '28.5%', '160,700', 'Dallas, Texas']
    ['31', 'Meta Platforms', 'Technology', '116,609', '1.1%', '86,482', 'Menlo Park, California']
    ['32', 'Bank of America', 'Financials', '115,053', '22.6%', '216,823', 'Charlotte, North Carolina']
    ['33', 'Target Corporation', 'Retail', '109,120', '2.9%', '440,000', 'Minneapolis, Minnesota']
    ['34', 'Dell Technologies', 'Technology', '102,301', '4.4%', '133,000', 'Round Rock, Texas']
    ['35', 'Archer Daniels Midland', 'Food industry', '101,556', '19.1%', '41,181', 'Chicago, Illinois']
    ['36', 'Citigroup', 'Financials', '101,078', '26.6%', '238,104', 'New York City, New York']
    ['37', 'United Parcel Service', 'Transportation', '100,338', '3.1%', '404,700', 'Atlanta, Georgia']
    ['38', 'Pfizer', 'Pharmaceutical industry', '100,330', '23.4%', '83,000', 'New York City, New York']
    ['39', "Lowe's", 'Retail', '97,059', '0.8%', '244,500', 'Mooresville, North Carolina']
    ['40', 'Johnson & Johnson', 'Pharmaceutical industry', '94,943', '1.2%', '152,700', 'New Brunswick, New Jersey']
    ['41', 'FedEx', 'Transportation', '93,512', '11.4%', '518,249', 'Memphis, Tennessee']
    ['42', 'Humana', 'Health Insurance', '92,870', '11.8%', '67,100', 'Louisville, Kentucky']
    ['43', 'Energy Transfer Partners', 'Petroleum industry', '89,876', '33.3%', '12,565', 'Dallas, Texas']
    ['44', 'State Farm', 'Financials', '89,328', '8.6%', '60,519', 'Bloomington, Illinois']
    ['45', 'Freddie Mac', 'Financials', '86,717', '31.6%', '7,819', 'McLean, Virginia']
    ['46', 'PepsiCo', 'Beverage', '86,859', '8.7%', '315,000', 'Purchase, New York']
    ['47', 'Wells Fargo', 'Financials', '82,859', '0.5%', '238,000', 'San Francisco, California']
    ['48', 'The Walt Disney Company', 'Media', '82,722', '22.7%', '195,800', 'Burbank, California']
    ['49', 'ConocoPhillips', 'Petroleum industry', '82,156', '69.9%', '9,500', 'Houston, Texas']
    ['50', 'Tesla', 'Automotive and Energy', '81,462', '51.4%', '127,855', 'Austin, Texas']
    ['51', 'Procter & Gamble', 'Consumer products Manufacturing', '80,187', '5.3%', '106,000', 'Cincinnati, Ohio']
    ['52', 'United States Postal Service', 'Logistics', '78,620', '2.0%', '576,000', 'Washington, D.C.']
    ['53', 'Albertsons', 'Retail', '77,650', '8.0%', '198,650', 'Boise, Idaho']
    ['54', 'General Electric', 'Conglomerate', '76,555', '3.2%', '172,000', 'Boston, Massachusetts']
    ['55', 'MetLife', 'Financials', '69,898', '1.7%', '45,000', 'New York City, New York']
    ['56', 'Goldman Sachs', 'Financials', '68,711', '5.7%', '48,500', 'New York City, New York']
    ['57', 'Sysco', 'Food Service', '68,636', '33.8%', '70,510', 'Houston, Texas']
    ['58', 'Bunge Limited', 'Food industry', '67,232', '13.7%', '23,000', 'White Plains, New York']
    ['59', 'RTX Corporation', 'Conglomerate', '67,074', '4.2%', '182,000', 'Arlington County, Virginia']
    ['60', 'Boeing', 'Aerospace and defense', '66,608', '6.9%', '156,000', 'Arlington County, Virginia']
    ['61', 'StoneX Group', 'Financials', '66,036', '55.3%', '305', 'New York City, New York']
    ['62', 'Lockheed Martin', 'Aerospace and Defense', '65,984', '1.6%', '116,000', 'Bethesda, Maryland']
    ['63', 'Morgan Stanley', 'Financials', '65,936', '7.9%', '82,427', 'New York City, New York']
    ['64', 'Intel', 'Technology', '63,054', '20.1%', '131,900', 'Santa Clara, California']
    ['65', 'HP', 'Technology', '62,983', '0.8%', '58,000', 'Palo Alto, California']
    ['66', 'TD Synnex', 'Infotech', '62,344', '97.2%', '28,500', 'Clearwater, Florida']
    ['67', 'IBM', 'Technology and Cloud Computing', '60,530', '16.3%', '303,100', 'Armonk, New York']
    ['68', 'HCA Healthcare', 'Healthcare', '60,233', '2.5%', '250,500', 'Nashville, Tennessee']
    ['69', 'Prudential Financial', 'Financials', '60,050', '15.3%', '39,583', 'Newark, New Jersey']
    ['70', 'Caterpillar', 'Machinery', '59,427', '16.6%', '109,100', 'Deerfield, Illinois']
    ['71', 'Merck & Co.', 'Pharmaceutical industry', '59,283', '15.8%', '68,000', 'Kenilworth, New Jersey']
    ['72', 'World Fuel Services', 'Petroleum industry and Logistics', '59,043', '88.4%', '5,214', 'Miami, Florida']
    ['73', 'New York Life Insurance Company', 'Insurance', '58,445', '14.2%', '15,050', 'New York City, New York']
    ['74', 'Enterprise Products', 'Petroleum industry', '58,186', '42.6%', '7,300', 'Houston, Texas']
    ['75', 'AbbVie', 'Pharmaceutical industry', '58,054', '3.3%', '50,000', 'Lake Bluff, Illinois']
    ['76', 'Plains All American Pipeline', 'Petroleum industry', '57,342', '36.3%', '4,100', 'Houston, Texas']
    ['77', 'Dow Chemical Company', 'Chemical industry', '56,902', '3.5%', '37,800', 'Midland, Michigan']
    ['78', 'AIG', 'Insurance', '56,437', '8.4%', '26,200', 'New York City, New York']
    ['79', 'American Express', 'Financial', '55,625', '27.3%', '77,300', 'New York City, New York']
    ['80', 'Publix', 'Retail', '54,942', '13.5%', '242,000', 'Lakeland, Florida']
    ['81', 'Charter Communications', 'Telecommunications', '54,022', '4.5%', '101,700', 'Stamford, Connecticut']
    ['82', 'Tyson Foods', 'Food Processing', '53,282', '13.2%', '142,000', 'Springdale, Arkansas']
    ['83', 'John Deere', 'Agriculture manufacturing', '52,577', '19.4%', '82,239', 'Moline, Illinois']
    ['84', 'Cisco', 'Telecom Hardware Manufacturing', '51,557', '3.5%', '83,300', 'San Jose, California']
    ['85', 'Nationwide Mutual Insurance Company', 'Financial', '51,450', '8.6%', '24,791', 'Columbus, Ohio']
    ['86', 'Allstate', 'Insurance', '51,412', '3.4%', '54,250', 'Northfield Township, Cook County, Illinois']
    ['87', 'Delta Air Lines', 'Airline', '50,582', '69.2%', '95,000', 'Atlanta, Georgia']
    ['88', 'Liberty Mutual', 'Insurance', '49,956', '3.6%', '50,000', 'Boston, Massachusetts']
    ['89', 'TJX', 'Retail', '49,936', '2.9%', '329,000', 'Framingham, Massachusetts']
    ['90', 'Progressive Corporation', 'Insurance', '49,611', '4.0%', '55,063', 'Mayfield Village, Ohio']
    ['91', 'American Airlines', 'Airline', '48,971', '63.9%', '129,700', 'Fort Worth, Texas']
    ['92', 'CHS', 'Agriculture cooperative', '47,194', '24.3%', '10,014', 'Inver Grove Heights, Minnesota']
    ['93', 'Performance Food Group', 'Food Processing', '47,194', '61.6%', '34,825', 'Richmond, Virginia']
    ['94', 'PBF Energy', 'Petroleum industry', '46,830', '71.8%', '3,616', 'Parsippany–Troy Hills, New Jersey']
    ['95', 'Nike', 'Apparel', '46,710', '4.9%', '79,100', 'Beaverton, Oregon']
    ['96', 'Best Buy', 'Retail', '46,298', '10.6%', '71,100', 'Richfield, Minnesota']
    ['97', 'Bristol-Myers Squibb', 'Pharmaceutical industry', '46,159', '0.5%', '34,300', 'New York City, New York']
    ['98', 'United Airlines', 'Airline', '44,955', '82.5%', '92,795', 'Chicago, Illinois']
    ['99', 'Thermo Fisher Scientific', 'Laboratory instruments', '44,915', '14.5%', '130,000', 'Waltham, Massachusetts']
    ['100', 'Qualcomm', 'Technology', '44,200', '31.7%', '51,000', 'San Diego, California']
    


```python

```


```python
wholetab = table.find_all("tr")

for row in wholetab:
    rowonly= row.find_all("td")
    nlist = [pi.text.split() for pi in rowonly]
    print(nlist)
```

    []
    [['1'], ['Walmart'], ['Retail'], ['611,289'], ['6.7%'], ['2,100,000'], ['Bentonville,', 'Arkansas']]
    [['2'], ['Amazon'], ['Retail', 'and', 'cloud', 'computing'], ['513,983'], ['9.4%'], ['1,540,000'], ['Seattle,', 'Washington']]
    [['3'], ['ExxonMobil'], ['Petroleum', 'industry'], ['413,680'], ['44.8%'], ['62,000'], ['Spring,', 'Texas']]
    [['4'], ['Apple'], ['Electronics', 'industry'], ['394,328'], ['7.8%'], ['164,000'], ['Cupertino,', 'California']]
    [['5'], ['UnitedHealth', 'Group'], ['Healthcare'], ['324,162'], ['12.7%'], ['400,000'], ['Minnetonka,', 'Minnesota']]
    [['6'], ['CVS', 'Health'], ['Healthcare'], ['322,467'], ['10.4%'], ['259,500'], ['Woonsocket,', 'Rhode', 'Island']]
    [['7'], ['Berkshire', 'Hathaway'], ['Conglomerate'], ['302,089'], ['9.4%'], ['383,000'], ['Omaha,', 'Nebraska']]
    [['8'], ['Alphabet'], ['Technology', 'and', 'Cloud', 'Computing'], ['282,836'], ['9.8%'], ['156,000'], ['Mountain', 'View,', 'California']]
    [['9'], ['McKesson', 'Corporation'], ['Health'], ['276,711'], ['4.8%'], ['48,500'], ['Irving,', 'Texas']]
    [['10'], ['Chevron', 'Corporation'], ['Petroleum', 'industry'], ['246,252'], ['51.6%'], ['43,846'], ['San', 'Ramon,', 'California']]
    [['11'], ['AmerisourceBergen'], ['Pharmaceutical', 'industry'], ['238,587'], ['11.5%'], ['41,500'], ['Chesterbrook,', 'Pennsylvania']]
    [['12'], ['Costco'], ['Retail'], ['226,954'], ['15.8%'], ['304,000'], ['Issaquah,', 'Washington']]
    [['13'], ['Microsoft'], ['Technology', 'and', 'Cloud', 'Computing'], ['198,270'], ['18.0%'], ['221,000'], ['Redmond,', 'Washington']]
    [['14'], ['Cardinal', 'Health'], ['Healthcare'], ['181,364'], ['11.6%'], ['46,035'], ['Dublin,', 'Ohio']]
    [['15'], ['Cigna'], ['Health', 'Insurance'], ['180,516'], ['3.7%'], ['70,231'], ['Bloomfield,', 'Connecticut']]
    [['16'], ['Marathon', 'Petroleum'], ['Petroleum', 'industry'], ['180,012'], ['27.6%'], ['17,800'], ['Findlay,', 'Ohio']]
    [['17'], ['Phillips', '66'], ['Petroleum', 'industry'], ['175,702'], ['53.0%'], ['13,000'], ['Houston,', 'Texas']]
    [['18'], ['Valero', 'Energy'], ['Petroleum', 'industry'], ['171,189'], ['58.0%'], ['9,743'], ['San', 'Antonio,', 'Texas']]
    [['19'], ['Ford', 'Motor', 'Company'], ['Automotive', 'industry'], ['158,057'], ['15.9%'], ['173,000'], ['Dearborn,', 'Michigan']]
    [['20'], ['The', 'Home', 'Depot'], ['Retail'], ['157,403'], ['4.1%'], ['471,600'], ['Atlanta,', 'Georgia']]
    [['21'], ['General', 'Motors'], ['Automotive', 'industry'], ['156,735'], ['23.4%'], ['167,000'], ['Detroit,', 'Michigan']]
    [['22'], ['Elevance', 'Health'], ['Healthcare'], ['156,595'], ['13.0%'], ['102,200'], ['Indianapolis,', 'Indiana']]
    [['23'], ['JPMorgan', 'Chase'], ['Financial', 'services'], ['154,792'], ['21.7%'], ['293,723'], ['New', 'York', 'City,', 'New', 'York']]
    [['24'], ['Kroger'], ['Retail'], ['148,258'], ['7.5%'], ['430,000'], ['Cincinnati,', 'Ohio']]
    [['25'], ['Centene'], ['Healthcare'], ['144,547'], ['14.7%'], ['74,300'], ['St.', 'Louis,', 'Missouri']]
    [['26'], ['Verizon', 'Communications'], ['Telecommunications'], ['136,835'], ['2.4%'], ['117,100'], ['New', 'York', 'City,', 'New', 'York']]
    [['27'], ['Walgreens', 'Boots', 'Alliance'], ['Pharmaceutical', 'industry'], ['132,703'], ['10.7%'], ['262,500'], ['Deerfield,', 'Illinois']]
    [['28'], ['Fannie', 'Mae'], ['Financials'], ['121,596'], ['19.7%'], ['8,000'], ['Washington,', 'D.C.']]
    [['29'], ['Comcast'], ['Telecommunications'], ['121,427'], ['4.3%'], ['186,000'], ['Philadelphia,', 'Pennsylvania']]
    [['30'], ['AT&T'], ['Conglomerate', 'and', 'Telecomunications'], ['120,741'], ['28.5%'], ['160,700'], ['Dallas,', 'Texas']]
    [['31'], ['Meta', 'Platforms'], ['Technology'], ['116,609'], ['1.1%'], ['86,482'], ['Menlo', 'Park,', 'California']]
    [['32'], ['Bank', 'of', 'America'], ['Financials'], ['115,053'], ['22.6%'], ['216,823'], ['Charlotte,', 'North', 'Carolina']]
    [['33'], ['Target', 'Corporation'], ['Retail'], ['109,120'], ['2.9%'], ['440,000'], ['Minneapolis,', 'Minnesota']]
    [['34'], ['Dell', 'Technologies'], ['Technology'], ['102,301'], ['4.4%'], ['133,000'], ['Round', 'Rock,', 'Texas']]
    [['35'], ['Archer', 'Daniels', 'Midland'], ['Food', 'industry'], ['101,556'], ['19.1%'], ['41,181'], ['Chicago,', 'Illinois']]
    [['36'], ['Citigroup'], ['Financials'], ['101,078'], ['26.6%'], ['238,104'], ['New', 'York', 'City,', 'New', 'York']]
    [['37'], ['United', 'Parcel', 'Service'], ['Transportation'], ['100,338'], ['3.1%'], ['404,700'], ['Atlanta,', 'Georgia']]
    [['38'], ['Pfizer'], ['Pharmaceutical', 'industry'], ['100,330'], ['23.4%'], ['83,000'], ['New', 'York', 'City,', 'New', 'York']]
    [['39'], ["Lowe's"], ['Retail'], ['97,059'], ['0.8%'], ['244,500'], ['Mooresville,', 'North', 'Carolina']]
    [['40'], ['Johnson', '&', 'Johnson'], ['Pharmaceutical', 'industry'], ['94,943'], ['1.2%'], ['152,700'], ['New', 'Brunswick,', 'New', 'Jersey']]
    [['41'], ['FedEx'], ['Transportation'], ['93,512'], ['11.4%'], ['518,249'], ['Memphis,', 'Tennessee']]
    [['42'], ['Humana'], ['Health', 'Insurance'], ['92,870'], ['11.8%'], ['67,100'], ['Louisville,', 'Kentucky']]
    [['43'], ['Energy', 'Transfer', 'Partners'], ['Petroleum', 'industry'], ['89,876'], ['33.3%'], ['12,565'], ['Dallas,', 'Texas']]
    [['44'], ['State', 'Farm'], ['Financials'], ['89,328'], ['8.6%'], ['60,519'], ['Bloomington,', 'Illinois']]
    [['45'], ['Freddie', 'Mac'], ['Financials'], ['86,717'], ['31.6%'], ['7,819'], ['McLean,', 'Virginia']]
    [['46'], ['PepsiCo'], ['Beverage'], ['86,859'], ['8.7%'], ['315,000'], ['Purchase,', 'New', 'York']]
    [['47'], ['Wells', 'Fargo'], ['Financials'], ['82,859'], ['0.5%'], ['238,000'], ['San', 'Francisco,', 'California']]
    [['48'], ['The', 'Walt', 'Disney', 'Company'], ['Media'], ['82,722'], ['22.7%'], ['195,800'], ['Burbank,', 'California']]
    [['49'], ['ConocoPhillips'], ['Petroleum', 'industry'], ['82,156'], ['69.9%'], ['9,500'], ['Houston,', 'Texas']]
    [['50'], ['Tesla'], ['Automotive', 'and', 'Energy'], ['81,462'], ['51.4%'], ['127,855'], ['Austin,', 'Texas']]
    [['51'], ['Procter', '&', 'Gamble'], ['Consumer', 'products', 'Manufacturing'], ['80,187'], ['5.3%'], ['106,000'], ['Cincinnati,', 'Ohio']]
    [['52'], ['United', 'States', 'Postal', 'Service'], ['Logistics'], ['78,620'], ['2.0%'], ['576,000'], ['Washington,', 'D.C.']]
    [['53'], ['Albertsons'], ['Retail'], ['77,650'], ['8.0%'], ['198,650'], ['Boise,', 'Idaho']]
    [['54'], ['General', 'Electric'], ['Conglomerate'], ['76,555'], ['3.2%'], ['172,000'], ['Boston,', 'Massachusetts']]
    [['55'], ['MetLife'], ['Financials'], ['69,898'], ['1.7%'], ['45,000'], ['New', 'York', 'City,', 'New', 'York']]
    [['56'], ['Goldman', 'Sachs'], ['Financials'], ['68,711'], ['5.7%'], ['48,500'], ['New', 'York', 'City,', 'New', 'York']]
    [['57'], ['Sysco'], ['Food', 'Service'], ['68,636'], ['33.8%'], ['70,510'], ['Houston,', 'Texas']]
    [['58'], ['Bunge', 'Limited'], ['Food', 'industry'], ['67,232'], ['13.7%'], ['23,000'], ['White', 'Plains,', 'New', 'York']]
    [['59'], ['RTX', 'Corporation'], ['Conglomerate'], ['67,074'], ['4.2%'], ['182,000'], ['Arlington', 'County,', 'Virginia']]
    [['60'], ['Boeing'], ['Aerospace', 'and', 'defense'], ['66,608'], ['6.9%'], ['156,000'], ['Arlington', 'County,', 'Virginia']]
    [['61'], ['StoneX', 'Group'], ['Financials'], ['66,036'], ['55.3%'], ['305'], ['New', 'York', 'City,', 'New', 'York']]
    [['62'], ['Lockheed', 'Martin'], ['Aerospace', 'and', 'Defense'], ['65,984'], ['1.6%'], ['116,000'], ['Bethesda,', 'Maryland']]
    [['63'], ['Morgan', 'Stanley'], ['Financials'], ['65,936'], ['7.9%'], ['82,427'], ['New', 'York', 'City,', 'New', 'York']]
    [['64'], ['Intel'], ['Technology'], ['63,054'], ['20.1%'], ['131,900'], ['Santa', 'Clara,', 'California']]
    [['65'], ['HP'], ['Technology'], ['62,983'], ['0.8%'], ['58,000'], ['Palo', 'Alto,', 'California']]
    [['66'], ['TD', 'Synnex'], ['Infotech'], ['62,344'], ['97.2%'], ['28,500'], ['Clearwater,', 'Florida']]
    [['67'], ['IBM'], ['Technology', 'and', 'Cloud', 'Computing'], ['60,530'], ['16.3%'], ['303,100'], ['Armonk,', 'New', 'York']]
    [['68'], ['HCA', 'Healthcare'], ['Healthcare'], ['60,233'], ['2.5%'], ['250,500'], ['Nashville,', 'Tennessee']]
    [['69'], ['Prudential', 'Financial'], ['Financials'], ['60,050'], ['15.3%'], ['39,583'], ['Newark,', 'New', 'Jersey']]
    [['70'], ['Caterpillar'], ['Machinery'], ['59,427'], ['16.6%'], ['109,100'], ['Deerfield,', 'Illinois']]
    [['71'], ['Merck', '&', 'Co.'], ['Pharmaceutical', 'industry'], ['59,283'], ['15.8%'], ['68,000'], ['Kenilworth,', 'New', 'Jersey']]
    [['72'], ['World', 'Fuel', 'Services'], ['Petroleum', 'industry', 'and', 'Logistics'], ['59,043'], ['88.4%'], ['5,214'], ['Miami,', 'Florida']]
    [['73'], ['New', 'York', 'Life', 'Insurance', 'Company'], ['Insurance'], ['58,445'], ['14.2%'], ['15,050'], ['New', 'York', 'City,', 'New', 'York']]
    [['74'], ['Enterprise', 'Products'], ['Petroleum', 'industry'], ['58,186'], ['42.6%'], ['7,300'], ['Houston,', 'Texas']]
    [['75'], ['AbbVie'], ['Pharmaceutical', 'industry'], ['58,054'], ['3.3%'], ['50,000'], ['Lake', 'Bluff,', 'Illinois']]
    [['76'], ['Plains', 'All', 'American', 'Pipeline'], ['Petroleum', 'industry'], ['57,342'], ['36.3%'], ['4,100'], ['Houston,', 'Texas']]
    [['77'], ['Dow', 'Chemical', 'Company'], ['Chemical', 'industry'], ['56,902'], ['3.5%'], ['37,800'], ['Midland,', 'Michigan']]
    [['78'], ['AIG'], ['Insurance'], ['56,437'], ['8.4%'], ['26,200'], ['New', 'York', 'City,', 'New', 'York']]
    [['79'], ['American', 'Express'], ['Financial'], ['55,625'], ['27.3%'], ['77,300'], ['New', 'York', 'City,', 'New', 'York']]
    [['80'], ['Publix'], ['Retail'], ['54,942'], ['13.5%'], ['242,000'], ['Lakeland,', 'Florida']]
    [['81'], ['Charter', 'Communications'], ['Telecommunications'], ['54,022'], ['4.5%'], ['101,700'], ['Stamford,', 'Connecticut']]
    [['82'], ['Tyson', 'Foods'], ['Food', 'Processing'], ['53,282'], ['13.2%'], ['142,000'], ['Springdale,', 'Arkansas']]
    [['83'], ['John', 'Deere'], ['Agriculture', 'manufacturing'], ['52,577'], ['19.4%'], ['82,239'], ['Moline,', 'Illinois']]
    [['84'], ['Cisco'], ['Telecom', 'Hardware', 'Manufacturing'], ['51,557'], ['3.5%'], ['83,300'], ['San', 'Jose,', 'California']]
    [['85'], ['Nationwide', 'Mutual', 'Insurance', 'Company'], ['Financial'], ['51,450'], ['8.6%'], ['24,791'], ['Columbus,', 'Ohio']]
    [['86'], ['Allstate'], ['Insurance'], ['51,412'], ['3.4%'], ['54,250'], ['Northfield', 'Township,', 'Cook', 'County,', 'Illinois']]
    [['87'], ['Delta', 'Air', 'Lines'], ['Airline'], ['50,582'], ['69.2%'], ['95,000'], ['Atlanta,', 'Georgia']]
    [['88'], ['Liberty', 'Mutual'], ['Insurance'], ['49,956'], ['3.6%'], ['50,000'], ['Boston,', 'Massachusetts']]
    [['89'], ['TJX'], ['Retail'], ['49,936'], ['2.9%'], ['329,000'], ['Framingham,', 'Massachusetts']]
    [['90'], ['Progressive', 'Corporation'], ['Insurance'], ['49,611'], ['4.0%'], ['55,063'], ['Mayfield', 'Village,', 'Ohio']]
    [['91'], ['American', 'Airlines'], ['Airline'], ['48,971'], ['63.9%'], ['129,700'], ['Fort', 'Worth,', 'Texas']]
    [['92'], ['CHS'], ['Agriculture', 'cooperative'], ['47,194'], ['24.3%'], ['10,014'], ['Inver', 'Grove', 'Heights,', 'Minnesota']]
    [['93'], ['Performance', 'Food', 'Group'], ['Food', 'Processing'], ['47,194'], ['61.6%'], ['34,825'], ['Richmond,', 'Virginia']]
    [['94'], ['PBF', 'Energy'], ['Petroleum', 'industry'], ['46,830'], ['71.8%'], ['3,616'], ['Parsippany–Troy', 'Hills,', 'New', 'Jersey']]
    [['95'], ['Nike'], ['Apparel'], ['46,710'], ['4.9%'], ['79,100'], ['Beaverton,', 'Oregon']]
    [['96'], ['Best', 'Buy'], ['Retail'], ['46,298'], ['10.6%'], ['71,100'], ['Richfield,', 'Minnesota']]
    [['97'], ['Bristol-Myers', 'Squibb'], ['Pharmaceutical', 'industry'], ['46,159'], ['0.5%'], ['34,300'], ['New', 'York', 'City,', 'New', 'York']]
    [['98'], ['United', 'Airlines'], ['Airline'], ['44,955'], ['82.5%'], ['92,795'], ['Chicago,', 'Illinois']]
    [['99'], ['Thermo', 'Fisher', 'Scientific'], ['Laboratory', 'instruments'], ['44,915'], ['14.5%'], ['130,000'], ['Waltham,', 'Massachusetts']]
    [['100'], ['Qualcomm'], ['Technology'], ['44,200'], ['31.7%'], ['51,000'], ['San', 'Diego,', 'California']]
    


```python

```


```python

```


```python

```


```python

```


```python

```
