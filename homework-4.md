Homework 4: Bags, Forests, Boosts, oh my
================
Eric Stromgren
2/28/2019

Problem 1
---------

Problem 7 from Chapter 8 in the text. To be specific, please use a sequence of `ntree` from 25 to 500 in steps of 25 and `mtry` from 3 to 9 for by 1.

Answer 1
--------

\`\`\`{r}
=========

\# Construct the train and test matrices
========================================

set.seed(1101)
==============

train = sample(dim(Boston)\[1\], dim(Boston)\[1\]/2)
====================================================

X.train = Boston\[train, -14\]
==============================

X.test = Boston\[-train, -14\]
==============================

Y.train = Boston\[train, 14\]
=============================

Y.test = Boston\[-train, 14\]
=============================

bag\_boston\_25\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 25)
=============================================================================================================================

bag\_boston\_50\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 50)
=============================================================================================================================

bag\_boston\_75\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 75)
=============================================================================================================================

bag\_boston\_100\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 100)
===============================================================================================================================

bag\_boston\_125\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 125)
===============================================================================================================================

bag\_boston\_150\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 150)
===============================================================================================================================

bag\_boston\_175\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 175)
===============================================================================================================================

bag\_boston\_200\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 200)
===============================================================================================================================

bag\_boston\_225\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 225)
===============================================================================================================================

bag\_boston\_250\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 250)
===============================================================================================================================

bag\_boston\_275\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 275)
===============================================================================================================================

bag\_boston\_300\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 300)
===============================================================================================================================

bag\_boston\_325\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 325)
===============================================================================================================================

bag\_boston\_350\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 350)
===============================================================================================================================

bag\_boston\_375\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 375)
===============================================================================================================================

bag\_boston\_400\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 400)
===============================================================================================================================

bag\_boston\_425\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 425)
===============================================================================================================================

bag\_boston\_450\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 450)
===============================================================================================================================

bag\_boston\_475\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 475)
===============================================================================================================================

bag\_boston\_500\_3 &lt;- randomForest(x\_training, y\_training, xtest = x\_testing, ytest = y\_testing, mtry = 3, ntree = 500)
===============================================================================================================================

plot(1:500, rf.boston.p*t**e**s**t*mse, col = "green", type = "l", xlab = "Number of Trees",
============================================================================================

ylab = "Test MSE", ylim = c(10, 19))
====================================

lines(1:500, rf.boston.p.2*t**e**s**t*mse, col = "red", type = "l")
===================================================================

lines(1:500, rf.boston.p.sq*t**e**s**t*mse, col = "blue", type = "l")
=====================================================================

legend("topright", c("m=p", "m=p/2", "m=sqrt(p)"), col = c("green", "red", "blue"),
===================================================================================

cex = 1, lty = 1)
=================

bag\_boston
===========

\`\`\`

Problem 2
---------

Problem 8 from Chapter 8 in the text. Set your seed with 9823 and split into train/test using 50% of your data in each split. In addition to parts (a) - (e), do the following:

1.  Fit a gradient-boosted tree to the training data and report the estimated test MSE.
2.  Fit a multiple regression model to the training data and report the estimated test MSE
3.  Summarize your results.
