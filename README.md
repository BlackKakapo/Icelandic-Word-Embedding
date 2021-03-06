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
    
In: sp??nn
Out:
('??tal??a', 0.811682403087616)
('frakkland', 0.7648149728775024)
('grikkland', 0.7166905403137207)
('argent??na', 0.7072430849075317)
('brasil??a', 0.7048637270927429)
('sl??ven??a', 0.6866981983184814)
('r??men??a', 0.6782016158103943)
('andal??s??a', 0.6689508557319641)
('port??gal', 0.6633602380752563)
('madr??d-samf??lagi??', 0.6570574045181274)

In: r??men??a
Out:
('b??lgar??a', 0.787040114402771)
('sl??ven??a', 0.7784465551376343)
('p??lland', 0.7485482692718506)
('belg??a', 0.7436263561248779)
('ungverjaland', 0.7411393523216248)
('sl??vak??a', 0.7309471964836121)
('serb??a', 0.7282808423042297)
('lettland', 0.7272511720657349)
('kr??at??a', 0.716016948223114)
('noregur', 0.7095803022384644)

In: ??sland
Out: 
('noregur', 0.6620221734046936)
('danm??rk', 0.60569828748703)
('finnland', 0.5955715775489807)
('noreg', 0.5871228575706482)
('nor??ur-atlantshafslaxins', 0.581960141658783)
('f??reyjar', 0.5819252133369446)
('kr??at??a', 0.5767964720726013)
('belg??a', 0.5625469088554382)
('eistland', 0.5602771639823914)
('nor??url??ndin', 0.556350827217102)

In: ????islegt
Out:
('yndislegt', 0.8013175129890442)
('geggja??', 0.7791568040847778)
('d??samlegt', 0.762319803237915)
('????islega', 0.7110927104949951)
('jiii', 0.6798439025878906)
('????isleg', 0.6753286719322205)
('ge??veikt', 0.6734864115715027)
('svooooooo', 0.6663821339607239)
('flott', 0.6644969582557678)
('f??nt', 0.6557028889656067)
```
