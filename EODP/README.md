# EODP STUDY GUIDE SUMMARY
##### a full summary for the question that list on study guide

## LECTURE 1 ( concept of data wrangling)
1. what is data wrangling?
    - The process of organising, converting, mapping data from one format into another
2. what activities it encompasses(include)
    - This may include activites such as data integration, enrichment, aggregation structuring, storage, visualisation and publishing.
3. why it is useful?
	- normally the raw data is not usable, including some wrong data and missing value
	- we need to build connection beteween different data set in order to  implement anaylsis
4. why it is challenging
    - reformatting and validating data requires transforms, which is can be difficult to specify and evaluate.
    - converting data values to different types sometimes quite challenge.
5. why it is done
    - make data more accessible
    - have better insights about data



## LECTURE 2 AND LECTURE 3 (re, XML, HTML, JSON)

1. How is data stored and in what formats
    - Structured: Relational databses, CSV
	- Unstructured: text -- no Structure, harder to organise, lacks regularity and
    decomposable internal structure. Also very hard to process/search for information.
	- Semi-structured: HTML, XML, JSON
2. the role that relational databases play in data wrangling
	- highly structured so that easier to analyse, easier to query, easier to store,
    easier to clean, maintain consistency and security, especiall with multiple users
	- once data is into a relational database, it is easier to wrangle,
    but maybe hard to load it there in the first place.
3. regular expression(re) related
	- '.' matches any character
	- '^' matches start of string
	- '$' matches end of string
	- '*' zero or more repetitions
	- '+' one or more repetitions
	- '|' the or operator, used in conjunction with parantheses ()
	- '\[\]' a set of character, e.g. \[abcd\] or \[a-zA-Z\]
	- JA the pattern J followed immediately by A
	- JA* the pattern J followed by zero or more occurences of A
	- (J|A)* Zero or more repetitions of 'J' or 'A'
	- (J|A)+ One or more repetitions of 'J' or 'A' can also be writen as \[JA\]+
4. what is csv file, what is a spreadsheet, and difference between them
	- csv is comma separated values
	- spreadsheet is an electronic document in which data is arranged in the rows
    and columns of a grid and can be manipulated and used in calculations.
    For example, Microsoft Excal document.
	- difference: csv file is human readable, versus binary xls(Excel)
	- csv lack the formatting information of an xls file
5. Motivation for XML and XML namespaces
    - XML
    	- **both human and mechine readable format.**
        - more flexible than csv
        - allowing search engines or other tools to operate over a range of documents that vary in many respects but use common names for common element types
    - XML namespace
    	- namespace declaration are used to qualify names with URI's.
    A URI uniquely identifies a resource on the Web.
    Notice that a URI doesn't have to refer to a real Web resource.
    	- namespace can be used to descrive both elements and attributes.
6. differences between XML and HTML
	- HTML tags are predefined tags where as XML tags are user defined tags.
	- HTML tags are limited number of tags where as XML tags are extensible and user defined.
	- HTML tags are case insensitive whereas XML tags are sensitive.
	- HTML tags are meant for displaying the data but not for describing the data
    where as XML tags are meant for describing the data.
	- HTML focuses on how data looks whereas XML focuses on what data is.
	-  Use HTML for data that will be viewed in browser by humans, formatdd nicely.
     XML for applications such as data exchange, integration, export
     into other formats. where semantics is needed, etc.
7. difference between XML attributes and elements, and when should use one is preferred over the other
	- attributes are designed to contain data related to specific element or
    provide additional information about elements
	- elements is the basic building block for XML, it can behave as
    containers to hold informations.
	- An atrribute is something that is self-contained, i.e., a color, and ID, a name. Whereas, an element is something that does or could have attributes of its own or contain other elements.
8. XML documents example with attributes and name space
	~~~XML
	<?xml version="1.0" encoding="utf-8"?>

	<q:queen title="Queen Elizabeth II" marriedTo="Philip, Duke of Edinburgh"
	 xmlns="http:info.gov.uk"
	 xmlns:q="http://queenly.gov.uk"
	 xmlns:p="http://princely.gov.uk"
	 xmlns:ps="http://princessly.gov.uk"
	>
		<p:prince title="Charles, Prince of Wales" marriedTo="Lady Diana Spencer">
			<p:prince title="Prince William of Wales" />
			<p:prince title="Prince Henry of Wales" />
		</p:prince>
		<ps:princess title="Anne, Princess Royal" />
		<p:prince title="Andrew, Duke of York" />
		<p:prince title="Edward, Earl of Wessex" />
	</q:queen>
	<!-- notice that the indentation here is not necessary >
	~~~
