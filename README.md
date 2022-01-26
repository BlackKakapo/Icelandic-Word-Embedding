# Icelandic Word Embedding

These vectors was trained with 3 different methods (CBOW, Skip-Gram, FastText) from Gensim library. The dataset is a bunch of text that was taken from internet (news, comments, blogs etc.).

#

> Please notice I do not claim that these vectors are the best for icelandic language!

#

### About Dataset 
The text is pre processed and cleaned.

- 34.001.430 -  Sentences (One of purpose is the sentence need to be bigger than 35 characters, including the spaces) 
- 509.359.137 -  Words
- 366.181 - Unique words
- 14,98 - AVG number of words in sentence

#

| Method | Size | Min_count | Window | Download | Size | 
| ------ |----- | --------- | ------ | ---- | ---- |
| CBOW | 300 | 20 | 5 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/Ec2KxXdTc6BGmqlz3qWOwbEBXVlovgbDsEajHjRlQHmZJg?e=su8lvu">Download</a> | 770 MB |
| CBOW | 300 | 20 | 15 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/EW9NBIMFHvtJnKBzYr0EGQoBN5ZSMc-f89UwG7ZvXcM3hQ?e=pr5MSp">Download</a> |  770 MB |
| Skip-Gram | 300 | 20 | 5 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/EZapSz0ynWNDkNBqU7mO2nsBJ1w8E0p6CxXdYBQE6NGk6A?e=878XZi">Download</a> |  770 MB |
| Skip-Gram | 300 | 20 | 15 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/EY9obSjS-4FCj2e8CkbsOKkBMWyGTNapzB_g3nf0MdMrNQ?e=LEOzjm">Download</a> |  770 MB |
| FastText (SG) | 300 | 20 | 5 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/EX9vSrfarMFEiapWKQsQzkcBwttb1QsXFhN7qJBNdnH5lw?e=xZwW2p">Download</a> | 2.75 GB |
| FastText (SG) | 300 | 20 | 15 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/ETXN0LesJCdMuout30KScRQBfLuWYCardkbf5Vu70HWWqw?e=14hz7j">Download</a> | 2.75 GB |


#

### Some tests with ICE_SG_300_20_15.model 


```python
from gensim.models import Word2Vec

model = Word2Vec.load('ICE_SG_300_20_15.model')

resultQuery = model.wv.most_similar('**WORD**')

for result in resultQuery:
    print(result)
    
In: spánn
Out:
('ítalía', 0.811682403087616)
('frakkland', 0.7648149728775024)
('grikkland', 0.7166905403137207)
('argentína', 0.7072430849075317)
('brasilía', 0.7048637270927429)
('slóvenía', 0.6866981983184814)
('rúmenía', 0.6782016158103943)
('andalúsía', 0.6689508557319641)
('portúgal', 0.6633602380752563)
('madríd-samfélagið', 0.6570574045181274)

In: rúmenía
Out:
('búlgaría', 0.787040114402771)
('slóvenía', 0.7784465551376343)
('pólland', 0.7485482692718506)
('belgía', 0.7436263561248779)
('ungverjaland', 0.7411393523216248)
('slóvakía', 0.7309471964836121)
('serbía', 0.7282808423042297)
('lettland', 0.7272511720657349)
('króatía', 0.716016948223114)
('noregur', 0.7095803022384644)

In: ísland
Out: 
('noregur', 0.6620221734046936)
('danmörk', 0.60569828748703)
('finnland', 0.5955715775489807)
('noreg', 0.5871228575706482)
('norður-atlantshafslaxins', 0.581960141658783)
('færeyjar', 0.5819252133369446)
('króatía', 0.5767964720726013)
('belgía', 0.5625469088554382)
('eistland', 0.5602771639823914)
('norðurlöndin', 0.556350827217102)

In: æðislegt
Out:
('yndislegt', 0.8013175129890442)
('geggjað', 0.7791568040847778)
('dásamlegt', 0.762319803237915)
('æðislega', 0.7110927104949951)
('jiii', 0.6798439025878906)
('æðisleg', 0.6753286719322205)
('geðveikt', 0.6734864115715027)
('svooooooo', 0.6663821339607239)
('flott', 0.6644969582557678)
('fínt', 0.6557028889656067)
```
