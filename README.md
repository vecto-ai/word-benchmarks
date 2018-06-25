# Benchmarks for intrinsic evaluation word embeddings

## **THE DEVELOPMENT STOPPED, PROJECT TRANSFERRED TO [VECTO](https://github.com/vecto-ai)**

### 1. Word semantic similarity ####

This method is based on an idea that the distances between words in an embedding space could be evaluated through the human heuristic judgments on the actual semantic distances between these words (e.g., the distance between *cup* and *mug* defined in an continuous interval {0,1} would be 0.8 since these words are synonymous, but not really the same thing). The assessor is given a set of pairs of words and asked to assess the degree of similarity for each pair. The distances between these pairs are also collected in a word embeddings space, and the two obtained distances sets are compared. The more similar they are, the better are embeddings

1. **SimVerb-3500**, 3 500 pairs of verbs assessed by semantic similarity (that means that pairs that are related but not similar have a fairly low rating) with a scale from 0 to 4.
2. **MEN** (acronym for Marco, Elia and Nam), 3 000 pairs assessed by semantic relatedness with a discrete scale from 0 to 50.
3. **RW** (acronym for Rare Word), 2 034 pairs of words with low occurrences (rare words) assessed by semantic similarity with a scale from 0 to 10.
4. **SimLex-999**, 999 pairs assessed with a strong respect to semantic similarity with a scale from 0 to 10.
5. **SemEval-2017**, 500 pairs assessed by semantic similarity with a scale from 0 to 4 prepared for the *SemEval-2017 Task 2* (*Multilingual and Cross-lingual Semantic Word Similarity*). Notably, dataset contains not only words, but also collocations (e.g. *climate change*).
6. **MTurk-771** (acronym for Mechanical Turk), 771 pairs assessed by semantic relatedness with a scale from 0 to 5.
7. **WordSim-353**, 353 pairs assessed by semantic similarity (however, some researchers find the instructions for assessors ambiguous with respect to similarity and association) with a scale from 0 to 10.
8. **MTurk-287**, 287 pairs assessed by semantic relatedness with a scale from 0 to 5.
9. **WordSim-353-REL**, 252 pairs, a subset of WordSim-353 containing no pairs of similar concepts.
10. **WordSim-353-SIM**, 203 pairs, a subset of WordSim-353 containing similar or unassociated (to mark all pairs that receive a low rating as unassociated) pairs.
11. **Verb-143**, 143 pairs of verbs assessed by semantic similarity with a scale from 0 to 4.
12. **YP-130** (acronym for Yang and Powers), 130 pairs of verbs assessed by semantic similarity with a scale from 0 to 4.
13. **RG-65** (acronym for Rubenstein and Goodenough), 65 pairs assessed by semantic similarity with a scale from 0 to 4.
14. **MC-30** (acronym for Miller and Charles), 30 pairs, a subset of RG-65 which contains 10 pairs with high similarity, 10 with middle similarity and 10 with low similarity.

### 2. Word analogy

This evaluation method (in certain works also called *analogical reasoning*, *linguistic regularities* and *word semantic coherence*) is the second most popular method of word embeddings evaluation. It is based on the idea that arithmetic operations in a word vector space could be predicted by humans: given a set of three words, $a$, $a*$ and $b$, the task is to identify such word $b*$ that the relation $b$:$b*$ is the same as the relation $a$:$a*$. For instance, one has words $a=Paris$, $b=France$, $c=Moscow$. Then the target word would be $Russia$ since the relation $a:b$ is $capital:country$, so one needs need to find the capital of which country is *Moscow*.

1. **WordRep**, 118 292 623 *analogy questions* (4-word tuples) divided into 26 semantic classes, a superset of *Google Analogy* with additional data from WordNet.
2. **BATS** (acronym for Bigger Analogy Test Set), 99 200 questions divided into 4 classes (*inflectional morphology*, *derivational
morphology*, *lexicographic semantics* and *encyclopedic semantics*) and 10 smaller subclasses.
3. **Google Analogy** (also called Semantic-Syntactic Word Relationship Dataset), 19 544 questions divided into 2 classes (*morphological relations* and *semantic relations*) and 10 smaller subclasses (8 869 semantic questions and 10 675 morphological questions).
4. **SemEval-2012**, 10 014 questions divided into 10 semantic classes and 79 subclasses prepared for the  *SemEval-2017 Task 2* (*Measuring Degrees of Relational Similarity*).
5. **MSR** (acronym for Microsoft Research Syntactic Analogies), 8 000 questions divided into 16 morphological classes.
6. **SAT** (acronym for Scholastic Aptitude Test), 5 610 questions divided into 374 semantic classes.
7. **JAIR** (acronym for Journal of Artificial Intelligence Research), 430 questions divided into 20 semantic classes. Notably, dataset contains not only words but collocations (like *solar system*).

### 3. Concept categorization

This method (also called *word clustering*) evaluates an ability of word embeddings space to be clustered. Given a set of words, the task is to split it into subsets of words belonging to different categories (for example, for words $dog$, $elephant$, $robin$, $crow$ the first two make one cluster which is $mammals$ and the last two form another second cluster which is $birds$; the cluster name is not necessary to be formulated). The amount of clusters should be defined. Possible critique of such method could address the question of either choosing the most appropriate clustering algorithm or choosing the most adequate metric for evaluating clustering quality.

1. **BM** (acronym for Battig and Montague), 5 321 words  divided into 56 categories.
2. **AP** (acronym for Almuhareb and Poesio), 402 words divided into 21 categories.
3. **BLESS** (acronym for Baroni and Lenci Evaluation of Semantic Spaces), 200 words divided into 27 semantics classes. Despite the fact that BLESS was designed for another type for evaluation, it is also possible to use this dataset in a word categorization task.
4. **ESSLLI-2008** (acronym for the European Summer School in Logic, Language and Information), 45 words divided into 9 semantic classes (or 5 in less detailed categorization); the dataset was used in a shared task on a *Lexical Semantics Workshop on ESSLI-2008*.

### 4. Outlier word detection

This method evaluates the same feature of word embeddings as the word categorization method (it also proposes clustering), but the task is not to divide a set of words into certain amount of clusters, but to identify a semantically anomalous word in an already formed cluster (for example, for a set $\{orange, banana, lemon, book, orange\}$ which are mostly fruits, the word $book$ is the outlier since it is not a fruit).

1. **8-8-8 Dataset**, 8 clusters, each is represented by a set of 8 words with 8 outliers.
2. **WordSim-500**, 500 clusters, each is represented by a set of 8 words with 5 to 7 outliers.