9. XML documents namespace syntax and exampe
	- xmlns:prefix="namespaceURI", for example, xmlns:a="http://info.gov.uk"
	- example was shown above
10. Why we need namespace?
    - define the scope of attributes or elements.
    - to say somethings meaningful.
    - allow multiple mark-up languages to be combined
    - **same as motivation of namespace i think**
11. Difference between XML and JSON, and where they suit
	- JSON dont have tags, instead, it use brackets to structure data
	- JSON is smaller and more compact/lightweight than XML and easier to parse,
    which originally designed to speed up interactions. Widely used for storing
    data in noSQL database.
	- XML allows complex schema definitions (via re) and allows formal validation.
    Also, XML makes you consider the data design more closely.
12. eample of making JSON doc and converting to XML
  ~~~JSON
  {
      "id": "book001",
      "author": "Salinger, J. D.",
      "title": "The Catcher in the Rye",
      "price": "44.95",
      "language": "English",
      "publish_date": "1951-07-16",
      "publisher": "Little, Brown and Company",
      "isbn": "0-316-76953-3",
      "description": "A story about a few important days in the life of Holden Caulfield"
  }
  ~~~

  ~~~XML
  <?xml version="1.0" encoding="utf-8"?>
  <book id="book001">
    <author>Salinger, J. D.</author>
    <title>The Catcher in the Rye</title>
    <price>44.95</price>
    <language>English</language>
    <publish_date>1951-07-16</publish_date>
    <publisher>Little, Brown and Company</publisher>
    <isbn>0-316-76953-3</isbn>
    <description>A story about a few important days in the life of Holden Caulfield</description>
  </book>
  ~~~
13. the purpose of using schemas for XML and JSON data
    - for JSON is to describe the structure and validation constraints of the JSON file

    - for XML, its more flexible, which can be user defined, and mianly
      for describing more complex data structure.

      

## LECTURE 4

1. the motivation behind data preprocessing and data cleaning
    - to impove the data quality from the following perspectives.
    - Accuracy: correct or wrong, accurate or not.
    - Completeness: not recorded, unavilable.
    - Consistency: discrepancies in representaion.
    - Timeliness: updated in timely way.
    - Believability: Do I trust the data?
    - Interpretability: How easily can I understand the data.
2. details about each step of data pre-preprocessing
    - data cleaning: transfer the raw data to useable data.
    - data integration: combine similar data from each dataset.
    - data reduction: remove some unwanted or redundent data. Maybe delete some real data or delete some features.
    - data transfermation: maybe implement data transfermation or data normalization.
3. terminologies explain: features, attributes, instances, objects.
    - features: the property of the data, normally is the columns of the data. For example, the height and weight of a person.
    - attributes: same as features
    - instances: data items (for the above example, just each person), normally represent number of rows
    - objects: same as instances
4. the difference between categorical/discrete features versus continuous features
    - categorical features and discrete features are the same things. they normally imply individually separate features. For example, gender.
    - continuous features are not restricted to separate values, for example, the height of people.
5. why data might be missing, and the possible causes
    - malfunction of equipment (e.g. sensor)
    - not recorded due to misunderstanding
    - May not be considered important at time of entry
    - Deliberate
    - The consequence of missing data: May break application data that are not expecting it, less power for later anaylsis, may bias later anaylsis.
6.  difference between data missing completely at random versus data missing
not completely at random
    - Data are missing independently of observed and unobserved data
    - not at random is that the people who don't respone to the survey.
7. understand the following strategies for handling missing data and their relative advantages/disadvantages (delete all instances with a missing value, manual correction, imputation)
    - delete all instance with a missing value: easy to analysis the new complete data but may produce bias on anaylsis if new sample size is small or a structure exists in the missing data.
    - manual correction: A human eyeballs the missing value and fills it in using their expert knowledge. the missing data might be filled with more percise data, but whne the dataset becomes larger this becomes a really time consuming method.
    - imputation: replace the missing value with the substitute one. After imputing all missing values, one can use standard analysis techniques for complete dataset.The drawbacks are listed blow.
