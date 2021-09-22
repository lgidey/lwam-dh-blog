---
layout: post
title:  "Count and compare words in Gibbon&Smith's text"
date:   2021-09-22 15:51:43 -0400
categories: jekyll update
---
*Python code for counting and sorting words from Gibbon's and Smith's text*

You can find collab code here:
[Count and Sort Words](https://colab.research.google.com/drive/10XYAnH-ZLkQWIex45-LszVp6JHz7XhCC?usp=sharing)


**Import python packages**
```python
import nltk
import urllib.request
from nltk import word_tokenize
from nltk.corpus.reader.plaintext import PlaintextCorpusReader
nltk.download('punkt')
import matplotlib.pyplot as plt
from nltk.corpus import stopwords
nltk.download('stopwords')
from nltk.stem import WordNetLemmatizer
nltk.download('wordnet')
from sklearn.feature_extraction.text import TfidfVectorizer
import pandas as pd
import spacy
import scattertext as st
from IPython.core.display import HTML
from google.colab import files
import re
```


**Input Gibbon's**
```python
def countwords_in_gibbon(fname):


    f = open(fname)
    print()
    #print(fname)
    totwords = 0
    wordlist = {}
    for l in f:
        l = re.sub('<[^>]+>',' ',l)
        l = re.sub('[\.;,:"\(\)]',' ',l)
        words = l.split()

        for foo in words:
            totwords = totwords + 1
            if( foo in wordlist):
                wordlist[foo] = wordlist[foo] + 1
            else:
                wordlist[foo] = 1
    i = 0
    print(totwords)

    for foo in sorted(wordlist,key=wordlist.get,reverse=True):
        if(  not re.search('^[A-Z]',foo) or  foo.lower() in wordlist):
            continue
        if(i> 20):
            continue
        i = i + 1
        print(foo,wordlist[foo],(wordlist[foo]*10000)/totwords)
    return(wordlist)
    f.close()
resl = countwords_in_gibbon('declineandfall-gut.txt')
```


**Output**
```python
1608114
Roman 2171 13.500286671218582
Hist 1412 8.780472031211717
Constantinople 1159 7.207200484542763
Italy 995 6.187372288283044
Constantine 985 6.125187642169648
Christian 836 5.198636415080025
Julian 826 5.136451768966628
Greek 819 5.09292251668725
Christians 792 4.9250239721810765
Justinian 589 3.662675656079109
Latin 559 3.4761217177389163
Goths 533 3.3144416378440833
Egypt 480 2.9848630134430767
Asia 477 2.9662076196090577
Persian 474 2.947552225775038
Europe 471 2.928896831941019
Gothic 471 2.928896831941019
Mahomet 468 2.910241438107
Gaul 453 2.8169644689369036
Theodosius 449 2.792090610491545
Africa 408 2.5371335614266153
```

**Input Smith's**
```python
def countwords_in_smith(fname):


    f = open(fname)
    print()
    #print(fname)
    totwords = 0
    wordlist = {}
    for l in f:
        l = re.sub('<[^>]+>',' ',l)
        l = re.sub('[\.;,:"\(\)]',' ',l)
        words = l.split()

        for foo in words:
            totwords = totwords + 1
            if( foo in wordlist):
                wordlist[foo] = wordlist[foo] + 1
            else:
                wordlist[foo] = 1
    i = 0
    print(totwords)

    for foo in sorted(wordlist,key=wordlist.get,reverse=True):
        if(  not re.search('^[A-Z]',foo) or  foo.lower() in wordlist):
            continue
        if(i> 20):
            continue
        i = i + 1
        print(foo,wordlist[foo],(wordlist[foo]*10000)/totwords)
    return(wordlist)
    f.close()
resl = countwords_in_smith('wealthofnations-gut.txt')
```


**Output**
```python
384899
Europe 404 10.496260057833354
England 402 10.444298374378732
Britain 373 9.690853964286735
France 233 6.053536122463296
America 198 5.144206662007436
Scotland 170 4.416743093642748
English 135 3.507413633186888
British 135 3.507413633186888
London 131 3.4034902662776467
European 112 2.9098542734587514
French 111 2.883873431731441
Indies 102 2.6500458561856486
Spain 95 2.468179964094477
Portugal 95 2.468179964094477
India 85 2.208371546821374
Holland 78 2.026505654730202
Mr 70 1.8186589209117197
Roman 62 1.6108121870932375
China 59 1.5328696619113067
Gutenberg-tm 55 1.4289462950020655
Dutch 53 1.376984611547445
```

**Analysis**
In gibbon's there are above 1 Million words and 'Roman' is ranked the highest with 2171 words
In Gibbons the words with the most frequency such as hist, Christian Italy,
Greek played role in the fall and decline of the the roman empire


In Simth's text we see that the words with the most frequency are
nations with Britain and America leading the wealth of nations
