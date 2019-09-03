## TF-IDF

TF-IDF is a method to generate features from text by multiplying the frequency of a term (usually a word) in a document (the Term Frequency, or TF) by the importance (the Inverse Document Frequency or IDF) of the same term in an entire corpus. This last term weights less important words (e.g. the, it, and etc) down, and words that don’t occur frequently up. 

IDF is calculated as:

IDF(t) = log_e(Total number of documents / Number of documents with term t in it).

An example (from www.tfidf.com/) illustrates the concept nicely:

Consider a document containing 100 words in which the word cat appears 3 times. The term frequency (i.e., tf) for cat is then (3 / 100) = 0.03. Now, assume we have 10 million documents and the word cat appears in one thousand of these. Then, the inverse document frequency (i.e., idf) is calculated as log(10,000,000 / 1,000) = 4. Thus, the Tf-idf weight is the product of these quantities: 0.03 * 4 = 0.12.

TF-IDF is very useful in text classification and text clustering. It is used to transform documents into numeric vectors, that can easily be compared.

For string matching, algorithms like Jaro-Winkler or Levenshtein distance measures are used commonly. However, these algorithms are not suitable to find string similarities in large datasets as their responses are slow. Using TF-IDF with N-grams can be used to find similar strings as it transforms the problem into matrix multiplication problem and is computationally much cheaper.
