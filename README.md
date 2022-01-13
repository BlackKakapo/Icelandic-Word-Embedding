# Icelandic Word Embedding

These vectors was trained with 3 different methods (CBOW, Skip-Gram, FastText) from Gensim library. The dataset is a bunch of text that was taken from internet (news, comments, blogs etc.).

#

> Please notice I do not claim that these vectors are the best for icelandic language!

#

### About Dataset
The text is pre processed and cleaned.

- 6.010.024 -  Sentences (One of purpose is the sentence need to be bigger than 35 characters, including the spaces) 
- 104.383.513 -  Words
- 138.815 - Unique words
- 17,36 - AVG number of words in sentence

#

| Method | Size | Min_count | Window | Download | Size | 
| ------ |----- | --------- | ------ | ---- | ---- |
| CBOW | 300 | 20 | 5 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/Eeo2DW1Zs1hLrFMEVpOAfmcBFNwbDzZ6lj_iX1a0cDKPJw?e=RAXWtp">Download</a> | 457 MB |
| CBOW | 300 | 20 | 15 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/ERcFWiNOZOhFg-fMaM0Z2soBzNDGVZLG1lknPFkyNiJakg?e=6OtOul">Download</a> |  457 MB |
| Skip-Gram | 300 | 20 | 5 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/Ec08q7oNz5NMnJPRAHO6G0oBmogzgKUSjOmbrSLruo48dw?e=B4nVNM">Download</a> |  457 MB |
| Skip-Gram | 300 | 20 | 15 | <a href="https://utm-my.sharepoint.com/:u:/g/personal/alexandru_petrachi_iis_utm_md/EZJOf2YeOqtFqbZhN1GdopoBeTGqQ7scju-o38Tu9nIqTA?e=wzqJ2R">Download</a> |  457 MB |
| FastText (SG) | 300 | 20 | 5 | <a href="">Download</a> | 457 MB |
| FastText (SG) | 300 | 20 | 15 | <a href="">Download</a> | 457 MB |


#

### Some test with SG_300_20_15 


```python
from gensim.models import Word2Vec

model = Word2Vec.load('ICE_SG_300_20_15.model')

resultQuery = model.wv.most_similar('**WORD**')

for result in resultQuery:
    print(result)
    
In: rúmenía
Out:
('ítalía', 0.8026369214057922)
('frakkland', 0.7354145646095276)
('brasilía', 0.6769333481788635)
('suður-kórea', 0.6618354916572571)
('grikkland', 0.658340334892273)
('holland', 0.6535623073577881)
('búlgaría', 0.6508313417434692)
('malasía', 0.6478225588798523)
('rúmenía', 0.644788384437561)
('ungverjaland', 0.6446587443351746)

In: spánn
Out:
('búlgaría', 0.806666374206543)
('bosnía', 0.7892762422561646)
('svartfjallaland', 0.7860967516899109)
('slóvakía', 0.7753440737724304)
('armenía', 0.7678728103637695)
('hvíta-rússland', 0.7650558352470398)
('moldóva', 0.762825071811676)
('georgía', 0.760909914970398)
('albanía', 0.7547202706336975)
('ungverjaland', 0.749718964099884)

In: ísland
Out: 
('noregur', 0.6396039128303528)
('landið', 0.6065800786018372)
('lettland', 0.6062490940093994)
('bretland', 0.6035197973251343)
('króatía', 0.60196852684021)
('herlaust', 0.6003057956695557)
('albanía', 0.5989615321159363)
('finnland', 0.5932950973510742)
('armenía', 0.5875704288482666)
('eistland', 0.5819126963615417)

In: æðislegt
Out:
('yndislegt', 0.7517484426498413)
('dásamlegt', 0.698316216468811)
('frábært', 0.6924771666526794)
('geggjað', 0.6774240136146545)
('æðislega', 0.6632941365242004)
('gegjað', 0.6567961573600769)
('svooooo', 0.6526150703430176)
('fínt', 0.648186206817627)
('leiðinlegt', 0.6447832584381104)
('rosalega', 0.6400995850563049)
```
