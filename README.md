Download Link: https://assignmentchef.com/product/solved-csci567-homework-4-generative-models
<br>
<h1>Generative models</h1>

<strong>Q1.1 </strong>Let <em>X </em>∈ R be a random variable. We assume that it is uniformly-distributed on some unknown interval (0<em>,θ</em>], where <em>θ &gt; </em>0. In particular,

<sup>(<u>1</u><em>θ           </em></sup>, if <em>x </em>∈ (0<em>,θ</em>]<em>,                                                                 </em>(1)

<em>P</em>(<em>X </em>= <em>x</em>|<em>θ</em>) =

0     , otherwise,

<em>,                                                                        </em>(2)

where <strong>1 </strong>is an indicator function that outputs 1 when the condition is true, and 0 otherwise.

Suppose <em>x</em><sub>1</sub><em>,x</em><sub>2</sub><em>,…,x</em><sub>N </sub>are drawn i.i.d. from this distribution. Write down the likelihood of the observations <em>P</em>(<em>x</em><sub>1</sub><em>,…,x</em><sub>N</sub>). What is the maximum likelihood (ML) estimate of <em>θ</em>? Give a sentence or two explaining why your equation corresponds to the maximum likelihood estimate.

<em>What to submit: </em>The equation for the likelihood (at most two lines), the final equation of ML estimate for <em>θ </em>(one line), and fewer-than-two sentences of explanation.

<strong>Q1.2 </strong>Now suppose <em>X </em>is distributed according to a <strong>mixture </strong>of two uniform distributions: one on some unknown interval (0<em>,θ</em><sub>1</sub>] and the other on (0<em>,θ</em><sub>2</sub>], where 0 <em>&lt; θ</em><sub>1 </sub>≤ <em>θ</em><sub>2</sub>. In particular,

<em>P</em>(<em>X </em>= <em>x</em>) = <em>ω</em><sub>1</sub><em>U</em>(<em>X </em>= <em>x</em>|<em>θ</em><sub>1</sub>) + <em>ω</em><sub>2</sub><em>U</em>(<em>X </em>= <em>x</em>|<em>θ</em><sub>2</sub>)<em>,                                                        </em>(3)

where <em>U </em>is the uniform distribution defined as in Eq. (1) or Eq. (2), and <em>ω</em><sub>1</sub>, <em>ω</em><sub>2 </sub>are mixture weights such that

<em>ω</em><sub>1 </sub>≥ 0<em>,ω</em><sub>2 </sub>≥ 0, and <em>ω</em><sub>1 </sub>+ <em>ω</em><sub>2 </sub>= 1<em>.                                                                    </em>(4)

Suppose <em>x</em><sub>1</sub><em>,x</em><sub>2</sub><em>,…,x</em><sub>N </sub>are drawn i.i.d. from this mixture of uniform distributions. We will use an EM algorithm to derive the ML estimates of the parameters in this model. Answer the following three questions.

<ul>

 <li>First, what is the form of <em>P</em>(<em>k</em>|<em>x<sub>n</sub>,θ</em><sub>1</sub><em>,θ</em><sub>2</sub><em>,ω</em><sub>1</sub><em>,ω</em><sub>2</sub>), where <em>k </em>∈ {1<em>,</em>2} indicates the corresponding mixture component? You answer should be explicit. You may include the indicator function as in Eq. (2) and the <em>U </em>function as in Eq. (3).</li>

 <li>Second, what is the form of the expected complete-data log-likelihood of the observations {<em>x</em><sub>1</sub><em>,…,x</em><sub>N</sub>}, given that the parameters from the last EM iteration are</li>

</ul>

0<em>,ω</em><sub>2</sub><sup>OLD </sup><em>&gt; </em>0}, where? You answer should be explicit. You may include the indicator function as in Eq. (2) and the <em>U </em>function as in Eq. (3).

<em>Hint: Please refer to page 34/44 and other related pages of lecture 14.</em>

<ul>

 <li>Third, what are the forms of the M-step updates for <em>θ</em><sub>1 </sub>and <em>θ</em><sub>2</sub>? You may use <em>P</em><sub>OLD</sub>(<em>k</em>|<em>x<sub>n</sub></em>) =</li>

</ul>

), where <em>k </em>∈ {1<em>,</em>2}, to simplify your derivation/answer if

