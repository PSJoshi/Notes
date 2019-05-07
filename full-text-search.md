### Why full text search

If you fire query like:

SELECT * FROM table_name WHERE Foo LIKE '%Bar';

can not take advantage of index. It has to look at every single row and see if it matches.  A full text index can give you instant answer! Full text index can offer a lot of flexibility in terms of the order of matching words, how words are closer.

#### Stemming
A fulltext search can stem words. If you search for run, you can get results for "ran" or "running". Most fulltext engines have stem dictionaries in a variety of languages.

#### Weighted results
A fulltext index can encompass multiple columns.e.g. if you search for "peach pie", the index can include title, keywords and a body. Results that match the title can be weighted higher as more relevant and can be sorted to show near the top.

#### Disadvantages
A fulltext index can be potentially huge, many times larger than standard B-tree index. So, most hosted providers who offer database instances disable this feature or at least charge extra for it. 
Fulltext indexes can be slower to update. If the data changes a lot, there might be some lag updating indexes compared to standard indexes.

The following stackoverflow answer nicely explains what is the meaning of fulltext search.

In general, there is a tradeoff between "precision" and "recall". High precision means that fewer irrelevant results are presented (no false positives), while high recall means that fewer relevant results are missing (no false negatives). Using the LIKE operator gives you 100% precision with no concessions for recall. A full text search facility gives you a lot of flexibility to tune down the precision for better recall.

Most full text search implementations use an "inverted index". This is an index where the keys are individual terms, and the associated values are sets of records that contain the term. Full text search is optimized to compute the intersection, union, etc. of these record sets, and usually provides a ranking algorithm to quantify how strongly a given record matches search keywords.

The SQL LIKE operator can be extremely inefficient. If you apply it to an un-indexed column, a full scan will be used to find matches (just like any query on an un-indexed field). If the column is indexed, matching can be performed against index keys, but with far less efficiency than most index lookups. In the worst case, the LIKE pattern will have leading wildcards that require every index key to be examined. In contrast, many information retrieval systems can enable support for leading wildcards by pre-compiling suffix trees in selected fields.

Other features typical of full-text search are

* lexical analysis or tokenization—breaking a block of unstructured text into individual words, phrases, and special tokens
* morphological analysis, or stemming—collapsing variations of a given word into one index term; for example, treating "mice" and "mouse", or "electrification" and "electric" as the same word
* ranking—measuring the similarity of a matching record to the query string

Ref - https://stackoverflow.com/questions/224714/what-is-full-text-search-vs-like

### Hadoop-Spark-Elasticsearch
Hadoop is distributed file system which allows you to develop distributed data processing applications under map-reduce model.
Spark is a layer on the top of Hadoop which allows you to develop applications in scala or python and improves the performance of iterative process by a factor of 100.
Elasticsearch is a distributed RESTful search engine and uses NoSQL to store documents.
