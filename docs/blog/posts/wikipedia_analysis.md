---
draft: false 
date: 2025-09-15
categories:
  - Corpora
authors:
  - team
tags:
  - data_analysis
  - NLP
# icon: fontawesome/solid/masks/theater not rendered
comments: true
---

# Thai wikipedia

We processed a Sept. 2025 dump of [Thai wikipedia](https://th.wikipedia.org/). The purpose was to produce a frequency list based on a relatively neutral corpus. Throughout this blog, the resulting frequency list will be referred to as the 'thwiki' list. 500,000 articles, north of 150+ million words/tokens. We processed it so you don't have to.

<!-- more -->

## Sourcing

!!! info "a big file"
    - https://dumps.wikimedia.org/thwiki
    - update 20250901
    - bz2 460MB to xml 1 file 3GB 
    - high-level site-info and 593,089 pages


**thwiki** as a corpus?

Assumptions:
- it is balanced;
    it is not a wiki where article/stubs-generating bots are active;
    not many stubs for places, plants, animals, persons, companies, chemicals, etc.
- it covers most practical aspects of language in a semi-formal register (mostly);


## The process

### 'Design' Decisions

- no history log
- no discussion thread
- no deleted pages
- strip all technical markers, and meta info (e.g. title/heading/etc.)
- remove any words/segment not in Thai,
    - inc. unit (km, kg, etc.); # might be TEMP
    - any latin characters
    - words in Pali, Sanskrit, Khmer, written Chinese characters, etc.
- keep any segment even not in dictionary, but cut off at 5 occurences (might ned to raise to 10, tradi corpus work 3-5);
    - proper names etc. likely to be cut off, or very low occurences, so leave in;
- at least in first pass, do not attempt to remove infoboxes, and category links;
    - these will increase the occurences of certain words, but we feel it reflects actual increased usage.
    - we note that it might skew slightly the frequency for these words
- repeat-word ฯ 	paiyan noi
    1- as distinct word
    2- remove symbol, 1 word count
    3- double occurence NOPE
- keep only the most recent revision of an article, but regardless of status


**headers**

they are not attributed a special weight, as in e.g. Google Page Rank, but on the other hand, if some titles appear frequently (think of "Overview", "Plot", "References"), they **do** appear more frequently. They are therefore counted. The skew is likely marginal.

### Why less than 5 cutoff?

!!! info "Paul Nation and extensive reading"
    Paul Nation and his colleagues' research indicates that 95-98% vocabulary coverage is required for extensive reading.

    At 95% coverage: This translates to about one unknown word in every 20 running words. Research suggests that this level is adequate for gaining a basic understanding and guessing unknown words from context.

    At 98% coverage: This means about one unknown word in every 50 running words. At this higher level, the density of unknown words is low enough that comprehension is more fluent and less interrupted. Guessing from context becomes more reliable, and the reader can focus more on the meaning of the text.

    Summary: 95% undersatnding and new acquisitions from context, 98% comfortable reading.

!!! info "Standards for frequency lists"
    When reducing corpora to frequency lists, linguists generally apply a 3 to 5 occurences cut-off. But to compare two frequency rankings, the value of 5 for cut-off is the standard (5+ occur. for chi-squared). 
    
    As our ultimate goal is two compare the thwiki and the แจ่มไพบูลย์/แรช rankings, we used a 5 cut-off straight off the bat for thwiki.


Considering extensive reading and cut-off for the แจ่มไพบูลย์/แรช Frequency List for Thai Learners:

- Rank 11,557 is first word at 5, 12,316 the last;
- 95% of cumulative frequency spans words 3,856-4,479;
- 98% spans 6,495-8,361.

Conclusion: using a cut-off of 5 gives us roughly 12k words to compare with thwiki, and 12k is equivalent to 99% coverage of the textbooks.


### Soft side

We used `pythainlp.newmm` algorithm, which, as per our understanding, is an enhanced version of the dictionary-based, co-location, maximising algo used by Dr.Tantong Champaiboon in her thesis. Accuracy improved.

python scripts and regexes were used for the pre- and post-processing.

We used the dictionary coming with the algo, we are still working on superdict.

Excel was used for some final post-processing.

## The results

Number of articles: 395,944
Total tokens: 152,815,652
Dict raw size: 2,414,272 (tokens)

After removing non-Thai characters and arabic numbers:
Dict clean size: 189,101

At this stage, it still contains a few entries with spaces, tabs and/or nbsp, and punctuation and numbers (thai numbers).

can eliminate in excel
    1. sort on word
    2. delete 
    3. sort by count desc.

After excel clean up, they are no longer tokens, but words.

count	 184,760 on a total words	of 88,478,626 

113,854 have 5 or less occurences -> cut-off (less than 5 would have been ~ 109k)

After cut-off:

### count	 70,906 
### total words	 88,283,877 
### Contains 585 repeat-words

| rank | word | count | raw freq | cum. freq | position |
| :---: | :--- | :---: | ---: | ---: | :---: |
| 12265	| เชี่ยน	| 481	| 0.00%		| 95.00%		| FIRST 95	| 
| 14377	| นายพราน	| 361 	| 	0.00%	| 	95.99%	| 	LAST 95	| 
| 21818	| ลัสปัลมัส	| 152 	| 	0.00%	| 	98.00%		| FIRST 98	| 
| 30434	| เก็บเสียง	| 67 	| 	0.00%		| 98.99%		| LAST 98	| 



## Further work

We are working on a comparison of the ranking between the 20k frequency list and the one obtained from wikipedia. Stay posted.