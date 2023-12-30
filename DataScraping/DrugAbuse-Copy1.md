```python
from bs4 import BeautifulSoup
import requests
import pandas as pd


url = "https://en.wikipedia.org/wiki/Substance_abuse"

page = requests.get(url)

soup = BeautifulSoup(page.text, "html")

hello = soup.find_all("table")[2]

head = hello.find_all("th")
fhead = [new.text.strip() for new in head]
fhead = fhead[:-1]

df = pd.DataFrame(columns = fhead)
df


row = hello.find_all("tr")


list = []
for elem in row[1:-1]:
    nrow = elem.find_all("td")
    frow = [pi.text.strip() for pi in nrow]
    #(frow)

    length = len(df)
    df.loc[length] = frow

print(df)

#df.to_csv(r'C:\Users\luqma\OneDrive - Dublin City University\2nd Yr\DrugAbuse.csv', index = False)


```

                     Drug               Drug class Physicalharm  \
    0     Methamphetamine            CNS stimulant         3.00   
    1              Heroin                   Opioid         2.78   
    2             Cocaine            CNS stimulant         2.33   
    3        Barbiturates           CNS depressant         2.23   
    4           Methadone                   Opioid         1.86   
    5             Alcohol           CNS depressant         1.40   
    6            Ketamine  Dissociative anesthetic         2.00   
    7     Benzodiazepines           Benzodiazepine         1.63   
    8         Amphetamine            CNS stimulant         1.81   
    9             Tobacco                  Tobacco         1.24   
    10      Buprenorphine                   Opioid         1.60   
    11           Cannabis              Cannabinoid         0.99   
    12      Solvent drugs                 Inhalant         1.28   
    13              4-MTA            Designer SSRA         1.44   
    14                LSD              Psychedelic         1.13   
    15    Methylphenidate            CNS stimulant         1.32   
    16  Anabolic steroids         Anabolic steroid         1.45   
    17                GHB         Neurotransmitter         0.86   
    18            Ecstasy   Empathogenic stimulant         1.05   
    19     Alkyl nitrites                 Inhalant         0.93   
    20               Khat            CNS stimulant         0.50   
    
       Dependenceliability Socialharm Avg.harm  
    0                 2.80       2.72     2.92  
    1                 3.00       2.54     2.77  
    2                 2.39       2.17     2.30  
    3                 2.01       2.00     2.08  
    4                 2.08       1.87     1.94  
    5                 1.93       2.21     1.85  
    6                 1.54       1.69     1.74  
    7                 1.83       1.65     1.70  
    8                 1.67       1.50     1.66  
    9                 2.21       1.42     1.62  
    10                1.64       1.49     1.58  
    11                1.51       1.50     1.33  
    12                1.01       1.52     1.27  
    13                1.30       1.06     1.27  
    14                1.23       1.32     1.23  
    15                1.25       0.97     1.18  
    16                0.88       1.13     1.15  
    17                1.19       1.30     1.12  
    18                1.13       1.09     1.09  
    19                0.87       0.97     0.92  
    20                1.04       0.85     0.80  
    


```python

```


```python

```


```python

```
