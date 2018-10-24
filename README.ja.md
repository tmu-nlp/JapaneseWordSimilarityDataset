# 日本語単語類似度データセット (JapaneseWordSimilarityDataset)

データ：

低頻度語を含む日本語に関する類似度データセットを構築しました。

対象とした品詞は、動詞 (verb)・形容詞 (adj)・名詞 (noun)・副詞 (adv)になっています。

データ作成：

[Luong et al. (2013)](http://nlp.stanford.edu/~lmthang/data/papers/conll13_morpho.pdf) の Stanford Rare Word Similarity Dataset (RW) のデータセット構築を参考にデータセットの作成を行いました。

小平ら (2016) によって提案されている[語彙平易化システムの評価データセット](https://github.com/KodairaTomonori/EvaluationDataset) から日本語動詞ペア・形容詞ペアを抽出しました（動詞・サ変動詞を合わせて動詞,形容詞・形容動詞を合わせて形容詞と表現しています）。

クラウドソーシング ([Lancers](http://www.lancers.jp)) を利用して、10 人のアノテータに11段階で単語ペアの類似度を付与してもらいました。

0（類似していない） 〜 10（類似している）

## データの内容

以下の例のようにデータが配列されています。

word1 | word2 | mean(remove_extreme_annotator) | sub1 | sub2 | ... | sub9 | sub10 | mean
------------ | ------------- | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |  ------------  |
排除する | 無視する  | 4.6 | 5 | 3 | ... | 5 | 6 | 4.8 |
排除する | 除外する  | 6.6 | 7 | 6 | ... | 5 | 7 | 6.8 |

mean(remove_extreme_annotator) : 極端な値を付けやすいアノテータを削除した上で計算した類似度の平均

mean : アノテータが付けた類似度の平均

sub* : 各アノテータが付けた類似度

## src の内容

論文内でスピアマンの順位相関係数を計算するために使用したスクリプトが入っています。

実際の実験は Wikipedia で学習した単語ベクトルから単語ペア間の類似度を計算して平均の値との順位相関を算出しています。

## ライセンス

Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)
にてご利用いただけます。

## 論文

1. Yuya Sakaizawa and Mamoru Komachi. Construction of a Japanese Word
Similarity Dataset. In 11th edition of the Language Resources and Evaluation
Conference (LREC 2018), pp.948-951. May 2018.
2. Yuya Sakaizawa and Mamoru Komachi. Construction of a Japanese Word
Similarity Dataset. In arXiv e-prints, 1703.05916 (5 pages). March
2017.（v2 が上記と同一）
3. 堺澤勇也, 小町守. 日本語動詞・形容詞類似度データセットの構築. 言語処理学会第22回年次大会, pp.262-265. March 2016.

## 参考文献

1. Tomonori Kodaira, Tomoyuki Kajiwara, Mamoru Komachi. Controlled and
Balanced Dataset for Japanese Lexical Simplification. ACL 2016 Student
Research Workshop, pp.1-7. August 2016.
2. 小平知範, 梶原智之, 小町守. 均衡コーパスを用いた日本語語彙平易化データセットの構築. 言語処理学会第22回年次大会, pp.258-261. March 2016.
3. Minh-thang Luong, Richard Socher, Christopher D. Manning. Better Word Representations with Recursive Neural Networks for Morphology. CoNLL 2013, pp.104-113. August 2013.

---------------
  首都大学東京大学院システムデザイン研究科情報通信システム学域小町研究室  
  
  堺澤勇也
  
  e-mail: ksf.doingmorewithless-at-gmail.com

---------------