8. understand the following strategies for imputation of missing values and their relative advantages/disadvantages (fill in with zeros, fill in with mean/median value, fill in with category
mean)
    - imputation (fill in with zero or similar): It's simple, and won't break application programs, but limited utility for analysis.
    - imputation (fill in with mean value): can be good for supervised classification, and apply separately for each atrribute. However, it reducces the varience of the feature, it may creates a incorrect view of the distribution for that attributes. Also, the relationships to other features changes.
    - imputation(fill in with category mean): if the survey took by both gender and one of peroson's age is missing, we only compute the age mean for its gender, instead of all gender. Might become more percise, but still hold the similar drawback as fill in with mean value. Eespecially when the dataset is small.



## LECTURE 4 AND 5: Outliers
1. the importance of finding outliers and give concrete examples where this
would be useful
    - importance: they can potentially skew or bias any analysis performed on the dataset. Therefore, it is very important to deal with them.
    - Application:
        - credit card fraud detection (change in behavior)
        - telecom fraud detection
        - medical analysis (unusual test results)
        - sports (identifying exceptional talent)
2. what is Outliers
    - A data object that deviates significantly from thenormal objects as if it were generated by a different mechanism
3. the difference between a global outlier and a contextual outlier
    - global outlier: significantly deviate from the rest of the data set
    - contextual outlier: significantly deviate from the give contextual, for example, 5 degree for human body temperature.
4. Tukey Boxplot
    - Outlier(filled black) area: \>3\*IQR above third quartile or \>3\*IQR below 1st quartile (IQR is the distance between first and third quartile).
    - Suspect Outlier(open black) area: \>1.5\*IQR above third quartile or \>1.5\*IQR below 1st quartile.
5. Histograms
    - advantage: can clearly shows the distribution of the data, and outlier can be found by eyeballing.
    - disadvantages: Hard to choose an appropriate bin size for histograms,too small bin size will results in normal objects in empty or rare bins, false positive. Too big bin size will results in outliers in some frequent bins, false negative.



## LECTURE 5 AND 6 : RECOMMANDER SYSTEM

1. what is a recommander system
    - normally is a system that give some advise of what should buy to the customer based on what they bought and what they like.
2. collaborative filtering
    - make predictions about a user's missing data according to the behaviour of many other users
    - User based methods: Identify like-minded users
    - Item based methods: Identify similar items
    - Model (matrix) based methods: Solve an optimization problem and identify latent factors
3. Method 1 and Method 2
    - Method1: compute mean value for each user (2 in total in this example), and then compute and summing Euclidean distance between resulting vector. But it may change the distribution of the data.
    - Method2:compute and sum Euclidean distance between vectors, summing only pairs without missing values. Scale the result, according to percentage of pairs with a missing value, for example, if 6 results in total but 2 are missing, then the sum should be scaled up by $\frac{6}{(6-2)}​$ . when there are a lot of missing value, method 2 won't work.
4. when performing user-user similarity, understand how to select neighbors and make a prediction of the missing item
    - Use a method to calculate the similarity between you and other users.
    - Then select the top k similar users and find the similarity.
    - Then predict the missing value based on top k similar users.
    - **but how to predict?** (use weighted average, detailed calculations not examinable)
5. Item-Item based
    - search for simiarities among items
    - all computations can be done offline
    - item-item similarity is more stable than user-user similarity which no need for frequent updates
6. be able to explain scenarios where recommender systems i) are likely to make incorrect recommendations, ii) over-recommend certain items, ii) under-recommend certain item
    - a circle, popular items been recommended $\rightarrow $ users are more likely to give high rates to those item $\rightarrow​$  the popularity of these items increse.
    - Recommendar system(RS) has no understanding of the items, over and under recommending naturally occur as the system performing its job.
    - The approaches to address this is adding an extra level to manipulate the results from RS, to ensure the diversity (cover a board range of items) to prevent users get the same recommendation all the time.
7. online and offline
    - online is more conputational intense, is a real time calculation.
    - offline did the calculation before, which means it will response quicker.



## LECTURE 6-8: visualisation

1. Motivation for visualisation
    - converting data into a visual format
    - Huamns are very good at analysing information in a visual format
    - Visualisation helps tell a story
2. Scatter plot or bubble plot
    - can find the cluster
    - can find how data are related, for example, positive related.
3. Heat map
    - This can be useful when objects are sorted according to class
    - Typically, features are normalized to prevent one attribute from dominating the plot
    - can find some pattern of data, for example, the busiest time of a supermarket.
