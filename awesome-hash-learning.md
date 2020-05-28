[AWESOME] Unsupervised Hash Learning
---
## Locally Sensitive Hashing

TrendMicro Locally Sensitive Hashing (2013) 
* [paper](https://documents.trendmicro.com/assets/wp/wp-locality-sensitive-hash.pdf), [ppt](https://github.com/trendmicro/tlsh/blob/master/TLSH_Introduction.pdf), [code](https://github.com/trendmicro/tlsh)
* N-gram별로 locally하게 (좁은 range의)hash를 뜨고, quantized hash histogram을 fingerprint로 간주
* 고정 크기의 fingerprint 간에 유사성으로 O(N) retrieval

Locally sensitive Hash (1998) 
* [paper](https://www.theoryofcomputing.org/articles/v008a014/v008a014.pdf), [lecture1](http://web.stanford.edu/class/cs246/slides/03-lsh.pdf), [lecture2](http://web.stanford.edu/class/cs246/slides/04-lsh_theory.pdf), [code of datasketch](https://github.com/ekzhu/datasketch/blob/master/datasketch/lsh.py)
* MinHash + band technique
* AND-OR, OR-AND construction cascade 로 원하는 유사쌍 탐색의 fpr, recall 을 얻는다.
* Euclidean distance와 Cosine distance 등으로 일반화할 수 있다.


LSH forest (2005) 
* [paper](http://infolab.stanford.edu/~bawa/Pub/similarity.pdf)
* 기존 LSH는 data-dependent하게 튜닝할 파라미터가 많았다(최소유사거리 문턱값, band당 minhash수)
    * 데이터 크기가 커지면 minhash를 늘려야 한다.
    * Neighborhood 대한 거리 민감도가 국부적으로 다를 수 있다(어떤 클러스터에서는 밀집해서, 어떤 곳에서는 더 sparse하게). 이 경우 최소 유사거리를 여러 개 운영해야 할 경우도 있었다.
* 이를 보완하기 위해 prefix-tree기반의 LSH tree를 다수 운영하는 것이 LSH forest이다. 
    * Prefix tree의 특성으로 말미암아 다양한 # minhash 크기 지원이 가능

LSH ensemble (2016) 
* [paper](http://www.vldb.org/pvldb/vol9/p1185-zhu.pdf)

## Hash Learning (TBD)

## Discrete Representation Learning (TBD)