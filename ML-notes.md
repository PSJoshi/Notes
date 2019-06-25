## Machine learning vs traditional programming

Artifical intelligence is an umbrella that contain other realms like image processing, cognitive science, neural network and much more.
The core idea is computer not only just use pre-written algorithm, but learns how to solve the problem itself.

Arthur Samuel - definition - ML is a field of study that gives computers the ability to learn without being explicitly programmed.

In traditional programming you hard code the behaviour of the program. In machine learning, you leave a lot of that to machine to learn from data.

ML is used in cases where traditional programming strategy falls behnind and it's not enough to fully implement a certain task.e.g. prediction of currency price.. It depends on many factors like country, location, its image, GDP etc. To improve accuracy, you may need many parameters. If you write your program logic with fixed parameters, your algorithm accuracies will not grow.
So, instead of developing algorithm on its own, you need to collect historical data that can be used for model building.
The end result is a model can predict the result more accurately.

Ref - https://towardsdatascience.com/machine-learning-vs-traditional-programming-c066e39b5b17

## Data science vs Machine learning
ML and statistics are part of data science. The word 'learning' means it depends on some kind of data. This encompasses many technique such as regression, naive bayes or clustering. But all the techniques does not fit in this category. e.g. unsupervised clustering- clusters are formed without any prior knowledge. Humans will label the clusters.

Data science is more than ML. Data in data science may not come from machine or mechanical process. It encompasses many things - many aspects of data processing and not just algorithmic or statisitcal aspect - data integration, data visualization, data engineering, data in production mode, data driven decisions etc.

### Machine learning vs rule based learning
ML and rule based systems are widely used to make inferences from data. Forget the hype about ML, rule based systems have a place in system design.
Rule-based system are simple kind of artifical intelligence which uses a series of IF-THEN-ELSE statements to guide computer to a conclusion.
Rule based system have set of facts and set of rules.

Set-of-facts: It is a knowledge base. It' used for formation of rules.
Set-of-rules: It's a rule engine. Rules describe the
relationship between IF and THEN statements.

Full rule based systems are built from combined knowledge of human experts in problem domain. The domain experts specify all the steps to make a decision and how to handle special cases. The number of special rule cases may grow over a period of time!

In machine learning, instead of emulating decision making process of an expert, you take outcomes from experts. Focussing on outcomes (rather than decision making process) makes machine learning more flexible and less suspectible to  problems in rule based system.
ML also uses probabilistic and stastical methods rather than rules. The basic moto is - given that we know about historical outcomes, what can we say about future outcomes.
Ref - https://deparkes.co.uk/2017/11/24/machine-learning-vs-rules-systems/

### ML vs Deep learning
The main difference between deep and machine learning is, machine learning models become better progressively but the model still needs some guidance. If a machine learning model returns an inaccurate prediction then the programmer needs to fix that problem explicitly but in the case of deep learning, the model does it by himself. Automatic car driving system is a good example of deep learning.

Deep learning and machine learning both are the subsets of AI.
“AI is a ability of computer program to function like a human brain ”

Machine learning is empowering computer systems with the ability to “learn”. The intention of ML is to enable machines to learn by themselves using the provided data and make accurate predictions. ML is a subset of artificial intelligence; in fact, it’s simply a technique for realizing AI.
Ref - 
* https://towardsdatascience.com/clearing-the-confusion-ai-vs-machine-learning-vs-deep-learning-differences-fce69b21d5eb
* https://emerj.com/ai-glossary-terms/what-is-machine-learning/


## Deep learning disadvantages
* it does not work well with small data. For high accuracies, you need large datasets.
* In practice, it is hard and expensive. you need computing and data resources along with human expertize.
* Deep learning is not easily interpreted.It's difficult to validate. Hyper-parameters and network design are also challenge due to absence of theortical foundation.

## Disadvantges of ML
* ML requires massive data sets to train and these should be unbiased and of good quality. So, you have to wait for data to be generated.
* ML requires enough time to let the algorithm to learn to achieve sufficient accuracy and relevancy. So, it needs massive computing and storage resources.
* Selection of right algorithm and interpretation of results is major challenge.
* ML learning is autonomous and is suspectible to errors. Suppose you train your algorithm on small datasets and it may end up making biased predictions.

Ref - https://data-flair.training/blogs/advantages-and-disadvantages-of-machine-learning/
