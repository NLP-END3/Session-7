# Session-7
End Session 3

Existing metrics for Natural Language Generation can be broadly categorized into using

1. N-gram Matching
2. Edit Distance
3. Embedding Matching or Learned functions

## Perplexity ##

Perplexity is just an exponentiation of the entropy!
Entropy is the average number of bits to encode the information contained in a random variable, so the exponentiation of the entropy should be the total amount of all possible information, or more precisely, the weighted average number of choices a random variable has.
For example, if the average sentence in the test set could be coded in 100 bits, the model perplexity is 2¹⁰⁰ per sentence





## BERT Score ##

BertScore computes the similarity of 2 sentences as a SUM OF COSINE SIMILARITY between their tokens embeddings

BERTSCore addresses 2 COMMON PIT FALLS in N-GRAM-BASED (BLEU) metrics:

N-Gram based methods often fail to ROBUSTLY match paraphrases.
Ex: Reference Sentence: "People like foreign cars"
Prediction1 : "People like visiting places abroad"
Prediction2 : "Consumers prefer imported cars"

BLEU (STRING MATCHING) and METEOR (HEURISTICS MATCHING) give higher score to Prediction1 and lower score to Prediction2. This results in performance underestimation of semantically correct phrases.

Fail to capture distant dependencies and penalize semantically critical ordering changes For example, given a small window of size two, BLEU will only mildly penalize swapping of cause and effect clauses (e.g. A because B instead of B because A), especially when the arguments A and B are long phrases.

BERTSCORE with the contextualized embeddings can take care of: a) paraphrasing and b) effectively capture distant dependencies and ordering
