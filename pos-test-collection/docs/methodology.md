# Methodology

## POS Test Collection

The pos-test-collection was evaluated on two early taggers, Stanford and TnT, and three versions of spaCy (0.101, 2.2.3, and 3.7.5).

The test consists of 500 words, each of which have at least two parts of speech.   There are 1012 sentences that correspond to each word+pos pair.

I also assessed robustness by converting the sentences to uppercase and tagging them again.

For version 2.2.3 I used the `en_core_web_sm` model, and for version 3.7.5 I used the `en_core_web_trf` (transformer) model.

## Tokenization

For the Stanford and TnT taggers, the sentences were tokenized using a tokenizer for the Penn Treebank.  For the spaCy taggers I used the tokenization provided by spaCy.

## Dataset Format

The resource is provided as a csv file (comma separated values).

The fields begin with:
    Target Word, Target POS, Sentence
    
and then there are two fields for each tagger (Stanford, TnT, and the three versions of spaCy), which indicate the tag that was provided, and whether the tag was correct.  After the field for the transformer tag, I give three results for the uppercase assessment: the result using the Stanford Tagger, the result using the TnT tagger, and the result with spaCy 3.7.5 using the transformer model.


## Wikipedia Assessment

I found that more than 80% of the remaining error on the test involves words that could be adjectives.  I created a resource to evaluate tagging further on a token basis, and I made an initial assessment of words that were incorrectly tagged on the test.  I used a download of the English Wikipedia for this purpose.  The download was done on May 25th, 2007.  I have a more recent download, and as future work I want to see how the distribution of part of speech tags changes over time.  I extracted all sentences in the Wikipedia that contained one of the 500 words in the test collection.  All of the sentences were tagged using the `en_core_web_sm` model.  A subset of 15 words was assessed which are ambiguous between adjectives and other parts-of-speech.  I compared the results using the small language model with a tagging that used the `en_core_web_trf` model (a transformer).  I evaluated the conditions where the taggers agreed and where they disagreed.  The set of words I evaluated and the judgments I made is given in the file `wikipedia-assessment-of-15-words.txt`.


