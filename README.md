
# The Cambridge MathIR Test Collection (version 1.0)
# Yiannos Stathopoulos and Simone Teufel.


## 1. Introduction
---------------

Thank you for your interest in downloading our MathIR test collection and using it in your research.
Please cite the following paper if you are using the corpus in your research:

Yiannos A. Stathopoulos, Simone Teufel:
Retrieval of research-level mathematical information needs: A Test Collection and Technical Terminology Experiment
In Proceedings of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International 
Joint Conference on Natural Language Processing of the Asian Federation of Natural Language Processing 
(ACL-IJCNLP 2015). Beijing, China, 2015.

The following BibTeX code may be of use:
@InProceedings{stathopoulos-teufel:2015:ACL-IJCNLP,
  author    = {Stathopoulos, Yiannos  and  Teufel, Simone},
  title     = {Retrieval of Research-level Mathematical Information Needs: A Test Collection and Technical Terminology Experiment},
  booktitle = {Proceedings of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing (Volume 2: Short Papers)},
  month     = {July},
  year      = {2015},
  address   = {Beijing, China},
  publisher = {Association for Computational Linguistics},
  pages     = {334--340},
  url       = {http://www.aclweb.org/anthology/P15-2055}
}

Throughout the following text, the above paper will be referenced as [1].

This test collection is distributed by Yiannos A. Stathopoulos and Simone Teufel, and has been downloaded
from 

http://www.cl.cam.ac.uk/~yas23/

## 2. Contents
-----------

README.txt - This readme file
topics/	- A directory with 120 html/text files containing topic data.
judgements.csv - A CSV file encoding the relevance judgements (see section 4)

## 3. Topics 
---------

The topics included with the test collection can be found under the "topics" directory.
There is a total of 120 files under this directory - one for each topic/MathOverflow thread.

3.1. Topic format

Topics are represented by a combination of HTML (adapted from the original MO data dump), MathML (derived from the original LaTeX) and
sentence tags. 

Sentence tags are used to tokenize sentences as described in [1]. In short, sentence tags can either denote sentence text that belongs 
to the prelude or a specific question. This information is encoded using attributes as shown in the following two examples:

(a) A prelude sentence
```
<s id="1" type="p">It is well known that if c(K)=2n+1, then u(K) is less than n+1.</s>
```
In this example, the &lt;s&gt; markup indicates that the sentence is the first sentence in the topic (id="1") and that it belongs to the prelude (type="p").

(b) A sentences belonging to sub-topic 2
```
<s id="5" type="q" qid="2">(2) Is there some reference for the specific case of the Universal enveloping algebra of a finite-dimensional 
semi-simple Lie algebra over C?</s>
```

In this example, the &lt;s&gt; markup indicates that the sentence is the fifth sentence in the topic (id="5"), is a question sentence (type="q") and, specifically, to sub-topic 2 (qid="2").


## 3.2. Some notes on the topic markup

As highlighted in [1], our aim has been to distribute topics from which researchers can generate queries as needed, in the spirit of TREC. We have annotated topics 
with the previously described strategy to enable researchers to do just that and experiment with different query strategies. As a result, the strategy used to 
generate actual queries becomes the responsibility of individual researchers (and the tasks of interests). One possible strategy that described in [1] where 
one query is generated per sub-topic by concatenating the topic prelude to the sub-topic sentences.

We have done our best to ensure that the <s> markup is consistent and valid. 
However, some errors may have creeped through since the annotation has been done by hand. Also, in some cases, text may not have been assigned to neither prelude nor 
a particular question. This is usually the case for text that is not relevant to either part of the discourse such as salutations (e.g., "Hello...") 
and expressions of gratitude (e.g., "Many thanks in advance..").

## 4. The relevance Judgements
---------------------------

The relevance judgements are distributed as the CSV file "judgements.csv", which will refer to as "the judgements file" from hence forth. 
Each line in the judgements file is a record of 5 fields, that represents a judgement by grouping the necessary information (a topic, sub-topic and document ID).
With the exception of the first line which is the header, there are 184 records in the judgements file. Fields in the CSV file are as follows:

seqid - The topic's sequence ID. This is the same as the number in a topic's filename.
postid - The MathOverflow questions ID from which the topic is derived.
doc_arxivid - The ArXiv document ID associated with the judgement represented by the record.
citationid - The citation sequence ID of the document doc_arxivid. This is used to identify a citated document in the set of all cited documents in the answer.
subtopic - The subtopic id, a number that is the same as that in the corresponding "qid" attribute of the <s> tags in the topic file.

Please note that relevant documents in the judgements are represented by their arxiv ID, which has been extracted from ArXiv metadata.
Therefore, matching physical document filenames to judgements may require additional effort as this is dependent on the MREC distribution and file naming strategy.

## 5. License
----------

This test collection (topics, relevance judgements) is distributed under 
the Creative commons license Creative Commons Attribution-Share Alike license (http://creativecommons.org/licenses/by-sa/3.0/).

In addition, we require that 

(a) Any modification and/or re-distribution of this test collection include this README file.
(b) Any use of this test collection cite the work mentioned in section 1.

This test collection is based on material posted on MathOverflow.net which, according to http://mathoverflow.net/help/licensing, is licensed under the 
Creative Commons Attribution-Share Alike license (http://creativecommons.org/licenses/by-sa/3.0/).

We hereby provide credit to MathOverflow.net users by including the MathOverflow urls this test collection is based on:

http://www.mathoverflow.net/questions/100008/
http://www.mathoverflow.net/questions/100451/
http://www.mathoverflow.net/questions/101707/
http://www.mathoverflow.net/questions/103540/
http://www.mathoverflow.net/questions/104664/
http://www.mathoverflow.net/questions/105543/
http://www.mathoverflow.net/questions/107041/
http://www.mathoverflow.net/questions/108661/
http://www.mathoverflow.net/questions/108823/
http://www.mathoverflow.net/questions/108912/
http://www.mathoverflow.net/questions/109218/
http://www.mathoverflow.net/questions/111943/
http://www.mathoverflow.net/questions/114267/
http://www.mathoverflow.net/questions/115099/
http://www.mathoverflow.net/questions/116485/
http://www.mathoverflow.net/questions/118930/
http://www.mathoverflow.net/questions/120232/
http://www.mathoverflow.net/questions/120893/
http://www.mathoverflow.net/questions/121315/
http://www.mathoverflow.net/questions/122180/
http://www.mathoverflow.net/questions/125255/
http://www.mathoverflow.net/questions/126610/
http://www.mathoverflow.net/questions/127010/
http://www.mathoverflow.net/questions/12758/
http://www.mathoverflow.net/questions/12962/
http://www.mathoverflow.net/questions/129818/
http://www.mathoverflow.net/questions/130010/
http://www.mathoverflow.net/questions/130191/
http://www.mathoverflow.net/questions/13058/
http://www.mathoverflow.net/questions/131134/
http://www.mathoverflow.net/questions/132134/
http://www.mathoverflow.net/questions/132191/
http://www.mathoverflow.net/questions/133673/
http://www.mathoverflow.net/questions/134733/
http://www.mathoverflow.net/questions/134974/
http://www.mathoverflow.net/questions/137227/
http://www.mathoverflow.net/questions/138722/
http://www.mathoverflow.net/questions/142434/
http://www.mathoverflow.net/questions/142519/
http://www.mathoverflow.net/questions/142938/
http://www.mathoverflow.net/questions/145292/
http://www.mathoverflow.net/questions/146554/
http://www.mathoverflow.net/questions/147381/
http://www.mathoverflow.net/questions/148549/
http://www.mathoverflow.net/questions/148980/
http://www.mathoverflow.net/questions/150968/
http://www.mathoverflow.net/questions/151268/
http://www.mathoverflow.net/questions/151608/
http://www.mathoverflow.net/questions/16848/
http://www.mathoverflow.net/questions/17072/
http://www.mathoverflow.net/questions/17440/
http://www.mathoverflow.net/questions/18336/
http://www.mathoverflow.net/questions/19090/
http://www.mathoverflow.net/questions/19607/
http://www.mathoverflow.net/questions/21257/
http://www.mathoverflow.net/questions/22398/
http://www.mathoverflow.net/questions/23487/
http://www.mathoverflow.net/questions/24137/
http://www.mathoverflow.net/questions/26528/
http://www.mathoverflow.net/questions/26776/
http://www.mathoverflow.net/questions/27922/
http://www.mathoverflow.net/questions/30402/
http://www.mathoverflow.net/questions/30629/
http://www.mathoverflow.net/questions/30788/
http://www.mathoverflow.net/questions/31250/
http://www.mathoverflow.net/questions/32412/
http://www.mathoverflow.net/questions/3309/
http://www.mathoverflow.net/questions/37578/
http://www.mathoverflow.net/questions/37602/
http://www.mathoverflow.net/questions/38437/
http://www.mathoverflow.net/questions/39402/
http://www.mathoverflow.net/questions/40887/
http://www.mathoverflow.net/questions/41742/
http://www.mathoverflow.net/questions/42283/
http://www.mathoverflow.net/questions/4259/
http://www.mathoverflow.net/questions/45232/
http://www.mathoverflow.net/questions/45782/
http://www.mathoverflow.net/questions/46524/
http://www.mathoverflow.net/questions/4699/
http://www.mathoverflow.net/questions/53669/
http://www.mathoverflow.net/questions/56275/
http://www.mathoverflow.net/questions/5790/
http://www.mathoverflow.net/questions/58071/
http://www.mathoverflow.net/questions/58825/
http://www.mathoverflow.net/questions/61615/
http://www.mathoverflow.net/questions/62815/
http://www.mathoverflow.net/questions/64112/
http://www.mathoverflow.net/questions/64211/
http://www.mathoverflow.net/questions/65841/
http://www.mathoverflow.net/questions/66210/
http://www.mathoverflow.net/questions/6764/
http://www.mathoverflow.net/questions/67808/
http://www.mathoverflow.net/questions/68096/
http://www.mathoverflow.net/questions/68110/
http://www.mathoverflow.net/questions/69471/
http://www.mathoverflow.net/questions/71661/
http://www.mathoverflow.net/questions/73279/
http://www.mathoverflow.net/questions/74843/
http://www.mathoverflow.net/questions/75245/
http://www.mathoverflow.net/questions/75471/
http://www.mathoverflow.net/questions/78191/
http://www.mathoverflow.net/questions/8228/
http://www.mathoverflow.net/questions/8262/
http://www.mathoverflow.net/questions/83626/
http://www.mathoverflow.net/questions/84508/
http://www.mathoverflow.net/questions/85547/
http://www.mathoverflow.net/questions/85741/
http://www.mathoverflow.net/questions/87622/
http://www.mathoverflow.net/questions/88037/
http://www.mathoverflow.net/questions/88112/
http://www.mathoverflow.net/questions/88568/
http://www.mathoverflow.net/questions/89258/
http://www.mathoverflow.net/questions/90038/
http://www.mathoverflow.net/questions/90151/
http://www.mathoverflow.net/questions/90645/
http://www.mathoverflow.net/questions/91282/
http://www.mathoverflow.net/questions/95158/
http://www.mathoverflow.net/questions/95970/
http://www.mathoverflow.net/questions/96584/
http://www.mathoverflow.net/questions/99972/
