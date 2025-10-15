# Columns

A Thai word frequency list of ~20k words used in textbooks of primary and secondary school for Thai children	
The แจ่มไพบูลย์/แรช Frequency List for Thai Learners v2.4	
	
The first 2,500-2,700 roughly correspond to primary school level. The whole list to secondary school level. 	
	
## Columns	
**index** - the index in the source thesis (19,494 words).

**word** - the Thai word

Measures of complexity (from the orginal work)
- **role** - Is it a content word, a grammar word, or both?
- **morpho** (morphology) - Single word, combined, compound, complex, or Eng. loanword
- **syllables** - 1, 2, or 3-and-more syllables
- **spelling** - 1, 2, or 3-and-more ways in which the word can be pronounced. Anything above 1 is a candidate for us to use the transliteration to learn the correct way(s) to pronounce.
- **semantics** - From easy to hard: Single words and English transliterations, Transparent, Ambiguous words, Opaque words

**senses** - textblock where each line is a type followed by the English meaning, e.g. Prep. To

**examples** - most entries have one or more sample. [I personally have a strong dislike of Anki and the likes, I prefer to learn in context.)

**classifiers** – one or more classifiers with their transliteration.

**ipa** – phonetics (most ipa, a few ThaiPhon)

**translit** - paiboon-esque transliteration **with** tone marks

**audio** – 1 if an audio file exists (sorry not shareable at this stage)

**audio_urls** –  1 or several URLs of audio in wikimedia

**num_senses** - number of senses/meanings

**weight** – 0 to 4 – how many dictionaries the word was found in

**quality** – quality markers include: NO_SENSE, NO_IPA and NO_TRANSLIT

**cumfreq** – the cumulative frequency in the original study, e.g. words 1 to 110 represent 50% of the occurrences in the 3M-words corpus.

## Details on some columns (caveats & distribution)
**Stats**: 19,494 words, 1,169 repeat-words, 2/3-rds of the words have examples. 
110 words represent half the corpus, and slightly less than 2,100 represent 90%. But on the other hand, 13,600 words are present in 3 or all 4 of the source dictionaries (see section ‘sources’), so they compose a ‘hard’ core of the Thai language. 

~60% have **audio** available; audio caveat: the links to Wikimedia are effective, but have not been verified one by one. I have not yet received authorisation to share the files for the ‘audio’ column (value=1)  I will update here if and when. In the meanwhile, the files are **not** available.

Normalized Frequency (NF) --ความยากง่ายในมิติต่าง ๆ --learning levels 1 to 4

### ความยากง่ายในมิติต่าง ๆ (dimensions of difficulty/complexity)
| Original work | List v2.4 for Thai L2 |
|:---|:---|
| คำเนื้อหา-คำไวยากรณ์ C/F<br/>C = คำเนื้อหา<br/>F = คำไวยากรณ์<br/>CF = คำที่เป็นได้ทั้งคำเนื้อหาและคำไวยากรณ์ | **role** - Is it a content word, a grammar word, or both? |
|  |  |
| การสร้าง-การประกอบคำ Morpho<br/>เดี่ยว = คำเดี่ยว<br/>ประสาน = คำประสาน<br/>ประสม = คำประสม<br/>ซ้อน = คำซ้อน<br/>ซ้ำ = คำซ้ำ<br/>ทับE = คำทับศัพท์ภาษาอังกฤษ | **Morpho-Word Formation**<br/>Single = Single word<br/>Combined = Combined word<br/>Compound = Compound word<br/>Duplicated = Repeated word COMPLEX?<br/>Repeat = Repeated word<br/>Transliterated = English transliterated word |
|  |  |
| จำนวนพยางค์ Syl<br/>1 = คำที่มี 1 พยางค์<br/>2 = คำที่มี 2 พยางค์<br/>3 = คำที่มีตั้งแต่ 3 พยางค์ขึ้นไป | **syllables** - 1, 2, or 3-and-more syllables |
|  |  |
| รูปเขียนกับการออกเสียง F/S<br/>1 – ไม่จำกัด ตัวเลขที่แสดงแทนจำนวนความเป็นไปได้ในการออกเสียงรูปศัพท์นั้น ๆ | **spelling and pronunciation** - 1, 2, or 3-and-more |
|  |  |
| ความทึบใสทางความหมาย Seman<br/>0 = คำเดี่ยวและคำทับศัพท์ภาษาอังกฤษ<br/>1 = คำใส<br/>2 = คำก้ำกึ่ง ไม่ทึบไม่ใส<br/>3 = คำทึบ | **Semantic opacity**<br/>0 = Single words and English transliterations<br/>1 = Transparent<br/>2 = Ambiguous words, neither opaque nor transparent<br/>3 = Opaque words |

* * *
## Distribution (complexity)

| role          |       |
| ------------- | ----- |
| both          | 102   |
| content       | 19052 |
| grammar       | 340   |

| morpho        |       |
| ------------- | ----- |
| combined      | 301   |
| complex       | 1642  |
| compound      | 7057  |
| loan Eng.     | 551   |
| repeated word | 1169  |
| single        | 8774  |

| spelling      |       |
| ------------- | ----- |
| 1             | 9470  |
| 2             | 4732  |
| 3             | 1540  |
| 4-990         | 3752  |

| semantics     |       |
| ------------- | ----- |
| ambiguous     | 1289  |
| opaque        | 1102  |
| single        | 9325  |
| transparent   | 7778  |

## Correlation
<picture>  <img src="assets/grades vs ranks -in-.png" alt="grades vs ranks" /></picture>\
**schooling levels vs 3k-bins** - words in the list (grouped in 3k words bins) compared with school levels
- primary 1-3 (+pre-school)
- primary 4-6
- secondary 1-3
- secondary 4-6

<picture>  <img src="assets/morphology vs semantics.png" alt="morphology vs semantics" /></picture>\
**morphology vs semantics**

<picture>  <img src="assets/number of words in dictionaries.png" alt="number of words in dictionaries" /></picture>\
**number of words in dictionaries**


* * *
## Sources & licences	
	
The thesis [https://www.arts.chula.ac.th/~ling/TTC/], as far as I can tell is in the public domain.	

Lexitron v2: [https://opend-portal.nectec.or.th/en/prepare/lexitron-2-0] NECTEC licence.	

Wiktionary [https://th.wiktionary.org/] is licenced under CC BY-SA 4.0 (Attribution-Share Alike 4.0 International)	

Volubilis v. 25.2 [https://belisan-volubilis.blogspot.com/], also under CC BY-SA 4.0.	

The Royal Institute Dictionary 1999 is also under NECTEC licence.	
	
This product is created by the adaptation of LEXiTRON developed by NECTEC.	
This frequency list is shared under CC BY-SA 4.0, including the mention above as work derivative from a NECTEC production.	


.
