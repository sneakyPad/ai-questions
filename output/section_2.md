<h1>3 EN: Data Science</h1>
<h2>Basics</h2>
<ol start=42>
<li>What are the two most common stochastic modelling approaches and in which areas (unsupervised/supervised) are they applied?<details><summary><b>Answer</b></summary><ul>
<li>Joint probability function (Unsupervised Learning)</li>
<li>conditional probability function (Supervised)</li>
</ul></details>
</li>
<li>What are the reasons for prediction/forecast errors?<details><summary><b>Answer</b></summary><ul>
<li>Used model cannot depict real situation</li>
<li>Randomness at generating the dataset from the real model (if dataset is small)</li>
<li>Randomness at learning (e.g. stochastic gradient descent, simulated annealing)</li>
</ul></details>
</li>
<li>What is the concept of I.I.D ?<details><summary><b>Answer</b></summary><ul>
<li>Independent Identically Distributed. Each of the n feature vectors is independent from the others and all have their origin in the same probability distribution.</li>
</ul></details>
</li>
<li>What is the definition of the Likelihood L(𝜗 | G)?<details><summary><b>Answer</b></summary><ul>
<li>For the likelihood L we usually take data G as given and evaluates the likelihood as function of 𝜗</li>
</ul></details>
</li>
<li>
<p>What is the definition of P(G | 𝜗)?</p><details><summary><b>Answer</b></summary><p>
<p>For a given 𝜗 we evaluate the probability of different results G of the data generation.</p>
<p><img alt="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled.png" height="50%" src="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled.png" width="50%"/></p>
<p>probability is the quantity most people are familiar with which deals with predicting new data given a known model ("what is the probability of getting heads six times in a row flipping this 50:50 coin?") while likelihood deals with fitting models given some known data ("what is the likelihood that this coin is/isn't rigged given that I just flipped heads six times in a row?"). I wanted to add this perspective because using the example in this clip, a likelihood quantity such as 0.12 is not meaningful to the layman unless it is explained exactly what 0.12 means: a measure of the sample's support for the assumed model i.e. low values either mean rare data or incorrect model!</p>
<p>Source: <a href="https://www.youtube.com/watch?v=pYxNSUDSFH4">https://www.youtube.com/watch?v=pYxNSUDSFH4</a></p>
</p></details></li>
<li>
<p>What is the Maximum-Likelihood-Prinicipal?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>
<p>We determine parameter 𝜗 that results in the max Likelihood for given data G</p>
<p>𝜗_hat = argmax 𝐿 ( 𝜗 | 𝐺 )</p>
</li>
</ul>
</p></details></li>
<li>
<p>What is the definition of a generative stochastical model?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>We talk about a a generative stochastical model for a data-mining challenge, on the assumption, that the data was generated by a stochastically process with a known structure (which most has unknown parameters)</li>
</ul>
</p></details></li>
<li>What is the difference between the Naive Bayes Classifier and the Bayes classifier?<details><summary><b>Answer</b></summary><ul>
<li>TL; DR: The naive Bayes classifier is an approximation to the Bayes classifier, in which we assume that the features are conditionally independent given the class instead of modeling their full conditional distribution given the class.</li>
<li>Taken from:<a href="https://www.quora.com/What-is-the-difference-between-the-Naive-Bayes-Classifier-and-the-Bayes-classifier">https://www.quora.com/What-is-the-difference-between-the-Naive-Bayes-Classifier-and-the-Bayes-classifier</a></li>
</ul></details>
</li>
</ol start=42>
<h3>Bias-Variance Tradeoff &amp; Bayesian Statistic</h3>
<ol start=50>
<li>What is the definition of Bias?<details><summary><b>Answer</b></summary><ul>
<li>The bias of a learned model for a specifically predicted value f(x_0) is the deviation between the expected value E(f(x_0) and the predicted value f(x_0) of the true value. (Ergo the estimaton of the parameter is not unbiased)</li>
</ul></details>
</li>
<li>How is the Bias produced/generated?<details><summary><b>Answer</b></summary><ul>
<li>Often the consequence is that the function class used in learning is not powerful enough to model the true context, or is prevented by regularization or a prior from choosing the parameters appropriately.</li>
</ul></details>
</li>
<li>Definition Variance<details><summary><b>Answer</b></summary><ul>
<li>The variance of the learned model for a certain predicted value 𝑓(𝑥) is understood to be a random deviation from the predictable portion 𝑓(𝑥) of the true value.</li>
<li>Especially for models with (too) many degrees of freedom, the prognosis result will be strongly influenced by the coincidence of the perturbation 𝜖, because the model can and will then also model this random noise, which turn out differently with each repetition.</li>
</ul></details>
</li>
<li>What is the composition of the Mean Squared Error (MSE) ?<details><summary><b>Answer</b></summary><ul>
<li>MSE =  Variance + Bias (E(f(x) - f'(x))^2) + non predictable portion/noise (epsilon)</li>
</ul></details>
</li>
<li>Describe the Tradeoff between Bias and Variance<details><summary><b>Answer</b></summary><ul>
<li>Suppose I took different degrees of freedom. Then my model will have a higher bias with fewer degrees of freedom, but a lower variance</li>
<li>The optimal total error is usually achieved somewhere in the middle of the model complexity, i.e. neither too much bias nor too much variance is desired.</li>
<li>However, if I know that a parameter is in fact independent of others, then the model would be limited if I did not treat it as such. In this case, after remodelling, I reduce the variance without increasing the bias.</li>
<li>→ Goal: Find independent Variables</li>
</ul></details>
</li>
</ol start=50>
<h3>Bayes</h3>
<ol start=55>
<li>What is the difference between the Bayesian learning approach and the classical one?<details><summary><b>Answer</b></summary><ul>
<li>The a-priori probability distribution is given and we generate a parameter vector THETA based on it. (One-time execution). This is used to generate the data using random experiments.</li>
<li>Based on the random sample, bayes is applied and the a-posteriori probability distribution is calculated (without bayes you would have a histogram here, which would basically be the Prior?)</li>
<li>A-posteriori is used for Inferenc/Recall</li>
</ul></details>
</li>
<li>What are the advantages of the Bayesian learning approach?<details><summary><b>Answer</b></summary><ul>
<li>The uncertainty of the estimates is taken into account in a consistent manner</li>
<li>Therefore less tendency to overfitting</li>
<li>The assumptions become explicitly visible in the form of the prior</li>
</ul></details>
</li>
<li>What are the disadvantages of Bayesian learning?<details><summary><b>Answer</b></summary><ul>
<li>The Prior must be mostly subjectively guessed.</li>
<li>The recall/inference is usually too complex for exact calculation and must be approximated numerically. (With all imaginable parameter values must be predicted, followed by weighted averaging).</li>
</ul></details>
</li>
<li>Definition Prior<details><summary><b>Answer</b></summary><ul>
<li>A-priori (i.e. prior knowledge of the data assumed on the basis of prior knowledge) probability distribution of the unknown parameters</li>
</ul></details>
</li>
<li>Definition Posterior<details><summary><b>Answer</b></summary><ul>
<li>A-posteriori (i.e. determined in consideration of data and prior knowledge) probability distribution of unknown parameters</li>
</ul></details>
</li>
<li>Is Bayes suitable for the practice?<details><summary><b>Answer</b></summary><ul>
<li>No, because calculating the integral over all possible parameters analytically is too costly</li>
</ul></details>
</li>
<li>Why do people still like to use Bayes?<details><summary><b>Answer</b></summary><ul>
<li>Serves as a source of intuition as to what one should expect for a good prognosis</li>
<li>Approaches of Model Averaging can be considered as approximations of Bayesian learning</li>
</ul></details>
</li>
<li>Give an example approach for the approximation of Bayes<details><summary><b>Answer</b></summary><ul>
<li>Bagging: Different sampling (random) and training of separate models. Inference averages the predictions of all models. Predictions turn out differently because of different samples.</li>
</ul></details>
</li>
</ol start=55>
<h2>Dimensionality reduction</h2>
<ol start=63>
<li>Why should dimensions be reduced?<details><summary><b>Answer</b></summary><ul>
<li>Too high dimensions lead either to computational problems or worsen performance due to irrelevant input. (Curse of Dimensionality)</li>
</ul></details>
</li>
<li>Which modeling assumptions are made to solve the problem?<details><summary><b>Answer</b></summary><ul>
<li>Assumption of a linear relationship (correlation of two features)</li>
<li>Assumption of irrelevant features (input pruning)</li>
<li>Assumption that the problem can be solved by a linear projection of the input space (PCA)</li>
</ul></details>
</li>
<li>Name concrete approaches for the reduction of dimensions<details><summary><b>Answer</b></summary><ul>
<li>Omit unimportant inputs (Input Pruning, Feature Selection), e.g. by<ol>
<li>Greedy Algorithm: remove the (apparently) least important one several times in succession</li>
<li>Ideal selection: Train a model with each subset of inputs and take the best one.</li>
</ol>
</li>
<li>Summarize inputs. (e.g. through aggregation or more complex transformations such as PCA (Principal Component Analysis))</li>
</ul></details>
</li>
<li>What are the critical points of  a) Greedy, b) Ideale Selection and c) PCA?<details><summary><b>Answer</b></summary><ul>
<li>a) Greedy selection can lead to suboptimal decisions</li>
<li>b) Impracticable, as it is too costly. Overtraining in input selection possible.</li>
<li>c) <strong>PCA</strong> considers only the statistical distribution of input values, without considering the relevance for the output.</li>
</ul></details>
</li>
<li>
<p>Explain the idea of PCA (Principal Component Analysis)?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>The idea is to eliminate axes representing variables by appropriate rotation (columns of the rotation matrix are orthogonal). One wants to omit the axes that express little variance of the data, which is caused, for example, by the correlation of two variables. This results in two goals:<ul>
<li>the <strong>resulting variables are linearly independent</strong> of each other.</li>
<li>the transformed dimensions have <strong>as much variance</strong> as possible and are sorted by the decreasing variance of the data</li>
</ul>
</li>
<li>Intuition:<ul>
<li>Preserve the information available in n variables as good as possible in m variables, where m&lt;n.</li>
</ul>
</li>
</ul>
<p>However: Result depends on the scaling of the inputs.</p>
</p></details></li>
<li>
<p>Name the steps of the PCA</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>Step 1: Make the variables as independent as possible by rotation</li>
<li>Step 2: Omit the variables with the lowest variance, for example the second main component</li>
</ul>
</p></details></li>
</ol start=63>
<h2>Sampling</h2>
<ol start=69>
<li>What is sampling and when should sampling be applied?<details><summary><b>Answer</b></summary><ul>
<li>If the data set is too large, the approaches are first tested on small excerpts. If the results are good, the large data set can be used.</li>
</ul></details>
</li>
<li>What are the possibilities for downsizing?<details><summary><b>Answer</b></summary><ul>
<li>Reduce number of tables or columns</li>
<li>Reduce number of rows</li>
</ul></details>
</li>
<li>What options are there for reducing the number of columns?<details><summary><b>Answer</b></summary><ul>
<li>Omitting tables or columns (only the important columns are kept)</li>
<li>Column aggregation (averaging of columns, e.g. pixels of images) E.g. replace measured values from different sensors by their average value</li>
<li>Dimension reduction, e.g. with PCA</li>
</ul></details>
</li>
<li>
<p>What options are there for reducing the number of rows?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>
<p>Aggregation of several rows</p>
<p>E.g. measured values that were recorded at millisecond intervals can be made larger by averaging them at one-second intervals</p>
</li>
<li>
<p>Simple Random Sampling</p>
<ul>
<li>Without putting it back: default case</li>
<li>With putting back: Loses more information, desired if stronger randomness is required</li>
</ul>
</li>
<li>Stratified Sampling<ul>
<li>Amount of data is divided into groups/categories and simple random sampling is performed on these groups. This ensures that the same amount of data is sampled from both groups. (Important if you want to keep the original distribution, e.g. elections)</li>
</ul>
</li>
<li>Systematic selection (by hand, manual)</li>
<li>What is the advantage of random sampling?</li>
<li>Both are robust, in case that the data set is arranged according to some systematic.</li>
<li>What is the difference between the variant "without replacement" and the variant "with replacement"?</li>
<li>Variant without replacement is the standard procedure and produces less variance than "with”</li>
<li>"With" is used if more variance is desired (e.g.: bagging)</li>
<li>What is a Bias?</li>
<li>Systematic estimation error</li>
<li>Which value increases the standard deviation for pure random sampling?</li>
<li>With the reciprocal of the root of the sampling rate</li>
<li>When is bias generated during sampling?</li>
<li>If the sampling selects data objects based on different probabilities</li>
<li>How can the generated bias be compensated?</li>
<li>if the data sets in the sample are assigned weighting factors that are inversely proportional to the probability of their being selected into the sample. → reciprocal value<ul>
<li>Example: Fraud cases with 100%, not fraud cases with 0.1% in the sample. Compensate by weighting data sets in the sample with the reciprocal of their sample probability. =&gt; not fraud * 1000</li>
</ul>
</li>
<li>Give two examples of criteria for systematic selection</li>
<li>Deterministic selection criterion with link to the data contents. Extreme form of stratified sampling in which nothing is left to random chance.</li>
<li>Example: A department store with an inventory of 100,000 products and 100 branches creates a data record of 10 million purchase transactions - for each product one transaction from each branch.</li>
<li>Deterministic selection criterion without relevance to the data contents:</li>
</ul>
<p>Example: Every 10th row of the data set (corresponds to random sampling for randomly sorted data)
- What does the abbreviation IID stand for and what does it mean?
- Independent and identically distributed random variables
    - Rows are independent of each other and are all subject to the same distribution