4. parallel coordinates
    - advantages: easier to find similar and different items
    - disadvantages: the ordering is very important, bad ordering may results in hard to find difference or similarity between items. (see the lecture example of iris species)
5. why it is useful to perform clustering on a dataset and understand the
challenges involved
    - clustering is used to find structure in unlabeled data
    - it can discover which set of data shows similar pattern
    - clustering is a major task in data analysis and visualisation
    - what callenges
        - bad clustering may mislead us to find the structure of the data
        - define K
        - what is the formula for distance
        - what feature to use
6. why it can bu useful to normalise each feature into the range \[0,1\] before computing Euclidean distance between vectors
    - make sure they are in the same scale
    - well contribution of distance, instead of bigger number comtribute more.
7. k-means
    - algorithms (understand only)
        - select k seed points as the intial cluster centres
        - assign each object to the cluster with the nearest seed point
        - compute new seed points as the centroids of the clusters of the current partitioning (the centroid is the center, i.e., mean point, of the cluster)
        - go back to step 2, stop when the assignment does not change
    - the scenarios where the k-means algorithm may perform poorly
        - different runs of the algorithms will produce different results (local optimum)
        - different number of k can lead to different results
8. Hierachical clustering
    - steps: keeping merge the two data with shortest distance
    - dendrogram: A tree like diagram that reords the sequences of merges or splits.
9. explain why knowledge of clustering can assist in outlier detection
    - an outlier is expected to be far away from any groups of normal objects
    - each object is associated with exactly once cluster and its outlier score is equal to the distance from its cluster centre.
10. dissimilarity matrix
    - generate by find the distance for each feature for each item
    - VAT algorithm of reordering heatmap using the
        - find a object at first
        - find another object which close to the object that already have
        - and then you will get a order of that
        ~~~python
        #pseudo-code
        Given an N*N dissimilarity matrix D
        let K={1...N}, i=j={}
        pick the two least similar objects oa and ob from D
            P(1)=a; I={a}; J=K-{a}
        for r=2...N
            select(i,j):pair of most similar object oi and oj from D
                such that i in I, j in J
            P(r)=j; I= i U {j}; J=J-{j};
        ~~~
    - number of cluster can read from the heatmap of the ordering
11. dimensionality reduction
    - why?
        - reduce amount of time and memory required by data processing algorithms
        - allow data to be more easily visualised
        - help eliminate irrelevant features or normalise
    - IO
        - input: A dataset with N features and K objectss
        - output: A transformed dataset with n<<\N features and K objects, which n is often set to 2 or 3, so that the transformed dataset can be easily visualised.
    - how to perform
        - selecting a subset of the original features
        - generating a small number of new features
12. PCA
    - intuition: select less features but won't lost much informations to describe objects
    - motivation: it's a systematical way to implement dimensionality reduction which is much better than doing it manually
    - PCA Idea: find the new axis line with the largest variance among data
    - not much infomation lost when drop pc2 in 2D plot since it contains the least variance
    - disadvantage: can lose much information without care; takes too long for large dataset
    - Second Principal Component: orthogonal to the first, capture as much of the rest variability as possible



## LECTURE 11 AND 12: CORRELATION

1. Why is correlation important
    - discover relation
    - one step towards discovering causality
2. Advantage and disadvantages of Euclidean distance
    - advantages: easy to implement
    - disadvantages: objects can be represented with different measuer scales, and euclidean distance does not give a clear intuition about how well variable are correlated.
3. Pearson correlation
    - advantage: can easily find how data are related from the result
    - disadvantages: can only find linear relation
4. Mutual Information(MI)
    - detect non-linear, discrete features
    - preprocessing: continuous features are first discreted into bins (by domain knowledge or equal width or equal frequency)
    - Entropy is a measuer used to assess the amount of uncertainty in an outcome
    - about how to calculate MI is on the formula sheet
    - mutual information indicate that the amount of information about X we gain from knowing Y
    - Normalised mutual information: NMI can be used to provide a more interpretable measure of correlation than MI
    - difference with Pearson correlation: 
    1) MI can measure non-linear relation
    2) MI is very effective for use with discrete features



## LECTURE 13 AND 14: CLASSIFICATION AND REGRESSION TECHNIQUES

