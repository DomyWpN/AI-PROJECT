# AI-PROJECT

SOCIAL MEDIA SHARES - Domenico Trimarchi, Guglielmo Filangieri, Simone Damasco



INTRODUCTION

Our project is based on impersonating machine learning engineers who were
hired by a company to find a way to maximize shares of its social media posts.
The company gave us an entire data frame containing all the characteristics of
each post(e.g. images, videos, words), feedback(positive or negative) and also
the date and day of publication(e.g. monday, tuesday...).



METHODS

As a first step, we imported all the packages we will need for a matter of order
and space in the cells. Thanks to Pandas we can know more about the dataframe
delivered to us by the company and thanks to the 'shape' function we
immediately notice that we have in front of us a medium-small dataset giving us
already some idea about the three models to try but we cannot take anything for
granted, in fact as first thing we started with the Dataset cleaning.
Also, since our target (shares) is a continuous number, we immediately deduced
that we should opt for regressors.
We considered it a priority to do a check on the null values and eventually
remove them, but fortunately the graph we have depicted (heatmap) shows that
there are none.

Outliers are points that are very far from any other, and to prove if there's any, we
used a box plot (FIGURE) to see them graphically and as we expected, there
were. How do we define whether a point is an outlier or not? Well, we chose the
points that are below the 10% and above the 90%, we thought of this ratio after
see that if we would have chosen the typical 25% and 75% we would have lost
too many points We didn’t use the auto-function because there is some data that
is described in a binary way(1 positive, 0 negative) such as the data of a post
(e.g.Sunday, Monday…) so we opted for a function that finds the index of the
outliers skipping the binary ones and, of course, the shares.
The choice of removing the outliers before the splitting comes from the fact that,
as we said at the beginning, we're testing linear regression as one of the models
and we know for fact that it doesn’t handle outliers at all.

We then decided to start the creation of the Train/Test split.
As we will see in the next steps, our results were quite odd, with MSE much higher that we expected,
therefore we still decided to continue with the implementation of our models as while testing for a lot of time,
we couldn't find our mystakes.



EXPERIMENTAL DESIGN

The regression models we thought of are first and foremost Linear Regression,
the most classic one although to try to make it as efficient as possible we had to
put our hands on the dataframe, mainly because of the issue of outliers, which
deflect the regression in a calculating way.
As a second, given the numerous data we have and not all linearly dependent,
we opted for a Polynomial Regression hoping it would handle better than Linear
because our data were not linearly-dependent(unexpected result).
As a third, we wanted to try for neural networks (wich was fun but actually hard to implement), as we discarded K-NN for two
main reasons: The slowness and the excessive number of calculations it would
have to do(given the dataset); we also discarded Random Forest as, although it
is robust and it is less prone to overfitting, it gives us a very general solution but
our aim is to be as more efficient/precise as possible.
However, we kept in mind that Support Vector Regressor is a really performing model,
but we already chose the Linear Regression as a linear model and also we thought that Neural Links would’ve helped us more in our work of precision.
For the Polynomial Regression and Neural Network model we referred and used some of the codes in the links below:


Polynomial

https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html
https://towardsdatascience.com/polynomial-regression-with-scikit-learn-what-you-should-know-bed9d3296f2

Feed-Forward Neural Network

https://keras.io/api/models/model_training_apis/
https://keras.io/api/models/sequential/
https://machinelearningmastery.com/grid-search-hyperparameters-deep-learning-models-python-keras/


To evaluate the performance of our models we used the MSE (Mean Square Error),
which measures the average of the squares of the errors (average squared difference between the estimated values and the actual value).



RESULTS

Unfortunately our results far more higher than expected. 
Our Linear Regression model got an MSE of: 52184659.45909838,
the model was the fastest of all 3 and the on with the "better" result, also during multiple iterations.
Our Plynomial Regressor, instead got an MSE of: 88915310.01345773, far higher than the Linear Regression but also a lot more slower!
The last one, Feed-Forward Neural Network was the most unpredictable, the MSE in this case is: 52145520.0; 
but in other cases surpassed the value of 100000000.00

We decided therefore to use our Linear Regression model as the best one, to compare the perfomances,
isolating the 20 features with the highest scores and using them to train and test again our model.
The result of the new MSE was: 222559148.98206106. 
Actually higher (and slower) than the previous one.

Ultimately we wanted to test the behaviour of a single feature in predicting the shares,
We isolated the feature "kw_avg_avg", wich was the one with the most relevance.
Our scatterplot shows with the Red Dots our expected shares and with the blue rows our predicted shares.
The graph doesn't tell us much about the performance of our model and we cannot guarantee the accuracy of our results.



CONCLUSIONS

As a conclusion, we cannot say that the results are what we expected,
however we know that we chose to work on some algorithms that were not perfectly suitable,
but the important thing is to have seen and tested the value of the programs,
the problem will be the data presentations (cleaning and splitting) of the dataset(?),
likely, since the machine cannot make mistakes in calculations. 
In any case, the important thing is to have tested and take the results as teaching and experience.



HOW WE WORKED

Given the different distances between us members, we worked mostly remotely together and simultaneously on call and then formatting everything into a single file,
we gave each other a lot of feedbacks and alternatives for different codes trying to bring in all the different and invidual ideas about possible procedures and development of the project.