- What problems can occur when sampling relational data (across multiple tables)?
- Integrity violations during subsequent joins (e.g. purchase order item with order_id for which there is no master data)
- Cross-record key figures can be falsified. (e.g. number of articles per shopping cart, average time interval between orders from a customer)
- Integritätsverletzungen bei späteren joins (z.B. Bestellposition mit order_id, zu der es keine Stammdaten gibt)</p>
<p>Falsifications can be corrected, but are very costly and depend on the type of key figure calculation. In addition, the corrected values tend to have a very high variance.</p>
</p></details></li>
<li>
<p>What would be the best solution for relational sampling?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>Look at the data and best is to sample the data on the top level and then join it (e.g. UserId is top level, join from order_ids)</li>
</ul>
</p></details></li>
<li>What are the disadvantages of relational sampling?<details><summary><b>Answer</b></summary><ul>
<li>If more than one table is processed, it may not be feasible</li>
<li>Sampling depends on the model approach and features used. 
(e.g. if we at Instacart want to have a variable for every order that tells us how shortly before the last order was received by Instacart - no matter which user)</li>
</ul></details>
</li>
</ol start=69>
<h2>Metrics</h2>
<ol start=75>
<li>
<p>What is the ROC curve? (Also called Precision Recall Curve)</p><details><summary><b>Answer</b></summary><p>
<p><a href="https://www.youtube.com/watch?v=4jRBRDbJemM">ROC and AUC, Clearly Explained!</a></p>
<ul>
<li>ROC is used if you want to compare different values for a threshold.</li>
<li>
<p>Comparison of True Positive Rate (Sensitivity) and False Positive Rate (1- Specifity)</p>
<p><img alt="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%201.png" height="50%" src="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%201.png" width="50%"/></p>
</li>
<li>
<p>For each new threshold the values are recalculated and plotted again. Here you can see that there are two points that would be best. The left point would have no false positives at all. Depending on the use case, a decision must be made here. The points can still be connected to a line.</p>
<p><img alt="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%202.png" height="50%" src="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%202.png" width="50%"/></p>
</li>
</ul>
</p></details></li>
<li>
<p>What is AUC?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>
<p>Area under the Curve. Describes the area below the curve and is very useful for comparing different approaches</p>
<p><img alt="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%203.png" height="50%" src="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%203.png" width="50%"/></p>
</li>
</ul>
</p></details></li>
<li>
<p>What is the disadvantage of AUC?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>Compared to Precision, an imbalance of the data (e.g. the true negative) can have an effect on the result.</li>
</ul>
</p></details></li>
<li>Provide metrics for regression models<details><summary><b>Answer</b></summary><ul>
<li>Mean squared error</li>
<li>Root mean squared error</li>
<li>Mean absolute error</li>
<li>Median absolute error</li>
</ul></details>
</li>
<li>What is the advantage of Root Mean Squared Error?<details><summary><b>Answer</b></summary><ul>
<li>Makes the mean squared error more interpretable</li>
</ul></details>
</li>
<li>What is the advantage of Mean Absolute Error?<details><summary><b>Answer</b></summary><ul>
<li>Not so sensitive to outliers (more robust)</li>
</ul></details>
</li>
<li>What is the advantage of Median Absolute Error?<details><summary><b>Answer</b></summary><ul>
<li>Even more robust against outliers</li>
</ul></details>
</li>
<li>When should Precision be used?<details><summary><b>Answer</b></summary><ul>
<li>Suitable for highly unbalanced problems</li>
</ul></details>
</li>
<li>
<p>What are the two approaches to multiclass classification?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>
<p>Look at the binary classification for each class. "belongs" or not. Average values over classes.</p>
<p>a) Arithmetic mean "macro averaging" → Not well-founded, rather poor</p>
<p>b) Weighted by class frequency "Weighted Averaging" → Better</p>
</li>
<li>
<p>Multiclass Confusion Matrix → "Micro Averaging" → Best option: No metrics are created for multiple classes</p>
<p><img alt="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%204.png" height="50%" src="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%204.png" width="50%"/></p>
</li>
<li>
<p>Taken from: <a href="https://towardsdatascience.com/multi-class-metrics-made-simple-part-ii-the-f1-score-ebe8b2c2ca1">https://towardsdatascience.com/multi-class-metrics-made-simple-part-ii-the-f1-score-ebe8b2c2ca1</a></p>
</li>
</ul>
</p></details></li>
</ol start=75>
<h2>Graphical Models</h2>
<ol start=84>
<li>What does a graphical model represent?<details><summary><b>Answer</b></summary><ul>
<li>The stochastic (in)dependence structures between random variables, that are modeled as nodes</li>
</ul></details>
</li>
<li>What types of networks are there?<details><summary><b>Answer</b></summary><ul>
<li>Causal networks (includes causal structure)</li>
<li>Bayesian networks (dependency structure like for causal networks, but without causal structure). Directed Graph</li>
<li>Markov networks (undirected graph)</li>
</ul></details>
</li>
<li>What is the difference between a causal network and a Bayesian network?<details><summary><b>Answer</b></summary><ul>
<li>By knowing the causality relationships it is possible to predict what happens when you change variables. With Bayes networks only a conclusion is made about what happens with what probability if you do not manipulate/intervene the system.</li>
</ul></details>
</li>
</ol start=84>
<h2>EM (Expectation-Maximization)-Algorithm</h2>
<ol start=87>
<li>What is the goal of the EM-Algos?<details><summary><b>Answer</b></summary><ul>
<li>Clustering of data points using the a-priori values variance and mean.</li>
</ul></details>
</li>
<li>
<p>Describe the process of the EM</p><details><summary><b>Answer</b></summary><p>
<p>Starting point: A cluster of data points without knowing by which probability function the values are created.</p>
<p><img alt="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%205.png" height="50%" src="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%205.png" width="50%"/></p>
<ol>
<li>Estimate the a-priori value for variance and mean value (start with two randomly placed Gaussians)</li>
<li>Estimate Step: Use Bayes Rule to estimate the probability of a point belonging to a certain distribution. Either blue or yellow, but no hard assignment, only the probability (between 0 and 1).</li>
<li>
<p>Maximize step: Update mu and variance based on the points that were assigned softly</p>
<p><img alt="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%206.png" height="50%" src="data/3%20EN%20Data%20Science%20fa58d61a8fcb4fe6ae468822baa9dde3/Untitled%206.png" width="50%"/></p>
</li>
<li>
<p>Source: <a href="https://www.youtube.com/watch?v=REypj2sy_5U&amp;list=PLBv09BD7ez_4e9LtmK626Evn1ion6ynrt&amp;ab_channel=VictorLavrenko">https://www.youtube.com/watch?v=REypj2sy_5U&amp;list=PLBv09BD7ez_4e9LtmK626Evn1ion6ynrt&amp;ab_channel=VictorLavrenko</a></p>
</li>
</ol>
</p></details></li>
<li>
<p>How does EM differ from K-Means?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>If you make a hard assignment in the E step (hard assignment to a cluster), that means each missing value is set to the most likely value, instead of continuing with the whole probability distribution, you get exactly the k-means algorithm.</li>
</ul>
</p></details></li>
</ol start=87>
<h2>Data Quality, Missing Values, and Outliers</h2>
<ol start=90>
<li>When do data flaws not bother you?<details><summary><b>Answer</b></summary><ul>
<li>If the frequency and type of flaws in the selected model type do not indicate a major change in the result. (e.g. single, minor measurement errors, rare outliers with an approach robust against outliers such as Median Absolute Error instead of Mean Squared Error)</li>
<li>If they can be considered as part of the learning problem</li>
</ul></details>
</li>
<li>When does it make sense to take data flaws into training?<details><summary><b>Answer</b></summary><ul>
<li>Training the model with it makes sense if the same deficiencies are also present as input when using the model. The advantage is that no effort is required for data cleansing and if the model can handle it, it is an optimal solution. The disadvantage is that a combination with expert knowledge or models from other sources is difficult. If necessary, rename the feature, for example Temperature → Temperature reported by sensor</li>
</ul></details>
</li>
<li>Specify causes for missing values<details><summary><b>Answer</b></summary><ul>
<li>Incomplete data collection (sensor failure, questionnaire incomplete)</li>
<li>Variable makes no sense (e.g. "time since last order" for first order)</li>
</ul></details>
</li>
<li>How can outliers be detected?<details><summary><b>Answer</b></summary><ul>
<li>Check the value range of the variables for plausibility, possibly look at the histogram.</li>
<li>Display joint distribution of pairs of variables, e.g. as a scatter diagram</li>
<li>Learn the probabilistic model of the common probability distribution of all variables (i.e. unsupervised). Data objects with the smallest probability are outlier candidates. (Or, for non-probabilistic clustering model: Objects with a large distance from their cluster center, as well as clusters with very few assigned points are candidates).</li>
</ul></details>
</li>
<li>How should outliers be dealt with?<details><summary><b>Answer</b></summary><ul>
<li>Leave it in (in any case at (3); also at (2), if the learning process can cope with it).</li>
<li>Possibly, use a robust model type (e.g. Median Absolute Error instead of Mean Squared Error)</li>
<li>Replace with replacement value or treat as missing.</li>
</ul></details>
</li>
<li>
<p>What types of missing values are there?</p><details><summary><b>Answer</b></summary><p>
<ol>
<li>
<p><strong>MCAR: Missing Completely at Random</strong>: </p>
<p>Whether a value is missing or not is stochastically independent of all input and output variables.
Example: Transmission error due to radio interference when reading out a radio temperature sensor.</p>
</li>
<li>
<p><strong>MAR: Missing at Random</strong>: </p>
<p>Whether a value is missing or not is stochastically independent of the missing value.
Example: Women are less willing to give their age in a survey than men. Here: stochastic dependence on gender, but not on age itself.</p>
</li>
<li>
<p><strong>NMR: Not Missing at Random: Whether a value is missing or not depends on the missing value.</strong>
Example: Older women are less willing to reveal their age than younger ones.</p>
</li>
<li>Which of the three types does not lead to a bias?</li>
<li>MCAR</li>
<li>Mention points for dealing with missing values</li>
<li>Use approaches that can handle missing values (for example, Naive Bayes classifier, certain decision tree variants)</li>
<li>Ignore affected data objects completely</li>
<li>Use affected data objects only partially</li>
<li>Insert a substitute value (imputation)</li>
<li>Use probability distribution of the missing value as a substitute. (EM algorithm)</li>
<li>Code 'value missing' as a special value of the variable. Thus, a model (or, in the case of manual analysis, a human) with approaches that require complete data can be applied to incomplete data.</li>
</ol>
<p>All these procedures only work under certain conditions. There is no way around finding out (or making assumptions) why the values are missing.</p>
</p></details></li>
<li>
<p>Handling missing values: Explain advantages/disadvantages of Naive Bayes classifier</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>Usually leads to bias, if not MCAR.</li>
<li>Advantage: Very simple, because you can simply omit one variable in the term.</li>
</ul>
</p></details></li>
<li>Handling missing values: Explain advantages/disadvantages when affected data objects are completely ignored<details><summary><b>Answer</b></summary><ul>
<li><strong>Advantage</strong>: Simplest approach.</li>
<li><strong>Disadvantage</strong>: Available data shrinks. Under certain circumstances this can happen very strongly.
Example: If there are 100 variables, and each individual value is missing with 2% probability (independent of the others), only 13% of the data objects are complete</li>
<li>May lead to bias if not MCAR and the output variable is stochastically dependent on the absence of the input variable (Supervised Learning), or if the absence of the input variable depends on the value of a variable whose probability distribution is to be modeled (Unsupervised Learning).</li>
<li><strong>Prerequisite</strong>: Only suitable when little is missing.</li>
</ul></details>
</li>
<li>
<p>Handling missing values: Explain advantages/disadvantages of affected data objects only partially used</p><details><summary><b>Answer</b></summary><p>
<ul>
<li><strong>Advantage</strong>: Data is optimally used</li>
<li>
<p><strong>Prerequisites</strong>/<strong>Disadvantage</strong>: May lead to bias if not <strong>MCAR</strong>, just like when affected data objects are completely ignored.</p>
<p>Example: In the scatterplot for the dimensions (X1, X2) omit the data objects where X1 or X2 are missing, in the scatterplot (X2, X3) omit those where X2 or X3 are missing.</p>
</li>
</ul>
</p></details></li>
<li>
<p>Handling missing values: Explain advantages/disadvantages of using substitute values (imputation)</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>(a) For quantitative feature, e.g. <strong>mean</strong> or <strong>median</strong></li>
<li>(b) For ordinal feature: <strong>median</strong></li>
<li>(c) For nominal feature: <strong>modal value</strong>; or</li>
<li>d) CPS hot deck (Current Population Survey): Use the value of the previous data object for this feature. (This means that a <strong>random value is taken from the distribution of this feature</strong>)</li>
<li>e) Or in general: <strong>Learn a predictive model</strong> for the missing feature and thus estimate the missing values. Common: <strong>k-nearest neigbor</strong></li>
</ul>
<p><strong>Advantage</strong> of a-d: Simple</p>
<p><strong>Downside</strong>:</p>
<ul>
<li>
<p>a - c falsifies the distribution of the missing attribute even with MCAR</p>
<p>→ possibly <strong>Bias</strong> in the results</p>
</li>
<li>
<p>(d) still generates <strong>some bias</strong> (because dependencies are not taken into account), but less than a-c, but additionally <strong>variance (model error/variance due to arrangement of objects)</strong></p>
</li>
<li>(e) produces no variance and even less bias than (d) (bias by using only the most likely value). Is <strong>more expensive</strong>. (Minimum bias is present because I take the best value)</li>
</ul>
</p></details></li>
<li>
<p>Handling missing values: Explain advantages/disadvantages of using probability distribution of missing value as a substitute. (EM algorithm)</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>Learn the prediction model for the probability distribution of the missing feature to estimate the missing feature from the other features (EM algorithm)</li>
<li>
<p>Create multiple data objects with the estimated probability values and weight the estimated value with the assigned probability.</p>
<p>A<strong>dvantage</strong>: <strong>Best practice from a statistical point of view</strong>, with MCAR there is no bias (or only to the extent that the model used has bias).</p>
<p>D<strong>isadvantage</strong>: <strong>High effort.</strong> Only worth it if many important values are missing.</p>
</li>
</ul>
</p></details></li>
<li>
<p>Handling missing values: Explain advantages/disadvantages of "value missing" encoding as a special value of the variable.</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>No problems with nominal variables</li>
<li>
<p>Not very nice with metric or ordinal variables (e.g. -99 = "missing").</p>
<p>Whether this is an issue depends on the model types used.</p>
<p>→ Solution:</p>
<ul>
<li>Perhaps assign <strong>additional binary variables (F1 ... Fn)</strong> to the variables (X1 ... Xn), which specify, which of the X-values are missing (nevertheless you need replacement values for the missing values in X).</li>
</ul>
<p><strong>Prerequisite</strong>: It makes sense to learn <strong>missing values as part of the problem definition</strong>.</p>
<p><strong>Advantage</strong>: <strong>Little effort</strong>. If the model can handle it, <strong>optimal solution</strong>.
<strong>Disadvantage</strong>: With ordinal or <strong>metric features</strong> the subject is <strong>difficult to model</strong> for many model types.</p>
</li>
</ul>
</p></details></li>
<li>
<p>How does the bias behave with MCAR and "omitting data objects", imputation and the EM algorithm?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>Generally unproblematic.</li>
<li>In this case, <strong>Omitting</strong> the relevant data objects results in <strong>no bias</strong>, but in an increase in the variance of the model because the amount of training data is reduced. A data scientist works on a random sample of the (unknown) complete data set.</li>
<li>If you let a model learn to estimate the probability distribution of the missing value depending on the other variables and thus generate replacement values, this also leads to <strong>no bias.</strong></li>
<li>However, using only the <strong>most probable replacement value</strong>, or the <strong>mean</strong> or <strong>median</strong>, generally results in a systematic deviation of the completed data set from the true values, and therefore in a <strong>bias</strong>.</li>
</ul>
</p></details></li>
<li>
<p>How does the <strong>bias</strong> behave with MAR and by using "omitting data objects", orr imputation and the EM algorithm?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li><em>Omitting</em> in MAR, if the value of the missing variable is to be estimated, leads to distorted estimates (<strong>bias</strong> increases)</li>
<li><em>Replacing by mean value</em> in MAR if the value of the missing variable is to be estimated, leads as well to distorted estimates (<strong>bias</strong> increases).</li>
</ul>
<p>Then the missing value is stochastically independent of the missing one under the condition that the other variables are known:</p>
<ol>
<li>If the variables on which the absence is stochastically dependent only serve as input variables, <strong>no bias</strong> occurs in the conditional probability distribution (or regression task) to be estimated, if one <strong>just leaves out</strong> the incomplete data sets.</li>
<li>If the absence also depends on output variables, or if a common probability distribution is to be estimated, omitting the data objects with missing values results in a <strong>bias</strong>. However, this <strong>bias</strong> can be <strong>compensated</strong> by creating an estimation model for the probability of the absence depending on the variable values, and then weighting the <strong>data records with the reciprocal of the probability of absence</strong>.</li>
</ol>
</p></details></li>
<li>
<p>How does the bias behave in NMR and by using "omitting data objects" or imputation and the EM algorithm?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>Omitting the incomplete data objects generally leads to a <strong>bias</strong>.</li>
<li>Problem: This can not be <strong>compensated</strong>, because the dependency of the missing
missing probability on the missing variable cannot be estimated. (No training data)</li>
<li>Also <strong>imputation procedures</strong> lead to a <strong>bias</strong> because there is no training data for data objects with missing values, but the value distribution for these data objects is different from that for those without missing values.</li>
</ul>
<p>If there is a risk that the missing values will have a significant influence on the results, the data must be collected again.</p>
</p></details></li>
<li>
<p>When is a clean approach to the problem critical?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>If a strong correlation between the missing and the target value of the modelling is to be feared</li>
</ul>
</p></details></li>
<li>What should be done first when it is noticed that features are incomplete?<details><summary><b>Answer</b></summary><ul>
<li>Make assumptions about the mechanism by which the missing values arise.</li>
</ul></details>
</li>
<li>When are the generated model errors probably not critical and a simpler procedure should be chosen?<details><summary><b>Answer</b></summary><ul>
<li>If only a few values are missing in a non-critical feature, or in general if values are missing in a non-essential feature.</li>
</ul></details>
</li>
<li>
<p>What should be done if data with the same systematics is expected to be missing when given as input to the inference?</p><details><summary><b>Answer</b></summary><p>
<p>→ Interpret missing data as part of the problem definition, give the model the information what is missing as input</p>
</p></details></li>
<li>
<p>Requirements for a bayes network?</p><details><summary><b>Answer</b></summary><p>
<ul>
<li>It is not allowed to be cyclical</li>
<li>Must have directional edges</li>
</ul>
</p></details></li>
</ol start=90>