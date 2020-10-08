NetflixStudy
==============================

Study of Netflix Ratings for Dr. Lei HanSheng of University of Texas RGV Masters Science in Computer Science.  

The purpose of the study is to develop a model for predicting movie ratings.

The training dataset has over 100million ratings from 480,179 of 17,770 movies.  Ratings were from 1 to 5.

This study uses the [Kaggle Netflix Prize dataset](https://www.kaggle.com/netflix-inc/netflix-prize-data).

Project Leader Steven Bowler 1oct2020.


### Program Documentation and Setup

Based on response time (main memory vs disk) it was decided to use pandas dataframes for all studies and modelling; therefore, the following references to MySQL loading and use were not used or relevant to this study.  The MySQL database may be used if the dataframes of raw data are found to be non-workable due to size or other limitation not yet identified.


##### MySQL reference, currently not used for study
Only way to load the massive 100million record netflixstudy training data to MySQL was thru MySQL command line thusly:
````
sb@DESKTOP-P48C40B c:\xampp\mysql\bin
# mysql.exe -u root --password
Enter password:

Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 432
Server version: 10.4.6-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> use netflixstudy
Database changed

MariaDB [netflixstudy]> load data local infile 'df.csv' into table ratings fields terminated by ',';
Query OK, 71833510 rows affected, 65535 warnings (6 min 47.817 sec)
Records: 71833510  Deleted: 0  Skipped: 0  Warnings: 71833513

MariaDB [netflixstudy]>
````


See references directory below for original project definition, based on [Cookiecutter](https://drivendata.github.io/cookiecutter-data-science/) data sciences framework, which can be executed from the bash prompt thusly:

````
cookiecutter https://github.com/drivendata/cookiecutter-data-science
````

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