needed. You can view log0 = −and 0 × log0 = 0 in this question.

<em>What to submit: </em>The form of <em>P</em>(<em>k</em>|<em>x<sub>n</sub>,θ</em><sub>1</sub><em>,θ</em><sub>2</sub><em>,ω</em><sub>1</sub><em>,ω</em><sub>2</sub>) (at most two lines), the form of the expected complete-data log-likelihood (at most five lines), and the forms of the M-step update (at most ten lines).

<h1>2           Mixture density models</h1>

[Recommended maximum time spent: 1 hour]

Consider a density model given by a mixture distribution

<em>K</em>

<em>P</em>(<em>x</em>) = <sup>X</sup><em>π<sub>k</sub>P</em>(<em>x</em>|<em>k</em>)<em>,</em>

<em>k</em>=1

<em>K</em>

where <em>π<sub>k </sub></em>≥ 0 ∀<em>k </em>∈ [<em>K</em>] and <sup>X</sup><em>π<sub>k </sub></em>= 1<em>,</em>

<em>k</em>=1

and suppose that we partition the vector <em>x </em>into two parts so that <em>x</em>. Show that the

conditional density <em>P</em>(<em>x<sub>b</sub></em>|<em>x<sub>a</sub></em>) is itself a mixture distribution. That is,

<em>K</em>

<em>P</em>(<em>x<sub>b</sub></em>|<em>x<sub>a</sub></em>) = <sup>X</sup><em>λ<sub>k</sub>P</em>(<em>x<sub>b</sub></em>|<em>x<sub>a</sub>,k</em>)<em>,</em>

<em>k</em>=1

<em>K</em>

where <em>λ<sub>k </sub></em>≥ 0 ∀<em>k </em>∈ [<em>K</em>] and <sup>X</sup><em>λ<sub>k </sub></em>= 1<em>.</em>

<em>k</em>=1

<strong>Q2.1      </strong>Find an expression for the mixing coefficients <em>λ<sub>k </sub></em>of the component densities in terms of <em>π<sub>k </sub></em>and <em>P</em>(<em>x<sub>a</sub></em>|<em>k</em>). Do not forget to verify if your answer obeys the constraint on <em>λ<sub>k </sub></em>mentioned above.

<em>Hint: </em>a) <em>λ<sub>k </sub></em>is a function of <em>x<sub>a </sub></em>instead of a constant. b) You may consider Bayes rule for derivation.

<em>What to submit: </em>No more than ten lines of derivation that leads to an expression for the mixing coefficients <em>λ<sub>k</sub></em>.

<h1>3           The connection between GMM and K-means</h1>

[Recommended maximum time spent: 1 hour]

Consider a Gaussian mixture model (GMM) in which all components have (diagonal) covariance <strong>Σ </strong>= <em>σ</em><sup>2</sup><em>I </em>and the K-means algorithm introduced in lecture 14.

<strong>Q3.1 </strong>In the case where both the GMM and the K-means algorithm have <em>K </em>components and the parameters <em>π<sub>k </sub></em>are pre-defined to be nonzero ∀<em>k </em>∈ [<em>K</em>], show that in the limit <em>σ </em>→ 0, <strong>maximizing </strong>the following expected complete-data log likelihood w.r.t. for the GMM model

<em>N       K                     N                     K </em>XX       XX          |              2

<em>γ</em>(<em>z<sub>nk</sub></em>)log<em>p</em>(<em>x<sub>n</sub>,z<sub>n </sub></em>= <em>k</em>) =                            <em>γ</em>(<em>z<sub>nk</sub></em>)[log<em>π<sub>k </sub></em>+ logN(<em>x</em><em>n </em><em>µ</em><em>k,σ </em><em>I</em>)]<em>,</em>

<em>n         k                                                                                            n         k</em>

where

is equivalent (up to a scaling or constant factor) to <strong>minimizing </strong>the distortion measure <em>J </em>w.r.t.

for the K-means algorithm given by

<em>K         N</em>

<em>J </em>= XX<em>r</em><em>nk</em>||<em>x</em><em>n </em>− <em>µ</em><em>k</em>||22<em>,</em>

<em>k         n</em>

