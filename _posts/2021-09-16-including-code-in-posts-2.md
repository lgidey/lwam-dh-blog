---
layout: post
title:  "Including code in your posts part 2"
date:   2021-09-16 15:51:43 -0400
categories: jekyll update
---
Another option to include code in your posts is to save a Jupyter or Colab notebook as a .md file and then just attach the usual header like you would any other blog post.

You may want to add "Input" and "Output" in between code blocks as I have done here

**Thanks to Peter Nadel for this example**

**Input**
```python
import requests
import pandas as pd
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.decomposition import NMF
from bs4 import BeautifulSoup
import seaborn as sns
```

**Input**
```python
response = requests.get("https://www.ccel.org/g/gibbon/decline/volume1/index.htm")
```

**Input**
```python
html_string = response.text
print(html_string)
```
**Output (which is being read as html)**

    <!DOCTYPE HTML>
    <HTML>
    <HEAD>
    <META charset="utf-8">
    <!-- Thursday, 24 July 2014 colours -->
    <!-- Tuesday, 1 October 2013 html 5 -->
    <!-- Monday, 6 September 2010 refine layout -->
    <!-- Sunday, 27 January 2008 add css -->
    <!-- Tuesday, 2 December 2003 For netscape-->
    <!-- Thursday, 7 March 2002 Tag title-->
    <!-- Thursday, 19 April 2001 Extend Scope-->
    <!--  Complete Removal of  summaries -->
    <!-- Wednesday, 24 January 2001 remove summary from 11-20-->
    <!-- Use Meta Tags, change civilization to Study-->
    <!-- Wednesday, 29 September 1999 Clarify volumes-->
    <!-- Amended Tuesday, 1 December 1998 for Virginia Uni-->
    <!-- Amended 8th September to amend wording of Title-->
    <TITLE> Fall of the Roman Empire in the West by  Edward Gibbon</TITLE>
    <meta name="description" content="The Fall In The West; first part of the 'History Of The Decline And Fall Of The Roman Empire' by Gibbon">
    <meta name="keywords" content="fall,in,the,west,decline,study,gibbon,antonines,barbarians,huns,christianity,persecution,of,heresy,julian,paganism,constantinople,persia,germany,constantine,final,division">
    <Meta name="author" content="Edward Gibbon">
    <style type="text/css">
    body {background-color:#FFFFFF; color:#000000}
    p { margin: 1.5ex 2% }
    p.cite {margin: 1.5ex 5%;font-family:arial;text-align:left}
    p.off {margin: 1ex 3%;font-family:"times new roman"}
    p.offset {font-family:arial;margin-left:5%;margin-right:5%}
    blockquote {margin: .5ex 4%;font-family:"courier new"}
    h1 {font-family:times new roman;font-size:11pt;text-align:center;font-weight:normal;margin-bottom:1ex;margin-top:.5ex}
    h1:first-line {font-weight:bold;font-size:14pt;font-family:arial}
    em {font-family:times new roman;font-style:normal;font-size:12pt}
    em.on {font-family:courier new;font-style:normal}
    b {font-family:arial}
    td.ok {background-color:#FFFFCC}
    th.ok {background-color:#FFFFCC;width:20%}
    abbr {background-color:#F0F0F0}
    a:link {text-decoration:underline; color:blue}
    a:visited {text-decoration:underline; color:#AAADEA} 
    a:hover {text-decoration:underline; color: green}
    a:active {text-decoration:underline; color:purple}
    th {border:thin solid gray;margin:.5ex 0 .5em 0;text-align:center;padding:1ex 0%}
    td {border:thin solid gray;margin:.5ex 1% .5em 15%;text-align:left;padding:1.2ex 1% 1.2ex 5%}
    table {border-collapse:collapse}
    tr.ok {background:#FFFFCC}
    </style>
    </head>
    <table style="background:#FFFFF2;margin:1em auto;width:90%; font-family:arial">
    <TR style="background:#ADEADA;font-size:x-large;text-align:center">
    <Th>
    Fall Of The Roman Empire In The West<br><small>By <a href="http://www.ourcivilisation.com/gibbon.htm">Edward Gibbon</a></small></th></tr>
    <tr style="background-color:#FFFFFF;font-size:medium">
    <Td style="text-align:center;padding:1ex 0">Originally Issued as 3 Volumes:
      <B>1</b>&#8212;Chapters 1-16 (1776),&nbsp;
     <abbr style="background:#FFFFCC">&nbsp;<b>2</b>&#8212;Chapters 17-26 (1781) , &nbsp;</abbr>  &nbsp;  <b>3</b>&#8212;Chapters 27-38 (1781).
    </td></tr>
    <tr><td style="padding:0;width:100%;height:22em">
    
    <table style="height:100%;width:18%;padding:0;float:left">
    <tr><th colspan=2 style="background-color:#ADEADA">The Antonines</th></tr>
    <tr> <th style="width:15%;background:#ADEADA"><a href="chap1.htm">1</a></th><td><a href="cntnt1.htm" title=" The extent and military force of the Roman empire, in the age of the Antonines">Age</a></td></tr>
    <tr> <th style="background:#ADEADA"><a href="chap2.htm" >2</a></th><td><a href="cntnt2.htm" title="The Union and Internal Prosperity of the Roman Empire in the Age of the Antonines">Prosperity</a></td></tr>
    <tr> <th style="background:#ADEADA"><a href="chap3.htm">3</a></th>
    <td><a href="cntnt3.htm" title="the Constitution of the Roman Empire in the Age of the Antonines">Constitution</a></td></tr>
    <tr><th><a href="chap4.htm">4</a></th><td>AD <a href="cntnt4.htm">180-193</a></td></tr>
    <tr><th><a href="chap5.htm">5</a></th><td>AD <a href="cntnt5.htm">193-197</a></td></tr>
    <tr><th><a href="chap6.htm">6</a></th><td>AD <a href="cntnt6.htm">208-235</a></td></tr>
    <tr><th><a href="chap7.htm">7</a></th><td>AD <a href="cntnt7.htm">235-248</a></td></tr>
    <tr><th><a href="chap8.htm">8</a></th><td><a href="cntnt8.htm">Persia</a></td></tr>
    </table> 
    <table style="height:100%;width:19%;padding:0;float:left">
    <tr><th style="width:19%"><a href="chap9.htm" title="The state of Germany till the invasion of the Barbarians, in the time of the emperor Decius">9</a></th><td><a href="cntnt9.htm">Germany</a></td></tr>
    <tr><th><a href="chap10.htm" title="The emperors Decius, Gallus, Aemilianus,Valerian and Gallienus">10</a></th><td>AD <a href="cntnt10.htm">248-260</a></td></tr>
    <tr><th><a href="chap11.htm">11</a></th><td>AD <a href="cntnt11.htm">268-275</a></td></tr>
    <tr><th><a href="chap12.htm">12</a></th><td>AD <a href="cntnt12.htm">275-285</a></td></tr>
    <tr><th><a href="chap13.htm">13</a></th><td>AD <a href="cntnt13.htm">285-313</a></td></tr>
    <tr><th><a href="chap14.htm">14</a></th><td>AD <a href="cntnt14.htm">305-324</a></td></tr>
    <tr><th colspan=2 style="background-color:#ADEADA">Christianity</th></tr>
    <tr> <th style="background:#ADEADA"><a href="chap15.htm">15</a></th><td title="The progress of the Christian religion"><a href="cntnt15.htm">Progress</a></td></tr>
    <tr> <th style="background:#ADEADA"><a href="chap16.htm">16</a></th><td><a href="cntnt16.htm" title="Conduct of the Roman government towards the Christians">Official</a> Reaction</td></tr>
    </table>
    <table style="height:100%;width:21%;padding:0;float:left">
    
    <tr class="ok"><th style="width:19%"><a href="chap17.htm">17</a></th><td><a href="cntnt17.htm">Constantinople</a></td></tr>
    <tr class="ok"><th><a href="chap18.htm">18</a></th><td>AD <a href="cntnt18.htm">324-353</a></td></tr>
    <tr class="ok"><th><a href="chap19.htm">19</a></th><td>AD <a href="cntnt19.htm">351-359</a></td></tr>
    <tr class="ok"><th><a href="chap20.htm">20</a></th><td>AD <a href="cntnt20.htm">306-438</a></td></tr>
    <tr class="ok"><th><a href="chap21.htm">21</a></th><td><a href="cntnt21.htm">Persecution</a> of Heresy </td></tr>
    <tr><th colspan=2 style="background-color:#ADEADA">Julian</th></tr>
    <tr class="ok"><th style="background:#ADEADA"><a href="chap22.htm">22</a></th><td><a href="cntnt22.htm">Rise</a></td></tr>
    <tr class="ok">  <th style="background:#ADEADA"><a href="chap23.htm">23</a></th><td><a href="cntnt23.htm">Religion</a></td></tr>
    <tr class="ok"> <th style="background:#ADEADA"><a href="chap24.htm">24</a></th><td><a href="cntnt24.htm">Death</a></td></tr>
    </table>
    <table style="height:100%;width:22%;padding:0;float:left">
    <tr class="ok"><th style="width:19%"><a href="chap25.htm">25</a></th><td>AD <a href="cntnt25.htm">363-375</a></td></tr>
    <tr class="ok"><th><a href="chap26.htm">26</a></th><td>The <a href="cntnt26.htm">Barbarians</a> </td></tr>
    <tr><th><a href="chap27.htm">27</a></th><td>AD <a href="cntnt27.htm">379-395</a></td></tr>
    <tr><th><a href="chap28.htm">28</a></th><td>Destruction of <a href="cntnt28.htm">Paganism</a></td></tr>
    <tr><th><a href="chap29.htm">29</a></th><td>Empire's <a href="cntnt29.htm">Final Division</a></td></tr>
    <tr><th><a href="chap30.htm">30</a></th><td>AD <a href="cntnt30.htm">395-408</a></td></tr>
    <tr><th><a href="chap31.htm">31</a></th><td>AD <a href="cntnt31.htm">408-418</a></td></tr>
    </table>
    <table style="height:100%;width:20%;padding:0">
    <tr><th><a href="chap32.htm">32</a></th><td>AD <a href="cntnt32.htm">395-440</a></td></tr>
    <tr><th><a href="chap33.htm">33</a></th><td>AD <a href="cntnt33.htm">423-439</a></td></tr>
    
    <tr><th><a href="chap34.htm">34</a></th><td><a href="cntnt34.htm">The Huns</a></td></tr>
    
    <tr><th><a href="chap35.htm">35</a></th><td>AD <a href="cntnt35.htm">450-455</a></td></tr>
    
    <tr><th><a href="chap36.htm">36</a></th><td><a href="cntnt36.htm">Fall</a>  in the West</td></tr>
    
    <tr><th><a href="chap37.htm">37</a></th><td><a href="cntnt37.htm">Monastic Life</a></td></tr>
    
    
    <tr><th><a href="chap38.htm">38</a></th><td><a href="cntnt38.htm">Barbarian</a> Rule</td></tr>
    </table></td>
    
    </tr></table>
    
    <table style="margin:1em auto 0 auto; background:#FFFFFF; width:85%;font-family:arial;font-size:small;text-align:center">
    <tr>
    <td style="border:none">&#171; <a href="../volume2/index.htm">Fall in the East</a> &#187;</td>
    <td style="border:none">&#171; <a href="../volume1/chap39.htm">Observations</a> &#187;</td>
    <td style="border:none">&#171; <a href="../index.htm"><I>The History Of The Decline and  Fall</I></a> &#187;</td>
    <td style="border:none">&#171; <a href="http://www.ourcivilisation.com/smartboard/shop/index.htm">Library</a> &#187;</td></tr>
    </table>
    </BODY>
    </HTML>
    
    

**Input**
```python
soup = BeautifulSoup(html_string, 'html.parser')
```

**Input**
```python
chapter_urls = []

for s in soup.find_all('table'):
    for t in s.find_all('tr'):
        for u in t.find_all('th'):
            for v in u.find_all('a'):
                if v['href'] != "http://www.ourcivilisation.com/gibbon.htm":
                    chapter_urls.append("https://www.ccel.org/g/gibbon/decline/volume1/" + v['href'])

chapter_final = []
for url in chapter_urls:
    if url not in chapter_final:
        chapter_final.append(url)#[url for url in chapter_urls if url not in chapter_urls]

chap_dict = {}
for chapter in chapter_final:
    chap_dict[ChapterNumbers(chapter).strip()] = chapter         
    
chap_dict
```
**Output**

    {'Chapter 1': 'https://www.ccel.org/g/gibbon/decline/volume1/chap1.htm',
     'Chapter 2': 'https://www.ccel.org/g/gibbon/decline/volume1/chap2.htm',
     'Chapter 3': 'https://www.ccel.org/g/gibbon/decline/volume1/chap3.htm',
     'Chapter 4': 'https://www.ccel.org/g/gibbon/decline/volume1/chap4.htm',
     'Chapter 5': 'https://www.ccel.org/g/gibbon/decline/volume1/chap5.htm',
     'Chapter 6': 'https://www.ccel.org/g/gibbon/decline/volume1/chap6.htm',
     'Chapter 7': 'https://www.ccel.org/g/gibbon/decline/volume1/chap7.htm',
     'Chapter 8': 'https://www.ccel.org/g/gibbon/decline/volume1/chap8.htm',
     'Chapter 9': 'https://www.ccel.org/g/gibbon/decline/volume1/chap9.htm',
     'Chapter 10': 'https://www.ccel.org/g/gibbon/decline/volume1/chap10.htm',
     'Chapter 11': 'https://www.ccel.org/g/gibbon/decline/volume1/chap11.htm',
     'Chapter 12': 'https://www.ccel.org/g/gibbon/decline/volume1/chap12.htm',
     'Chapter 13': 'https://www.ccel.org/g/gibbon/decline/volume1/chap13.htm',
     'Chapter 14': 'https://www.ccel.org/g/gibbon/decline/volume1/chap14.htm',
     'Chapter 15': 'https://www.ccel.org/g/gibbon/decline/volume1/chap15.htm',
     'Chapter 16': 'https://www.ccel.org/g/gibbon/decline/volume1/chap16.htm',
     'Chapter 17': 'https://www.ccel.org/g/gibbon/decline/volume1/chap17.htm',
     'Chapter 18': 'https://www.ccel.org/g/gibbon/decline/volume1/chap18.htm',
     'Chapter 19': 'https://www.ccel.org/g/gibbon/decline/volume1/chap19.htm',
     'Chapter 20': 'https://www.ccel.org/g/gibbon/decline/volume1/chap20.htm',
     'Chapter 21': 'https://www.ccel.org/g/gibbon/decline/volume1/chap21.htm',
     'Chapter 22': 'https://www.ccel.org/g/gibbon/decline/volume1/chap22.htm',
     'Chapter 23': 'https://www.ccel.org/g/gibbon/decline/volume1/chap23.htm',
     'Chapter 24': 'https://www.ccel.org/g/gibbon/decline/volume1/chap24.htm',
     'Chapter 25': 'https://www.ccel.org/g/gibbon/decline/volume1/chap25.htm',
     'Chapter 26': 'https://www.ccel.org/g/gibbon/decline/volume1/chap26.htm',
     'Chapter 27': 'https://www.ccel.org/g/gibbon/decline/volume1/chap27.htm',
     'Chapter 28': 'https://www.ccel.org/g/gibbon/decline/volume1/chap28.htm',
     'Chapter 29': 'https://www.ccel.org/g/gibbon/decline/volume1/chap29.htm',
     'Chapter 30': 'https://www.ccel.org/g/gibbon/decline/volume1/chap30.htm',
     'Chapter 31': 'https://www.ccel.org/g/gibbon/decline/volume1/chap31.htm',
     'Chapter 32': 'https://www.ccel.org/g/gibbon/decline/volume1/chap32.htm',
     'Chapter 33': 'https://www.ccel.org/g/gibbon/decline/volume1/chap33.htm',
     'Chapter 34': 'https://www.ccel.org/g/gibbon/decline/volume1/chap34.htm',
     'Chapter 35': 'https://www.ccel.org/g/gibbon/decline/volume1/chap35.htm',
     'Chapter 36': 'https://www.ccel.org/g/gibbon/decline/volume1/chap36.htm',
     'Chapter 37': 'https://www.ccel.org/g/gibbon/decline/volume1/chap37.htm',
     'Chapter 38': 'https://www.ccel.org/g/gibbon/decline/volume1/chap38.htm'}



**Input**
```python
def ChapterNumbers(url):
    res = requests.get(url)
    chap_string = res.text
    chap_soup = BeautifulSoup(chap_string, 'html.parser')
    for t in chap_soup.find_all('h1'):
        try:
            Chapter = t.contents[0]
            if t.contents[1].string != 'XIV':
                Number = t.contents[1].string
            elif t.contents[1].string == 'XIV':
                Number = 14
            else:
                Number = 61
            string = Chapter + str(Number)
        except IndexError:
            string = url        
    return string
```

**Input**
```python
def getChapters(url):
    response = requests.get(url)
    html_string = response.text
    soup = BeautifulSoup(html_string, 'html.parser')
        
    chapter_urls = []

    for s in soup.find_all('table'):
        for t in s.find_all('tr'):
            for u in t.find_all('th'):
                for v in u.find_all('a'):
                    if v['href'] != "http://www.ourcivilisation.com/gibbon.htm":
                        chapter_urls.append(url[:-9] + v['href'])

    chapter_final = []
    for url in chapter_urls:
        if url not in chapter_final:
            chapter_final.append(url)#[url for url in chapter_urls if url not in chapter_urls]

    chap_dict = {}
    for chapter in chapter_final:
        chap_dict[ChapterNumbers(chapter).strip()] = chapter         

    return chap_dict
```

**Input**
```python
getChapters('https://www.ccel.org/g/gibbon/decline/volume2/index.htm')
```




    {'Chapter 39': 'https://www.ccel.org/g/gibbon/decline/volume2/chap39.htm',
     'Chapter 40': 'https://www.ccel.org/g/gibbon/decline/volume2/chap40.htm',
     'Chapter 41': 'https://www.ccel.org/g/gibbon/decline/volume2/chap41.htm',
     'Chapter 42': 'https://www.ccel.org/g/gibbon/decline/volume2/chap42.htm',
     'Chapter 43': 'https://www.ccel.org/g/gibbon/decline/volume2/chap43.htm',
     'Chapter 44': 'https://www.ccel.org/g/gibbon/decline/volume2/chap44.htm',
     'Chapter 45': 'https://www.ccel.org/g/gibbon/decline/volume2/chap45.htm',
     'Chapter 46': 'https://www.ccel.org/g/gibbon/decline/volume2/chap46.htm',
     'Chapter 47': 'https://www.ccel.org/g/gibbon/decline/volume2/chap47.htm',
     'Chapter 48': 'https://www.ccel.org/g/gibbon/decline/volume2/chap48.htm',
     'Chapter 49': 'https://www.ccel.org/g/gibbon/decline/volume2/chap49.htm',
     'Chapter 50': 'https://www.ccel.org/g/gibbon/decline/volume2/chap50.htm',
     'Chapter 51': 'https://www.ccel.org/g/gibbon/decline/volume2/chap51.htm',
     'Chapter 52': 'https://www.ccel.org/g/gibbon/decline/volume2/chap52.htm',
     'Chapter 53': 'https://www.ccel.org/g/gibbon/decline/volume2/chap53.htm',
     'Chapter 54': 'https://www.ccel.org/g/gibbon/decline/volume2/chap54.htm',
     'Chapter 55': 'https://www.ccel.org/g/gibbon/decline/volume2/chap55.htm',
     'Chapter 56': 'https://www.ccel.org/g/gibbon/decline/volume2/chap56.htm',
     'Chapter 57': 'https://www.ccel.org/g/gibbon/decline/volume2/chap57.htm',
     'Chapter 58': 'https://www.ccel.org/g/gibbon/decline/volume2/chap58.htm',
     'Chapter 59': 'https://www.ccel.org/g/gibbon/decline/volume2/chap59.htm',
     'Chapter 60': 'https://www.ccel.org/g/gibbon/decline/volume2/chap60.htm',
     'https://www.ccel.org/g/gibbon/decline/volume2/chap61.htm': 'https://www.ccel.org/g/gibbon/decline/volume2/chap61.htm',
     'Chapter 62': 'https://www.ccel.org/g/gibbon/decline/volume2/chap62.htm',
     'Chapter 63': 'https://www.ccel.org/g/gibbon/decline/volume2/chap63.htm',
     'Chapter 64': 'https://www.ccel.org/g/gibbon/decline/volume2/chap64.htm',
     'Chapter 65': 'https://www.ccel.org/g/gibbon/decline/volume2/chap65.htm',
     'Chapter 66': 'https://www.ccel.org/g/gibbon/decline/volume2/chap66.htm',
     'Chapter 67': 'https://www.ccel.org/g/gibbon/decline/volume2/chap67.htm',
     'Chapter 68': 'https://www.ccel.org/g/gibbon/decline/volume2/chap68.htm',
     'Chapter 69': 'https://www.ccel.org/g/gibbon/decline/volume2/chap69.htm',
     'Chapter 70': 'https://www.ccel.org/g/gibbon/decline/volume2/chap70.htm',
     'Chapter 71': 'https://www.ccel.org/g/gibbon/decline/volume2/chap71.htm'}




```python
book_urls = ["https://www.ccel.org/g/gibbon/decline/volume1/index.htm", "https://www.ccel.org/g/gibbon/decline/volume2/index.htm"]

full_book_dict = pd.concat([pd.DataFrame.from_dict(getChapters(book_urls[0]), orient='index'), pd.DataFrame.from_dict(getChapters(book_urls[1]), orient='index')])
```


```python
full_book_dict
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
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Chapter 1</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
    </tr>
    <tr>
      <th>Chapter 2</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
    </tr>
    <tr>
      <th>Chapter 3</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
    </tr>
    <tr>
      <th>Chapter 4</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
    </tr>
    <tr>
      <th>Chapter 5</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>Chapter 67</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
    </tr>
    <tr>
      <th>Chapter 68</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
    </tr>
    <tr>
      <th>Chapter 69</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
    </tr>
    <tr>
      <th>Chapter 70</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
    </tr>
    <tr>
      <th>Chapter 71</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
    </tr>
  </tbody>
</table>
<p>71 rows × 1 columns</p>
</div>




```python
def getText(url):
    response = requests.get(url)
    html_string = response.text
    text_soup = BeautifulSoup(html_string, 'html.parser')
    text_list = []
    
    for p in text_soup.find_all("p"):
        text_list.append(p.get_text())
        
    return ''.join(text_list)
```


```python
full_book_dict['String_Text'] = full_book_dict[0].apply(getText)
```


```python
full_book_dict
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
      <th>0</th>
      <th>String_Text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Chapter 1</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>The extent and military force of the Roman emp...</td>
    </tr>
    <tr>
      <th>Chapter 2</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>Of the Union and Internal Prosperity of the Ro...</td>
    </tr>
    <tr>
      <th>Chapter 3</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>Of the Constitution of the Roman Empire in the...</td>
    </tr>
    <tr>
      <th>Chapter 4</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>The cruelty, follies and murder of Commodus. E...</td>
    </tr>
    <tr>
      <th>Chapter 5</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>Public sale of the Empire to Didius Julianus b...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Chapter 67</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Schism of the Greeks and Latins.\n Reign and C...</td>
    </tr>
    <tr>
      <th>Chapter 68</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Reign and Character of Mahomet the Second.\n S...</td>
    </tr>
    <tr>
      <th>Chapter 69</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>State of Rome from the Twelfth Century.\n Temp...</td>
    </tr>
    <tr>
      <th>Chapter 70</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Character and Coronation of Petrarch. \nRestor...</td>
    </tr>
    <tr>
      <th>Chapter 71</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Prospect of the Ruins of Rome in the Fifteenth...</td>
    </tr>
  </tbody>
</table>
<p>71 rows × 2 columns</p>
</div>




```python
tfidf = TfidfVectorizer(max_df=0.95, min_df=2, stop_words='english')
dtm = tfidf.fit_transform(full_book_dict['String_Text'])
dtm
```




    <71x13769 sparse matrix of type '<class 'numpy.float64'>'
    	with 196945 stored elements in Compressed Sparse Row format>




```python
nmf_model = NMF(n_components=15,random_state=42)
nmf_model.fit(dtm)
```

    C:\Users\brian\miniconda3\lib\site-packages\sklearn\decomposition\_nmf.py:312: FutureWarning: The 'init' value, when 'init=None' and n_components is less than n_samples and n_features, will be changed from 'nndsvd' to 'nndsvda' in 1.1 (renaming of 0.26).
      warnings.warn(("The 'init' value, when 'init=None' and "
    




    NMF(n_components=15, random_state=42)




```python
for index,topic in enumerate(nmf_model.components_):
    print(f'THE TOP 15 WORDS FOR TOPIC #{index+1}')
    print([tfidf.get_feature_names()[i] for i in topic.argsort()[-15:]])
    print('\n')
```

    THE TOP 15 WORDS FOR TOPIC #1
    ['province', 'tribes', 'claudius', 'senate', 'tacitus', 'germany', 'legions', 'valerian', 'gaul', 'gallienus', 'danube', 'probus', 'germans', 'goths', 'aurelian']
    
    
    THE TOP 15 WORDS FOR TOPIC #2
    ['barons', 'pilgrims', 'sultan', 'french', 'knights', 'robert', 'baldwin', 'saladin', 'france', 'godfrey', 'crusaders', 'holy', 'jerusalem', 'latins', 'alexius']
    
    
    THE TOP 15 WORDS FOR TOPIC #3
    ['spiritual', 'religious', 'pagans', 'persecution', 'bishop', 'zeal', 'christ', 'athanasius', 'faith', 'christianity', 'religion', 'bishops', 'christian', 'church', 'christians']
    
    
    THE TOP 15 WORDS FOR TOPIC #4
    ['alemanni', 'libanius', 'gods', 'romans', 'gaul', 'march', 'troops', 'antioch', 'tigris', 'caesar', 'jovian', 'gallus', 'sapor', 'constantius', 'julian']
    
    
    THE TOP 15 WORDS FOR TOPIC #5
    ['elagabalus', 'albinus', 'guards', 'macrinus', 'alexander', 'praetorian', 'augustus', 'marcus', 'niger', 'caracalla', 'maximin', 'pertinax', 'commodus', 'severus', 'senate']
    
    
    THE TOP 15 WORDS FOR TOPIC #6
    ['moslems', 'arabian', 'koreish', 'arabs', 'koran', 'ali', 'abubeker', 'caliphs', 'saracens', 'caliph', 'omar', 'prophet', 'mecca', 'medina', 'mahomet']
    
    
    THE TOP 15 WORDS FOR TOPIC #7
    ['procopius', 'ravenna', 'king', 'constantinople', 'romans', 'gelimer', 'vandals', 'italy', 'antonina', 'theodora', 'narses', 'gothic', 'goths', 'justinian', 'belisarius']
    
    
    THE TOP 15 WORDS FOR TOPIC #8
    ['italy', 'church', 'vatican', 'petrarch', 'ursini', 'capitol', 'peter', 'romans', 'avignon', 'st', 'cardinals', 'pope', 'popes', 'rienzi', 'colonna']
    
    
    THE TOP 15 WORDS FOR TOPIC #9
    ['troops', 'minister', 'radagaisus', 'claudian', 'gothic', 'gainas', 'constantinople', 'goths', 'eutropius', 'alaric', 'arcadius', 'theodosius', 'honorius', 'rufinus', 'stilicho']
    
    
    THE TOP 15 WORDS FOR TOPIC #10
    ['edecon', 'constantinople', 'ambassadors', 'goths', 'scythia', 'scythian', 'honoria', 'king', 'valens', 'maximin', 'valentinian', 'theodosius', 'aetius', 'huns', 'attila']
    
    
    THE TOP 15 WORDS FOR TOPIC #11
    ['constans', 'emperors', 'italy', 'tiridates', 'troops', 'crispus', 'magnentius', 'maximin', 'maxentius', 'constantius', 'maximian', 'licinius', 'galerius', 'diocletian', 'constantine']
    
    
    THE TOP 15 WORDS FOR TOPIC #12
    ['gothic', 'aetius', 'goths', 'visigoths', 'king', 'anthemius', 'clovis', 'odoacer', 'valentinian', 'placidia', 'italy', 'gaul', 'genseric', 'vandals', 'theodoric']
    
    
    THE TOP 15 WORDS FOR TOPIC #13
    ['soliman', 'constantinople', 'janizaries', 'anatolia', 'mahomet', 'mogul', 'zingis', 'moguls', 'amurath', 'turks', 'ottoman', 'bajazet', 'turkish', 'timour', 'sultan']
    
    
    THE TOP 15 WORDS FOR TOPIC #14
    ['king', 'hormouz', 'magi', 'phocas', 'artaxerxes', 'justinian', 'lombards', 'nushirvan', 'maurice', 'persians', 'persia', 'avars', 'persian', 'heraclius', 'chosroes']
    
    
    THE TOP 15 WORDS FOR TOPIC #15
    ['pope', 'manuel', 'catalans', 'genoese', 'john', 'patriarch', 'byzantine', 'latins', 'greek', 'cantacuzene', 'michael', 'greeks', 'andronicus', 'palaeologus', 'constantinople']
    
    
    


```python
f = open("gibbon_topics.txt", "w")
for index,topic in enumerate(nmf_model.components_):
    f.write(f'THE TOP 15 WORDS FOR TOPIC #{index+1}')
    f.write(str([tfidf.get_feature_names()[i] for i in topic.argsort()[-15:]]))
    f.write('\n')
f.close
```




    <function TextIOWrapper.close()>




```python
topic_results = nmf_model.transform(dtm)
full_book_dict['Topic'] = topic_results.argmax(axis=1)
full_book_dict
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
      <th>0</th>
      <th>String_Text</th>
      <th>Topic</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Chapter 1</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>The extent and military force of the Roman emp...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>Chapter 2</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>Of the Union and Internal Prosperity of the Ro...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>Chapter 3</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>Of the Constitution of the Roman Empire in the...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>Chapter 4</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>The cruelty, follies and murder of Commodus. E...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>Chapter 5</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume1/...</td>
      <td>Public sale of the Empire to Didius Julianus b...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Chapter 67</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Schism of the Greeks and Latins.\n Reign and C...</td>
      <td>12</td>
    </tr>
    <tr>
      <th>Chapter 68</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Reign and Character of Mahomet the Second.\n S...</td>
      <td>12</td>
    </tr>
    <tr>
      <th>Chapter 69</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>State of Rome from the Twelfth Century.\n Temp...</td>
      <td>7</td>
    </tr>
    <tr>
      <th>Chapter 70</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Character and Coronation of Petrarch. \nRestor...</td>
      <td>7</td>
    </tr>
    <tr>
      <th>Chapter 71</th>
      <td>https://www.ccel.org/g/gibbon/decline/volume2/...</td>
      <td>Prospect of the Ruins of Rome in the Fifteenth...</td>
      <td>7</td>
    </tr>
  </tbody>
</table>
<p>71 rows × 3 columns</p>
</div>


