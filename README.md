Download Link: https://assignmentchef.com/product/solved-natcomp-assignment-5-ensemble-learning
<br>



Please upload the assignment in the form of a neatly formatted PDF file containing the names and student ids of the group members and your group’s

answers. The grade for this assignment will be <u><sup>score</sup></u><sub>10</sub><u><sup>+5</sup></u>.

<h1>Learning Objectives</h1>

After this week’s lecture, reading and exercises, you will be able to

<ul>

 <li>explain Condorcet’s jury theorem</li>

 <li>explain the different between trained and untrained combiners</li>

 <li>list several ways to combine the results of models and apply them.</li>

 <li>explain the difference between bootstrapping and random subspaces</li>

 <li>implement a random forest classifier when given a decision tree implementation</li>

 <li>effectively apply a random forest classifier to a dataset and interpret its parameters and results</li>

 <li>give an explanation why a random forest might perform better than a single decision tree</li>

 <li>give an informal definition of a weak learner</li>

 <li>list and explain the steps in the AdaBoost algorithm</li>

 <li>describe the difference between bagging and boosting</li>

</ul>

<h1>Relevant Literature</h1>

<ul>

 <li>Hastie, T., Tibshirani, R., &amp; Friedman, J. H. (2009). The Elements of Statistical Learning (2nd ed.). Springer. Chapter 10 &amp; 15</li>

 <li>Kuncheva, L. I. (2004). Combining Pattern Classifers. Methods and Algorithms. Wiley, Chichester. Chapter 4 &amp; 5.</li>

 <li>Mohri, M., Rostamizadeh, A., &amp; Talwalkar, A. (2012). Foundations of Machine Learning. The MIT Press. Chapter 6</li>

 <li>(Optional) Ho, T. K. (1998). The random subspace method for constructing decision forests. IEEE Transactions on Pattern Analysis and Machine Intelligence, 20(8), 832-844.</li>

 <li>(Optional) Breiman, L. (2001). Random forests. Machine Learning, 45(1), 5-32.</li>

</ul>

<h1>Exercises</h1>

<ol>

 <li> Table 1 shows the posterior probability estimates, <em>p<sub>c</sub></em>(<em>ω</em>|<em>x</em>), of three different classifiers, for two different classes <em>ω </em>∈ {A<em>,</em>B}. Complete the table by filling in the values produced by the different combiners and indicate which decision each combiner would make based on these values.</li>

</ol>

<table width="402">

 <tbody>

  <tr>

   <td colspan="2" width="66"><em>p</em><sub>1</sub>(<em>ω</em>|<em>x</em>)</td>

   <td colspan="2" width="66"><em>p</em><sub>2</sub>(<em>ω</em>|<em>x</em>)</td>

   <td colspan="2" width="66"><em>p</em><sub>3</sub>(<em>ω</em>|<em>x</em>)</td>

   <td colspan="2" width="51">Mean</td>

   <td colspan="2" width="51">Max</td>

   <td colspan="2" width="51">Min</td>

   <td colspan="2" width="51">Prod</td>

  </tr>

  <tr>

   <td width="33">A</td>

   <td width="33">B</td>

   <td width="33">A</td>

   <td width="33">B</td>

   <td width="33">A</td>

   <td width="33">B</td>

   <td width="26">A</td>

   <td width="25">B</td>

   <td width="26">A</td>

   <td width="25">B</td>

   <td width="26">A</td>

   <td width="25">B</td>

   <td width="26">A</td>

   <td width="25">B</td>

  </tr>

  <tr>

   <td width="33">0.9</td>

   <td width="33">0.1</td>

   <td width="33">0.3</td>

   <td width="33">0.7</td>

   <td width="33">0.9</td>

   <td width="33">0.1</td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="33">0.9</td>

   <td width="33">0.1</td>

   <td width="33">0.2</td>

   <td width="33">0.8</td>

   <td width="33">0.1</td>

   <td width="33">0.9</td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="33">0.9</td>

   <td width="33">0.1</td>

   <td width="33">0.9</td>

   <td width="33">0.1</td>

   <td width="33">0.0</td>

   <td width="33">1.0</td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="33">0.7</td>

   <td width="33">0.3</td>

   <td width="33">0.3</td>

   <td width="33">0.7</td>

   <td width="33">0.2</td>

   <td width="33">0.8</td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="33">0.0</td>

   <td width="33">1.0</td>

   <td width="33">0.0</td>

   <td width="33">1.0</td>

   <td width="33">0.0</td>

   <td width="33">1.0</td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

   <td width="26"> </td>

   <td width="25"> </td>

  </tr>

 </tbody>