(

1<em>, </em>if <em>k </em>= argmin<em>,</em>

where      <em>r<sub>nk </sub></em>=

0<em>, </em>otherwise<em>.</em>

<em>Hint: </em>Start by showing that <em>γ</em>(<em>z<sub>nk</sub></em>) → <em>r<sub>nk </sub></em>as <em>σ </em>→ 0. Note that for this question the only set of parameters to learn for the GMM are . Any term independent of  can be treated as a constant.

<em>What to submit: </em>Derivation and reasoning with less than ten lines.

<h1>4           Naive Bayes</h1>

[Recommended maximum time spent: 1 hour]

Recall the naive Bayes model we have seen in class. Given a random variable <em>X </em>∈ R<sup>D </sup>and a dependent class variable <em>Y </em>∈ [C], the joint distribution of features <em>X </em>and class <em>Y </em>is defined as

<em>P</em>(<em>X </em>= <em>x,Y </em>= <em>c</em>) = <em>P</em>(<em>Y </em>= <em>c</em>)<em>P</em>(<em>X </em>= <em>x</em>|<em>Y </em>= <em>c</em>)                                                                  (5)

D

= <em>P</em>(<em>Y </em>= <em>c</em>) <sup>Y </sup><em>P</em>(<em>X<sub>d </sub></em>= <em>x<sub>d</sub></em>|<em>Y </em>= <em>c</em>)                                                    (6)

<em>d</em>=1

In this problem, we consider a naive Bayes model where each feature <em>x<sub>d </sub></em>of each class <em>c </em>is modeled as a (different) Gaussian. That is,

<em> ,                                       </em>(7)

where <em>µ<sub>cd </sub></em>and <em>σ<sub>cd </sub></em>are the mean and the standard deviation, respectively.

Moreover, we model <em>Y </em>as a multinomial distribution with parameter <em>π </em>(Note: this <em>π </em>is a parameter, whereas <em>π </em>in Eqn. (7) is a constant). That is,

C

<em>P</em>(<em>Y </em>= <em>c</em>;<em>π</em>) = <em>π<sub>c </sub></em>≥ 0 ∀<em>c </em>∈ [C], and <sup>X</sup><em>π<sub>c </sub></em>= 1<em>.                                                          </em>(8)

<em>c</em>

<strong>Q4.0         </strong>(Warm-up) What are the parameters to be learned in this model?

<em>What to submit: </em>Nothing.

<strong>Q4.1 </strong>Given the dataset {(<em>x<sub>n </sub></em>∈ R<sup>D</sup><em>,y<sub>n </sub></em>∈ [C])}<sup>N</sup><em><sub>n</sub></em><sub>=1</sub>, assumed to be drawn i.i.d. from this model, write down explicitly the expression for the joint log-likelihood.

<em>What to submit: </em>The expression for the joint log-likelihood (no more than ten lines). Parameters to be learned should all be in the expression.

<strong>Q4.2 </strong>Using the objective in <strong>Q4.1</strong>, derive the maximum likelihood (ML) estimates of the parameters. You should be able to compute these estimates from the training data {(<em>x<sub>n </sub></em><sup>∈ </sup>R<sup>D</sup><em>,y<sub>n </sub></em>∈

.

<em>What to submit: </em>The final equation of ML estimate as well as your short (no more than five lines) derivation for <em>each </em>parameter.

<strong>Programming component</strong>

<h1>5           High-level descriptions</h1>

<h2>5.1         Datasets</h2>

For Sect. 6 and 7, we will use 2-dimensional synthetic data hw4 circle.json and hw4 blob.json to perform clustering and density estimation. For Sect. 8, we will use the email dataset released during the 2001 Enron investigation for (binary) spam classification. See the text of the corresponding sections for more details.

<h2>5.2         Tasks</h2>

You will be asked to implement the K-means algorithm for clustering (Sect. 6), the Gaussian mixture model for density estimation (Sect. 7), and the naive Bayes model for binary classification (Sect. 8). Specifically, you will

<ul>

 <li>For Sect. 6: finish implementing the function kmeans clustering and related functions in py. Run the script kmeans.sh, which will output kmeans.json. Add, commit, and push kmeans.json and kmeans.py.</li>

 <li>For Sect. 7: finish implementing the function gmm clustering in py. Run the script gmm.sh, which will output gmm.json. Add, commit, and push gmm.json and gmm.py.</li>

 <li>For Sect. 8: finish implementing the following three functions—nb train, nb predict, and nb train smoothing—in nb spam.py. Run the scripts sh and nb2.sh, which will output nb1.json and nb2.json, respectively. Add, commit, and push nb spam.py, nb1.json, and nb2.json.</li>

</ul>

As in the previous homework, you are not responsible for loading/pre-processing data; we have done that for you. For specific instructions, please refer to text in Sect. 6, 7, 8, and the instructions in their corresponding scripts.

<h2>5.3         Cautions</h2>

Please do not import packages that are not listed in the provided code. Follow the instructions in each section strictly to code up your solutions. <strong>Do not change the output format</strong>. <strong>Do not modify the code unless we instruct you to do so</strong>. A homework solution that does not match the provided setup, such as format, name, initializations, etc., <strong>will not </strong>be graded. It is your responsibility to <strong>make sure that your code runs with the provided commands and scripts on the VM</strong>. Finally, make sure that you <strong>git add, commit, and push all the required files</strong>, including your code and generated output files.

<h1>6           K-means</h1>

As introduced in the class, the K-means algorithm tries to minimize the following distortion measure (or objective function):

<em>K        N</em>

<em>J </em>= XX<em>r</em><em>nk</em>||<em>x</em><em>n </em>− <em>µ</em><em>k</em>||22<em>,</em>

<em>k         n</em>

where <em>r<sub>nk </sub></em>is an indicator variable:

(

1<em>, </em>if <em>k </em>= argmin<em>,</em>

<em>r<sub>nk </sub></em>=

0<em>, </em>otherwise<em>.</em>

and {<em>µ</em><sub>1</sub><em>,…,</em><em>µ<sub>k</sub></em>} are the cluster centers, each with the same dimensionality of data points.

<strong>Q6.1              </strong>Implement K-means using random initialization for cluster centers. Run the algorithm on

2 two-dimensional synthetic datasets hw4 circle.json and hw4 blob.json (see Fig. 1 for illustration) with different values of <em>K </em>∈ {2<em>,</em>3<em>,</em>5}. The algorithm should run until none of the cluster assignments are changed.

<em>What to do and submit: </em>Finish the function kmeans clustering and related functions in kmeans.py. <em>Please do not change the random seeds set in our template code. </em>Detailed implementation instructions are provided in the python script. Then, run kmeans.sh, which will generate a kmeans.json file containing cluster center and the cluster assigned to each data point with all values of <em>K</em>. Add, commit, and push the modified kmeans.py and kmeans.json before the due date.

<strong>Q6.2 </strong>You are encouraged to plot the clustering assignments by different colors and markers. Does the algorithm work well in separating the two circles in the hw4 circle.json dataset and why?

<em>What to submit: </em>Nothing.

<h1>7           Gaussian Mixture Models</h1>

<strong>Q7.1 </strong>In this problem, you will implement an EM algorithm to fit a Gaussian mixture model on the hw4 blob.json dataset.

<em>What to do and submit: </em>Finish the implementation of the function gmm clustering in gmm.py. Detailed implementation instructions are provided in the python script. Then, run gmm.sh. It will run 5 rounds of your EM algorithm with the number of components <em>K </em>= 3 and generate a gmm.json file containing the mean and co-variance matrices of all the three Gaussian components. Add, commit, and push the modified gmm.py and gmm.json before the due date.

<strong>Q7.2 </strong>You are encouraged to plot the most likely clustering assignments by different colors and markers. Are the results from those 5 rounds the same? Why or why not?

<em>What to submit: </em>Nothing.

<h1>8           Naive Bayes</h1>

We will build a (binary) spam classifier using a naive Bayes model that classifies each document as “Spam” (1) or “Ham” (0).

<strong>Dataset       </strong>We will use the dataset drawn from emails released during the 2001 Enron investigation.

In what follows, we will describe this dataset in detail. <em>However, note that we have provided a python function that handles reading these files for you. </em>In the directory enron, you will find

<ul>

 <li>Word ID to word mapping in ind to vocab.txt. Specifically, each line consists of word ID and its corresponding actual word (space-separated). There are 158,963 words in the vocabulary.</li>

 <li>20,229 training emails in train txt and their labels in train labels.txt.</li>

 <li>6,743 validation emails in val features.txt and their labels in val labels.txt.</li>

</ul>

<table width="0">

 <tbody>

  <tr>

   <td width="400">0 word_id_0,1 frequency_word_id_0,1 word_id_0,2 frequency_word_id_0,2 . . word_id_0,D0 frequency_word_id_0,D0# 1 word_id_1,1 frequency_word_id_1,1 word_id_1,2 frequency_word_id_1,2 . . word_id_1,D2 frequency_word_id_1,D1# ...# N word_id_N,1 frequency_word_id_N,1 word_id_N,2 frequency_word_id_N,2 . . word_id_N,DN frequency_word_id_N,DN#</td>

  </tr>

 </tbody>

</table>

Figure 2: Format of * features.txt

<ul>

 <li>6,744 sampled test emails in sampled test features.txt and their labels in sampled test labels.txt.</li>

</ul>

The input format of * features.txt is shown in Fig. 2. Each of these features files consists of multiple documents separated by #. Each document starts with its ID n followed by Dn lines, where each line consists of word id and its frequency (space-separated). For example, the word word id 3,5 appears in document 3 for frequency word id 3,5 times. The labels of these documents are in * labels.txt, in which each line consists of document ID and its label (0 or 1).

<strong>Q8.1 Understand Data Format </strong>In nb spam.py, we have provided the function load docs which reads documents (words and their corresponding frequencies) for you. This function takes in two file names (features and labels), and outputs two lists. The first list contains documents, each of which is a list of tuples of word and its frequency in the document. The second contains labels of those documents. Your task is to read this function to understand the format of the data you will be working with.

<em>What to do and submit: </em>Nothing.

<strong>Q8.2 Train and Predict </strong>Please finish the implementation of the functions—nb train and nb predict—in nb spam.py:

<ul>

 <li>nb train estimates the parameters of the naive Bayes model, including the probability distribution of class being Ham or Spam <em>a priori </em>as well as the class-specific word probability distributions.</li>

 <li>nb predict uses the estimates from nb train to predict which class each new document belongs to.</li>

</ul>

Please follow the following implementation details. First, use the log-likelihood instead of the likelihood to avoid any numerical underflow issues. Moreover, if your model decides that a document has an equal chance of being Ham (0) or Spam (1), it should predict a Spam (1).

Finally, we will have to take care of unseen words. <em>Unseen words </em>are defined as words that do not appear in the <strong>training </strong>documents. In this question, we will ignore all unseen words during prediction. In addition, if you encounter computing log of a zero, replace the output with -1e50. This scenario could happen when a word appears in the training documents that belong to one class but it does not appear in those that belong to the other class.

<em>What to do and submit: </em>Finish the implementation of the functions nb train and nb predict in nb spam.py. Then, run script nb1.sh, which will generate a nb1.json file containing training, validation, and test accuracies. You should see that all accuracies are above 97%. Add, commit, and push the modified nb spam.py and nb1.json before the due date.

<strong>Q8.3 Train with smoothing </strong>We now take another approach to dealing with unseen words: a smoothing technique. Let <em>α &gt; </em>0 be a continuous-valued smoothing parameter. For each word in the vocabulary in each class, you will assume that you have seen it <em>α </em>times before even seeing any training data. That is, you should add <em>α </em>to its <em>count </em>before you train your model. This assumption will affect class-specific word distribution estimates. (<em>Hint</em>: you should see that <em>α </em>(and adjusted counts) affects both the numerator and the denominator in the formula of your parameter estimates).

Please finish the implementation of the function nb train smoothing in nb spam.py with the assumption described above. nb train smoothing estimates the parameters of the naive Bayes model, similar to nb train. Implementation details in the previous question apply to this question. Try <em>α </em>∈ {1e-8, 1e-7, 1e-6, 1e-5, 1e-4}.

<em>What to do and submit: </em>Finish the implementation of the function nb train smoothing in nb spam.py. Then, run script nb2.sh, which will generate a nb2.json file containing training, validation, and test accuracies for all values of <em>α</em>. You should see that, for the best <em>α</em>, all accuracies are above 98%. Add, commit, and push the modified nb spam.py and nb2.json before the due date.