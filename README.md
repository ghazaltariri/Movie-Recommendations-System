# Movie Recommender System:

* Project: Movie recommender based of data from the [MovieLens dataset](http://grouplens.org/datasets/movielens/)
* Data: Movies information, user information, and user's ratings 
* Algorithm's final goal: Suggest movies to users!


* The movies data and users data: `data/movies.dat` and `data/users.dat`
* The ratings data: `data/training.csv`
* The users' ratings: Broken into a training and test set

# Solution:

Using a Non-Negative Matrx Factorization technique (run via pyspark) user-movie ratings are inferred based on user's similarity to other users and movies's similarity to other movies.

The NMF technique, cannot be applied for new-movies and new-users. This is known as a cold-start issue. 
To solve that issue, I used popularity algorithm for new users and an NLP-based content similarity algorithm for new-movies.
For creating NLP (content-based) features, in similarity algorithm, for new-movies, additional metadata was used (by downloading [The Movies Dataset](https://www.kaggle.com/rounakbanik/the-movies-dataset/version/7))

### Note on running your script with Spark

`recommender.py` script relies on spark, you may need to use the script `run_on_spark.sh` to execute the code.
In a terminal, use: `run_on_spark.sh src/run.py` with arguments to run the recommender.
The `src/submit.py` doesn't need to run on spark, as it simply reads the result file produced by `run.py`.