</table>

Table 1: Posterior predictions of three classifiers for a classification problem with two classes (A, B), for 4 objects. Complete the table by calculating the values assigned by the different combiners and determine what decision each combiner makes for each object.

<ol start="2">

 <li>Suppose you are given an x-ray image of a patient, and you are given the task of choosing between the following three ways of making a diagnosis (yes vs. no bronchitis):

  <ul>

   <li>An expert radiologist who has a probability of making a correct diagnosis with probability <em>p </em>= 0<em>.</em>85.</li>

   <li>A group of 3 doctors, each of which has <em>p </em>= 0<em>.</em>75.</li>

   <li>A group of 31 medical students, each of which has <em>p </em>= 0<em>.</em>6.</li>

  </ul></li>

</ol>

Please answer the following questions:

<ul>

 <li>In the second case, what is the probability that all three doctors give the correct answer? What is the probability that at least 2 doctors make the right call? Combining these results, what is the probability that this group makes the right decision based on majority voting?</li>

 <li>Come up with a general formula to calculate and/or code a simulation for the probability that <em>c </em>doctors with competence <em>p </em>make the correct decision by majority voting. Use it to calculate the probability of a correct decision for the group of medical students.</li>

 <li> Make a graph of the probability of a correct decision for various sizes of the jury and different competence levels (<em>p</em>) of the individual doctors.</li>

 <li>Who has the highest chance to make the correct decision: the radiologist, the group of doctors or the group of students? How big does the group of medical students need to be to make the probability of a correct decision (almost) equal to the prediction of the group of doctors?</li>

 <li> If you did your computations correctly, you will have found that the probability of making a correct decision converges to 1 if the group of students is large enough. This is obviously unrealistic, but why? Explain your answer in terms of ensemble learning.</li>

</ul>

<ol start="3">

 <li> Consider the following independent classifiers:

  <ul>

   <li>A strong classifier with the probability of making a correct decision with probability <em>p </em>= 0<em>.</em>75.</li>

   <li>An ensemble of 10 weak classifiers with probability <em>p </em>= 0<em>.</em>6.</li>

  </ul></li>

</ol>

<ul>

 <li>(5 points) Suppose that we combine the strong classifier in an ensemble with the 10 weak classifiers. What is the probability of a correct decision in a majority vote if each classifier’s vote has the same weight? Is the combined prediction better than that of the strong classifier alone?</li>

 <li>(5 points) Instead of using an equal-weight majority vote, we can use a weighted majority vote in which the strong classifier has a larger weight. Implement a function that computes, for a given weight <em>w </em>for the strong classifier, the probability that the weighted majority vote results in the correct decision. Make a graph of the probability of a correct decision given different weights. What is the optimal weight for the strong classifier?</li>

 <li>(5 points) The AdaBoost.M1 algorithm provides a formula to compute the classifier weights based on their error on the training set. Use the expected errors of the strong and weak classifiers to compute their respective weights. Compare the answer to the answer you found in the previous question.</li>

 <li>(5 points) Plot the weight given to a base-learner in the AdaBoost algorithm for different values of the error the base-learner makes. Explain what you see. What does it mean for these weights if we assume the base-learners are weak-learners? What happens to the weights if the probability of error of the base-learner is <em>&gt; </em>0<em>.</em>5 and why?</li>

</ul>

<ol start="4">

 <li>(15 points) In a few sentences, explain the differences between bootstrapping, random subspaces, and boosting.</li>

 <li>(20 points) For this exercise you can choose to use random forests or AdaBoost. (If you are interested, feel free to compare both methods, but this is not required for the assignment.)</li>

</ol>

For your method of choice, find out what widely used implementations are available in your favourite programming language and apply the method to a prediction problem you find interesting (see, for instance the <a href="https://archive.ics.uci.edu/ml/index.php">UCI </a><a href="https://archive.ics.uci.edu/ml/index.php">Machine Learning repository</a> for interesting datasets). Write a short description (min. 100 words) of your findings, including what dataset and implementation you used, how you set up your experiment, what the effect of different parameter settings was, what the performance was, which variables were important et cetera.