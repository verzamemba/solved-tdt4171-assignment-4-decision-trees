Download Link: https://assignmentchef.com/product/solved-tdt4171-assignment-4-decision-trees
<br>
In this exercise you are to implement a decision tree classifier. You are <strong>not </strong>allowed to use an implementation of decision tree classifiers from libraries such as sklearn. You are <strong>not </strong>allowed to copy code you have found online. <strong>Read the entire exercise before writing any code or answering any questions.</strong>

<ol start="18">

 <li>Implement a decision tree that can support categorical variables. This algorithm is described in Figure 18.5 in AIMA. Use <em>information gain </em>as the Importance Use your implementation to train a decision tree on the Titanic dataset (see below). Some of the columns in the dataset are continuous attributes, and cannot be used with this implementation. Which are these? Test your model on the test set and print your accuracy. Add your decision tree to the PDF manually, using Graphviz, or with some other software.</li>

 <li>Extend your implementation to also support continuous variables. Train this model on the Titanic dataset again, now also using the continuous attributes you left out in <strong>a)</strong>. Test the model again on the test set and print the accuracy of the predictions. Add your decision tree to the PDF manually, using Graphviz, or with some other software.</li>

 <li>Discuss the results from <strong>a) </strong>and <strong>b)</strong>; is the performance difference what you expected? What might be done to improve the performance of the decision tree classifier on the test set? Suggest at least 2 changes that might be made to the algorithm that could improve performance. Argue why your changes <em>could </em>improve performance. You do not have to show that it actually does improve accuracy on the Titanic dataset.</li>

</ol>

<h2>Continous variables</h2>

Splitting on continuous variables is different from categorical variables. You cannot make a branch for all possible values, instead we find the best value to split on and make two branches, one for numbers smaller than the split, and one for numbers larger than the split. Because you are only making two branches at each split for continuous attributes, typically we let the decision tree split on those attributes multiple times. For your implementation in <strong>b) </strong>we only require you to be able to split on the continuous attributes <em>once</em>, just like with the categorical attributes. This makes it so that the tree will never become deeper than the number of attributes in the data.

<h2>Titanic dataset</h2>

The Titanic dataset contains information on passengers aboard RMS Titanic. The idea is to predict the survival of each passenger based on other collected information.

The dataset contains the following columns:

<table width="512">

 <tbody>

  <tr>

   <td width="79">Survival:</td>

   <td width="433">Did the passenger survive (0=No, 1=Yes)</td>

  </tr>

  <tr>

   <td width="79">Pclass:</td>

   <td width="433">Ticket class (1=1st, 2=2nd, 3=3rd)</td>

  </tr>

  <tr>

   <td width="79">Name:</td>

   <td width="433">The name of the passenger</td>

  </tr>

  <tr>

   <td width="79">Sex:</td>

   <td width="433">Sex</td>

  </tr>

  <tr>

   <td width="79">Age:</td>

   <td width="433">Age in years</td>

  </tr>

  <tr>

   <td width="79">SibSp:</td>

   <td width="433">Number of siblings/spouses aboard the Titanic</td>

  </tr>

  <tr>

   <td width="79">Parch:</td>

   <td width="433">Number of parents/children aboard the Titanic</td>

  </tr>

  <tr>

   <td width="79">Ticket:</td>

   <td width="433">Ticket number</td>

  </tr>

  <tr>

   <td width="79">Fare:</td>

   <td width="433">Passenger fare</td>

  </tr>

  <tr>

   <td width="79">Cabin:</td>

   <td width="433">Cabin number</td>

  </tr>

  <tr>

   <td width="79">Embarked:</td>

   <td width="433">Port of embarkation (C=Cherbourg, Q=Queenstown, S=Southampton)</td>

  </tr>

 </tbody>

</table>

Not all columns are suitable predictors, however. Use only the columns you find suitable for predicting survival rate and explain why you disregard the other attributes.

Data is split into two files:

<ul>

 <li>Training set (train.csv)</li>

 <li>Test set (test.csv)</li>

</ul>

The training and test sets includes all columns listed above. Furthermore, some of the columns contain missing values. You do not need to implement support for missing values, so you can disregard these attributes when training your decision tree.

We have given you a modified version of the Titanic dataset available at <a href="https://www.kaggle.com/c/titanic/data">https:</a>

<a href="https://www.kaggle.com/c/titanic/data">//www.kaggle.com/c/titanic/data</a><a href="https://www.kaggle.com/c/titanic/data">.</a>

<h2>Tips</h2>

Use a dataframe library to load the csv files. Pandas is a great option if you are using Python. Other Pandas methods that can come in handy when implementing the decision tree include <em>DataFrame.value </em><em>counts</em>, <em>DataFrame.groupby</em>, <em>DataFrame.map</em>, and <em>DataFrame.sort values</em>.

<h1>2       Missing Values</h1>

One of the columns in the Titanic dataset contained missing values. We chose to not use these columns at all when we implemented out decision tree, even though only very few values were missing. This means that we missed out on a lot of information that could have made our decision tree perform. Suggest at least two methods that we could have used to handle missing data either during training or prediction. Describe your proposed solutions either in text or with pseudo code. Discuss the advantages and disadvantages of your methods. What assumptions are you making?