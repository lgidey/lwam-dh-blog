---
layout: post
title:  "Blog#3: Named Entities Recognition "
date:   2021-10-03 12:37:53 -0400
categories: jekyll update
---

[Python code to retrieve labeled entities from chap.30](https://colab.research.google.com/drive/1O-ih0mm8vqJtWDNozPO5YYBEXwqOyc8c#scrollTo=vbkqg7QZWhq3)

**Output**
```
<NORP>Goths</NORP>
<GPE>Italy</GPE>
<PERSON>Alaric</PERSON>
<NORP>Germans</NORP>
<PERSON>Constantine</PERSON>
<GPE>Rome</GPE>
<DATE>winter</DATE>
<NORP>Gothic</NORP>
<ORDINAL>first</ORDINAL>
<LOC>Danube</LOC>

<ORG>Scythia</ORG> wrong label  
<DATE>winter</DATE>
<LOC>Danube</LOC>
<NORP>Gothic</NORP>
<LOC>Dalmatia</LOC>
<NORP>Goths</NORP>
<PERSON>Rufinus</PERSON>
<NORP>Roman</NORP>
<ORG>Imperial</ORG>
<PERSON>Arcadius</PERSON>


<NORP>Gothic</NORP>
<PERSON>Alaric</PERSON>
<LOC>Thrace</LOC>
<PERSON>Alaric</PERSON>
<CARDINAL>396</CARDINAL> irrelevant
<PERSON>Rufinus</PERSON>
<GPE>Greece</GPE>
<NORP>Gothic</NORP>
<PERSON>Antiochus</PERSON>
<PERSON>Alaric</PERSON>

<GPE>Macedonia</GPE>
<CARDINAL>three</CARDINAL> irrelevant
<CARDINAL>hundred</CARDINAL> irrelevant
<PERSON>Leonidas</PERSON>
```

**F-measure**
```
F-measure = 2*(Recall * Percision) (percision + Recall   =2*(0.97 * 0.88)/(0.97 + 0.88) = 1.71/1.85 = 0.923

Precision = # of instances correctly labeled by NER system/ total number of instances labeled by system =33 /34 =0.97

Recall = # of  relevant instances  labeled by NER system/  total number of instances labeled by system =30 /34 = 0.88
```


**Notes from NER classification techniques article:**

Metrics used to evaluate NER system performance :
Precision = number of instances correctly labeled by system / total number of instances labled by the system


Recall = number of instances correctly labeled by system/ total number of relevant instances labeled by the system
F-measure = 2 *(precision * Recall)/(precision + Recall)



**

Information extraction has become crucial

Named Entity recognition and classification
Finding predetermined classes such as persoon, location, date/time
Test pre-processing tools for nlp
Named Entity
Word form that recognizes the elements having similar properties

NERC(Named Entity Recognition and Classification)
Points to identify and classify members named entities
NERC recognizes and classifies entities
Important step in information extraction
Techniques for NERC:
Ruled-based approaches
Domain specific
Hand-crafted
Learning-based approaches
Machine learning: supervised(labeled training data) and unsupervised (not labeled and make decisions )
Hybrid approaches : using both
