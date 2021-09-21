# tune-sklearn-xgboost

This is to prepare for PyBay talk 2021.

The problem is based on Kaggle safe driver [contest](https://www.kaggle.com/c/porto-seguro-safe-driver-prediction). The goal is to predict if a driver will file an insurance claim in the next year. 

The original dataset has 57 columns. For the sake of time, I removed about half of the less important ones.

The demo will go like this:
* run a default xgboost classifier and see the result
* incentivize that there are so many hyperparameters to tune and GridSearchCV and RandomizedSearchCV can be improved by more advanced search and scheduling algorithms.
* run a hpo with a bunch of parameters (this currently takes about 40 minutes, as would be with any serious hpo)
* plan to just issue the run and direct the audience to notice a few things from the log lines
    *  resource allocations, by the line "Resources requested: 2.0/40 CPUs, 0/0 GPUs, 0.0/57.2 GiB heap, 0.0/4.66 GiB objects"
    *  hyperband algorithm, trials are paused and restored all the time
    *  Current best trial

* plan to show the pre-captured [result](https://gist.github.com/xwjiang2010/c63ffdce0d4a7c8aa6fe2cf09e342bcb)
* plan to run the best_model_ through test set and show the new result. Should improve the gini_score by around 5%.