1. Classification
    - definiton: given a collection of records(training set), each record contains a set of attributes, one of the attributes is the class. Find a predictive model for class attributes as a function of the values of other attributes. **then what is the difference between this and prediction? Is this only implement on known data?** same thing! classification is to predict a category.
    - useful scenarios:
        - animal classification
        - bank classifying borrower
        - detecting tax fraud/tax cheats
2. Regression
    - given a collection of records each record contains a set of attributes, one of the attributes is the target variable. Regression is use other attributes to fit the target variable.
    - useful scenarios:
        - predict a number/discrete data.
        - predicting ice-creams consumption from temperature
        - predict activity level of a target gene
3. Decision Tree
    - How to specify test conditon
        - Depends on attribute types
            - nominal (e.g. family, sports, luxury for car)
            - ordinal (e.g.small, large, medium for size)
            - continuous (e.g. ranged data)
        - Depends on number of ways to split
            - 2-way split
            - Multi-way split
    - Splitting Based on norminal atrributes
        - Muti-way split: use many partitions as distinct values
        - Binary split: divides values into two subsets. Need to find optimal partitioning.
        - how good is a splits
            - the impurity of parent node(before splitting) - the sum of the impurity of its children nodes, notice that each child node need to scale by a parameter, which is (number of data points in this child node) / (number of data points in parent node).
            - the results called **gain**, the large the gain the better split this is.
    - Advantages
        - easy to Interpret
        - relatively efficient to construct
        - fast for making a decision about a test instance
    - Disadvantages
        - Sometimes this is too simple for data with complex structure
        - For complex datasets, the tree might grow very big and hard to understand by human
        - May behave strangely for some types of features, for example student ID
4. Metrics for performance evaluation
    - TP: should say yes, and we said yes.
    - FN: should say yes, but we said no.
    - FP: should say no, but we said yes.
    - TN: should say no, and we said no.
    - first letter represent the result we get is right(T) or wrong(F), the second letter represent how right or wrong we are.
    - Accuracy formula is on the fomula sheet
    - the accuracy may misleading at here, it may not detect any other value in a dataset but still get very high accuracy. Therefore, we need other concept here, for example, recall rate might be useful.
5. K-nearest neighbors(K-NN / KNN)
    - k-nearest neighbors of a record x are data points that have the k smallest distance to x
    - process
        - compute the distance to other training records
        - identify k nearest neighbors
        - use class labels of nearest neighbors to determine the class label of unknown record
    - Advantage
        - easier to calculate than dicision tree
	- can handle datasets with complex structure 
    - Disadvantages
        - hard to determine the size of k
            - if k is too small, sensitive to noise points
            - if k is too large, neighborhood may include points from other classes
	- classification may be slow for large datasets
	- need to store training data in order to make the prediction 
6. why we need to split the dataset into training set and test set
    - Learn decision tree using training set and evaluate performance on the test set. This gives unbiased evaluation.
7. appreciate the benefits and limitations of accuracy as a performance metric for classification 
    - suppose there are 2 classes 0 and 1, with 9990 and 10 instances each
    - can be misleading if all test cases are predicted as class 0
8. understand why it is necessary to avoid using the test data (directly or indirectly), when constructing a model such as decision tree (from workshop)
    - Look at test data in feature selection will provide information to the feature selection process that should not have been seen. Consequently the model that was trained using the results from the feature selection was developed on information that should not have been seen.  The reported accuracy will thus likely be over optimistic. 
    - Test data missing value: Could either 
    i) Impute the missing values and then use the decision tree (the merit of doing this will depend on the accuracy of imputation), or 
    ii) When at prediction time we encounter a node in the decision tree which tests a variable A, and for that variable we have in our instance a missing value than all the possibilities are explored. 
    - Thus, for each possible sub-node a prediction is made. We keep the distribution for each sub-node and we add them. Finally the class chosen for prediction is the class with the biggest density value. 



## LECTURE 16-18: DATA LINKAGE

1. Data linkage problem
    - combining related/equivalent records across data sources
2. Why matching a database against itself can be regarded as a data linkage task
    - business wishes to carry out an advertising campaign
    - the customer database changes over time, people move address, change their names.
    - duplicate records about individuals - business wishes to know if the same person appears more than once.
3. Why record linkage is applied
    - For businesses purpose, need to identify if two or more records fefer to the same individual.
    - build connection between the similar record in separate table.
