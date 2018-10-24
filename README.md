# Japanese Word Similarity Dataset

## Data

We built a Japanese word similarity dataset including rare words.

We target verb, adjective, noun and adverb.

## Data construction

We constructed our dataset following the Stanford Rare Word Similarity Dataset
(RW) proposed by [Luong et al.
(2013)](http://nlp.stanford.edu/~lmthang/data/papers/conll13_morpho.pdf).

We extracted pairs of Japanese verbs (including sahen verb) and adjectives
(both i-adjective and na-adjective) from Kodaira et al.
(2016)'s [Evaluation dataset for Japanese lexical
simplification](https://github.com/KodairaTomonori/EvaluationDataset).

We employed a crowdsourcing service ([Lancers](http://www.lancers.jp)) to
recruite 10 annotators to assign 11 levels of similarity for word pairs.

0 (most dissimilar) - 10 (most similar)

## Entry

The sample of the dataset is as follows:

word1 | word2 | mean(remove_extreme_annotator) | sub1 | sub2 | ... | sub9 | sub10 | mean |
------------ | ------------- | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | 
排除する | 無視する  | 4.6 | 5 | 3 | ... | 5 | 6 | 4.8 |
排除する | 除外する  | 6.6 | 7 | 6 | ... | 5 | 7 | 6.8 |

mean(remove_extreme_annotator) : average of the similarity scores assigned by annotators(the annotator attached an extreme value are removed)

mean : average of the similarity scores assigned by annotators

sub* : the similarity score for each annotator

## Helper script in src

The src directory contains a helper script to calculate Spearman's  rank
correlation coefficient used in our LREC paper.

Specifically, we learned word vectors from Japanese Wikipedia to
calculatethe  rank correlation coefficient between the similarity of
word pairs and mean of annotated scores.

## License

Our work is licensed under Creative Commons Attribution-ShareAlike 3.0
Unported (CC BY-SA 3.0).

## Citation

If you use our dataset, please cite our LREC paper.

1. Yuya Sakaizawa and Mamoru Komachi. Construction of a Japanese Word
Similarity Dataset. In 11th edition of the Language Resources and Evaluation
Conference (LREC 2018), pp.948-951. May 2018.
2. Yuya Sakaizawa and Mamoru Komachi. Construction of a Japanese Word Similarity Dataset. In arXiv e-prints, 1703.05916 (5 pages). March 2017.

## References

1. Tomonori Kodaira, Tomoyuki Kajiwara, Mamoru Komachi. Controlled and
Balanced Dataset for Japanese Lexical Simplification. ACL 2016 Student
Research Workshop, pp.1-7. August 2016.
2. Minh-thang Luong, Richard Socher, Christopher D. Manning. Better Word Representations with Recursive Neural Networks for Morphology. CoNLL 2013, pp.104-113. August 2013.

---------------
  Tokyo Metropolitan University
  
  Yuya Sakaizawa
  
  e-mail: ksf.doingmorewithless-at-gmail.com

---------------

