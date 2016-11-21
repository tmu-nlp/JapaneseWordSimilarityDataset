# JapaneseWordSimilarityDataset
###日本語単語類似度データセット

データ：

低頻度語を含む日本語に関する類似度データセットを構築しました。

対象とした品詞は、動詞(verb)・形容詞(adj)・名詞(noun)・副詞(adv)になっています。

データ作成：

[Luong et al. (2013)](http://nlp.stanford.edu/~lmthang/data/papers/conll13_morpho.pdf) のStanford Rare Word Similarity Dataset (RW) のデータセット構築を参考にデータセットの作成を行いました。

小平ら (2016) によって提案されている[語彙平易化システムの評価データセット](https://github.com/KodairaTomonori/EvaluationDataset) から日本語動詞ペア・形容詞ペアを抽出しました（動詞・サ変動詞を合わせて動詞,形容詞・形容動詞を合わせて形容詞と表現しています）。

クラウドソーシング ([Lancers](http://www.lancers.jp)) を利用して、5人のアノテータに11段階で単語ペアの類似度を付与してもらいました。

0（類似していない） 〜 10（類似している）

## データの内容

以下の例のようにデータが配列されています。

word1 | word2 | mean | sub1 | sub2 | sub3 | sub4 | sub5
------------ | ------------- | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ 
排除する | 無視する  | 4.6 | 5 | 3 | 4 | 5 | 6
排除する | 除外する  | 6.6 | 7 | 6 | 8 | 5 | 7

mean : アノテータが付けた類似度の平均

sub* : 各アノテータが付けた類似度


### 参考文献

1. 日本語動詞・形容詞類似度データセットの構築 (2016)
2. Better Word Representations with Recursive Neural Networks for
Morphology (Luong et al. (2013))
3. 均衡コーパスを用いた日本語語彙平易化データセットの構築（小平ら (2016)）

---------------
  首都大学東京・システムデザイン・情報通信スステム・小町研究室  
  
  堺澤勇也
  
  e-mail: sakaizawa-yuya-at-ed.tmu.ac.jp

---------------