4. Blocking
    - process
        - preprocessing
            - clean the data
        - Blocking
            - represent complex records as simple values(blocks). Only score records with simple value in common.
        - Scoring
            - comparing two records and asses their similarity
            - can use Jaccard similarity or edit distance here.
        - Matching
            - match sufficiently similar records
        - Merging
            - merge two groups, resolve conflicting attributes
    - Why?
        - since blocking is much faster than linear scan and compare (n*m), but blocking only takes (m/b\*n/b\*b = m\*n/b)
    - challenges
        - to determine the size of b
            - when b is too small the speed is not significantly improved
            - when b is too large the accuracy will drop dramatically
            - for a good blocking strategy(uniform spread across blocks), then accuracy may be almost as good as strategy without blocking, but much much faster.
5. Privacy
    - When important?
        - Matched data is being passed to another organisation or being made public
        - Data matching is being conducted across databases from different organisation.
    - the objective of privacy preserving
        - without revealing any information about individuals who do not get linked across the databases
6. One way hashing
    - also means non invertible hash function
    - for each organisation, applies a one way hash function to the attribute used to join the databases and shares its hashed values with other organisation. Each checks which ones match. These are linked records.
    - Disadvantages
        - little big difference results in a completely different output
        - Dictionary attack: an organisation could mount a dictionary attack to "invert" the hash function. for example, organisation A scans the hashed values received from Organisation B. Checks if any match its hash dictionary. If yes, privacy is lost for those items.
7. Third party protocol
    - using salt
        - organisation A and B concatenate a secret word to every name field in their data before hashing(known as salt). Organisation C does not know what this word is and thus can't perform a dictionary attack to "reverse" the hashed values it received. When we send
        - disadvantages
            - may not robust to frequent attck,that is, 3rd party compares the distribution of hashed values to some known distribution. E.g. distribution of surename frequencies in a public database versus distribution of hash value. ***To prevent this, we also need to add some random record.***
            - adding salt does not help two parties protocol
            - doesnt help approximate matching
8. Similar match
    - using 2-grams to calculate the approximate similarity
        - 2*(number of 2 common 2-grams)/ (total number of 2-grams in both string)
	- easy comparison and effective method
9. Bloom filter
    - how it works
        - A bloom filter is an array of n bits, with all bits initially set to zero. We may store strings in the bloom filter by using hash functions H1...Hk to turn on certain bit. If a bit was set to 1 before, no change is made.
        - similarity is (number of bits set to 1 in bot bloom filter) / (sum of 1 bitss in bot bloom filter)
        - need to set the thread for similar comparison.
    - how to protect string
        - Very hard for third party to guess the exact word by only using the bloom filter but still perform similar to exact string compare.
    - notice that chose a proper size of bloom filter and number of hash function is very important, when bloom filter is too small or use too many hash functions the comparison is useless since almost all string has full 1 bits in bloom filter.



## LECTURE 19-20 BLOCKCHAIN

1. why blockchain
    - remove the middle man, that is, no central, trusted point of control
    - less administration, less bureaucracy
    - less fees
    - faster transactions
    - more control over records handed to users
    - ability to be anonymous
    - users can verify data in the blockchain
    - more secure solution(maybe)
2. why secure
    - each computer hold a copy of the ledger, the public ledger is called the blockchain (a file)
    - file is a sequecen of blocks, each block contains a header and some data(list of transactions)
    - block ID equals to a hash of its header
    - each block contains the ID of its parent block
    - therefore, any change will results in different hash results, and all of it child will change relatively
3. advantage
    - the advantage of this property is that the content is very hard to modify once it been created
    - no central authority
4. disadvantages
    - after it created, if there is a mistake, it is very hard for us to correct.
    - sometimes advatages can becomes disadvantages.
5. understand how digital signatures be used to verify data on the blockchain
    - using private key and public key, A place a digital signiture on a block, B can use public key to verfy if it is ture.
6. how hashing can be used to make information on the blockchain private
    - applies a hash to the fact then adds this hash output to the blockchain along with a digital signiture. No one can reverse the hash function to uncover the fact, and it store on the blockchain but privacy is preserved. Alternatively could encrypt the fact using Alice's public key.



## LECTURE 21-22 PRIVACY

1. Individual's privacy may be uncovered by linking to an external dataset or by use of background or external knowledge
2. Terms understandind
    - sensitive attributes
        - information that people don't wish to reveal (e.g. medical condition)
    - non-sensitive attributes
        - information that people don't care reveal or not.
    - quasi identifier
        - a combination of non sensitive attributes that can be linked with external data to identify an individual (e.g. gender, age, zip code)
    - Explicit identifier
        - Unique for an individual (e.g. passport number)
