# Session-7
End Session 3

Existing metrics for Natural Language Generation can be broadly categorized into using

1. N-gram Matching
2. Edit Distance
3. Embedding Matching or Learned functions

## Precision, Recall & F1-score

![image](https://user-images.githubusercontent.com/30425824/145586623-d53d1269-9e3e-4da4-a11f-b29ef2ad5932.png)

from code   
![image](https://user-images.githubusercontent.com/30425824/145595575-50c38bf4-2ebe-417b-bf76-c3bd4af6a7e8.png)


## Bleu Score ##
a. Bilingual Evaluation Understudy (BLEU)   
b. Measures what percentage of n-grams are present both in candidate corpus and reference corpus   
c. BLEU1 --> counts n-grams up to a length of 1, BLEU4 --> counts n-grams up to a length of 4.   
d. BLEU score is not only used as a metric for Machine Translation but also for other NLG tasks.   
e. Ordering of words is captured with n-gram but it doesn’t penalize more if the order is changed. Since meaning completely changes when the order is changed.   
f. Doesn’t take into account the grammar of the sentence.   
![image](https://user-images.githubusercontent.com/30425824/145586323-3b9a8de2-2d6f-46e6-a56c-cd79296c9b7e.png)

## Perplexity ##

Perplexity is just an exponentiation of the entropy!
Entropy is the average number of bits to encode the information contained in a random variable, so the exponentiation of the entropy should be the total amount of all possible information, or more precisely, the weighted average number of choices a random variable has.
For example, if the average sentence in the test set could be coded in 100 bits, the model perplexity is 2¹⁰⁰ per sentence

![image](https://user-images.githubusercontent.com/30425824/145587054-9c783bd3-31fe-4440-ae01-a383f3926021.png)

## BERT Score ##

BertScore computes the similarity of 2 sentences as a SUM OF COSINE SIMILARITY between their tokens embeddings
![image](https://user-images.githubusercontent.com/30425824/145587220-a851927f-7775-48dc-ab15-4662ad2052dd.png)

BERTSCore addresses 2 COMMON PIT FALLS in N-GRAM-BASED (BLEU) metrics:

N-Gram based methods often fail to ROBUSTLY match paraphrases.
Ex: Reference Sentence: "People like foreign cars"
Prediction1 : "People like visiting places abroad"
Prediction2 : "Consumers prefer imported cars"

BLEU (STRING MATCHING) and METEOR (HEURISTICS MATCHING) give higher score to Prediction1 and lower score to Prediction2. This results in performance underestimation of semantically correct phrases.

Fail to capture distant dependencies and penalize semantically critical ordering changes For example, given a small window of size two, BLEU will only mildly penalize swapping of cause and effect clauses (e.g. A because B instead of B because A), especially when the arguments A and B are long phrases.

BERTSCORE with the contextualized embeddings can take care of: a) paraphrasing and b) effectively capture distant dependencies and ordering

## Exceptions from results in Code ##
a. BertScore   

![image](https://user-images.githubusercontent.com/30425824/145590687-84e18d6a-7792-44f3-9b81-91d601a6ba6e.png)
![image](https://user-images.githubusercontent.com/30425824/145590805-9a6e4c4b-23f8-4757-aeb4-0ba70166395d.png)