3. K-anonymity
    - A record satisfies k-anonymity if every record in the table is indistinguishable from at least k-1 other records with respect to every set of quasi-identifier attributes. Such a table is called a k-anonymous table.
    - k-anonymity is susceptible to two tyoes of privacy attacks
        - homogeneity attack
            - k-anonymity can create groups that leak information due to leak of diversity in the sensitie attributes, which is caused by the sensitive information lack diversity when the attacker has some information about the person.
        - background attack
            - k-anonymity does not protect against attacks based on background knowledge. (e.g. Japanese have very low incidence of heart disease)
4. I-diversity
    - its a figure to indicate how sensitive attributes diverse within each group
5. How does K-anoymity and I-diversity protect privacy
    - with higher k and i, it makes the attacker much harder to find the sensitive information of individuals.
6. Benefits of using and sharing people’s location data
    - post on facebook or something like that
    - use GPS
    - use google map to find the nearest restaurant.
7. Possible privacy concerns of people’s location data being shared
    - under the potential of suffer inference attacks
        - Home/work location pairs may lead to a small set of potential individuals
        - regular visit place. (e.g Alice is Japanese, and regular visit heart hospital, so the user can be guessed.)
        - learn about indivuals travlling habits.
8. tradeoff to protect privacy (This part not examinable)
    - anonymity: clocking
        - K-anonymity
            - individuals are k-anonymous if their location information cannot be distinguish from k-1 other indivuals
        - Spatial cloaking
            - Gruteser & Grunwald use quadtrees
            - adapt the spatial precision of location information about a person according to the number of other people in the same quadrant
        - Temporal cloaking
            - Reduce the frequency of temporal information
    - Obfuscation
        - Idea
            - Mask an individual's precise location
            - Delibeately degrade the quality of information about an individual's location(imperfect information)
            - identity can be revealed
        - Assumption
            - Spatial imperfection almost means privacy
            - the greater the imperfect knowledge about a user's location, the greater the user's privacy
9. Differential privacy
    - What information is being protected
        - feels safe their are not much difference whether or not I take part in the survey
10. How much noise should be added?
    - Privacy budget (K)
        - how private we want the result to be (how hard for the attacker to guess the true result)
        - A is the probability that result is R with me, B is the probability that results R without me. Choses k to gearantee that A <= 2^k * B
            - k=0 No privacy loss, low utility
            - k=hgih: larger privacy loss, high utility
            - k=low: low privacy loss, lower utility
    - Global sensitivity (G)
        - How much difference the presence or absence of an indivual could make to the result
        - can be calculated by look at the datasets
    - how much to add
        - depending on G/k, that is, large G and small k allows more noise to be added.
        - but the average value of the noise is 0



## LECTURE 23 ETHICAL

1. Stakeholder
    - who
        - indivual
            - create big data
        - organization
            - own and benefit from data
        - society
            - guide and regular
2. appreciate the difference between the following two perspectives on the definition of (big) data analytics
    - Perspective 1: The ability to collect, store, and process increasingly large and complex data sets from a variety of sources, into competitive advantage. (more technology)
    - Perspective 2: Data is contributed, collected, extracted, exchanged, sold, shared, and processed for the purpose of predicting and modifying human behaviour in the production of economic or social value. (more social)
    - p1 is a organization perspective, p2 is a social perspective
3. summary of the 10 rules
    - rule 1
        - acknowledge that data are people and can do harm
        - all data are direct or indirect to people (e.g. social media)
    - rule 2
        - recognize that privacy is more than binary value
    - rule 3
        - guard against the reidentification of your data
    - rule 4
        - practie ethical data sharing
            - seeking consent from participants to share data
    - rule 5
        - consider the strengths and limitations of your data, big does not automatically mean better (Do not overstate clarity)
    - rule 6
        - debate the tough, ethical choices
            - importance of debating the issues within groups of peers
    - rule 7
        - develop a code of conduct for your organization, research community or industry (e.g. terms of service)
    - rule 8
        - desing your data and systems for auditability
            - plan for and welcome audits of your big data practices
	    - clarify how different datasets differ from each other
    - rule 9
        - engage with the broader consequences of data and analysis practices
        - that is, concern more about the society
    - rule 10
        - know when to break these rule
        - that is, know when to ignore these rules (e.g. natural disaster)
