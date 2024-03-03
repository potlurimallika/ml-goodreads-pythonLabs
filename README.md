![Cover Image](https://github.com/mat-tie/test/blob/88ecae2c0f01b78424d1be222e0417d92fe2c451/Project%20Cover%20Image)
# Book Rating Prediction Model
In this project, we implemented the use of a machine-learning model in order to predict book ratings. The steps were as follows:
* Importing & Cleaning the Dataset
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Modelling
  
Group Members: <a href="https://github.com/teaArchivist">Alexandra CURRAN</a>, <a href="https://github.com/mat-tie">Mathilde ROMAN</a>, <a href="https://github.com/Amiirah09">Amiirah CODABACCUS</a>, <a href="https://github.com/potlurimallika">Srimalika POTLURI</a>, <a href="https://github.com/rgsvm">Selvalakshmi RAMAGOPALAN</a>

## Dataset
The original dataset for this project was obtained from Goodreads book metadata. It is titled 1.books_original.csv. The columns are as follows:
| Data Columns             | Description |
| :---------------- | :---- |
| bookID       | A unique identification number for a book. |
| title         | The name under which the book was published. It may include the book universe and volume number if it is part of a series |
| authors    | The name of the author(s) and additional contributors for a book. Multiple authors/contributors are delimited with a '/' |
| average_rating | The average rating a book received in total |
| isbn | Another unique identification number for a book. It stands for International Standard Book Number.  |
| isbn13 | Another unique identification number for a book. It is a 13-digit ISBN to identify a book, instead of the standard 11-digit ISBN.  |
| language_code | A unique identifier for the language of a book e.g. 'eng' is standard for 'English'.  |
| num_pages | The number of pages a book contains.  |
| ratings_count | The total number of ratings a book received.  |
| text_reviews_count | The total number of written text reviews a book received. |
| publisher | The name of the publisher for a book. |

The original dataset was then merged to an additional dataset which was obtained from Mengting's Goodreads 2017 Data Dump. This merged dataset is found under 3.books_merged_series_format.csv.
> Mengting Wan, Julian McAuley, "[Item Recommendation on Monotonic Behavior Chains](https://mengtingwan.github.io/paper/recsys18_mwan.pdf)", in RecSys'18. [[bibtex](https://dblp.uni-trier.de/rec/conf/recsys/WanM18.html?view=bibtex)]
> Mengting Wan, Rishabh Misra, Ndapa Nakashole, Julian McAuley, "[Fine-Grained Spoiler Detection from Large-Scale Review Corpora](https://mengtingwan.github.io/paper/acl19_mwan.pdf)", in ACL'19. [[bibtex](https://dblp.uni-trier.de/rec/conf/acl/WanMNM19.html?view=bibtex)]


Two columns were then added to the dataset with the use of a small web-scraping script to obtain data from Open Library's API. These are found in the 3.books_merged_series_format.csv file:
| Data Columns             | Description |
| :---------------- | :---- |
| <b>format</b> | <b>The format for a book.</b> |
| <b>series exists</b> | <b>Indicates 1 if the book is part of a series, else indicates 0.</b> |

## Exploratory Data Analysis (EDA)
We mainly explored the relation of each feature to the target column i.e. average ratings column. We also looked at outliers for each feature.

## Feature Engineering
Based on how our EDA, we retained the num_pages, ratings_count, text_reviews_count and a calculated column called ratings_reviews_ratio.

## Modelling
We chose a regression model type to predict the average rating. We tested out four different models:
* Linear Regression
* Polynomial Regression
* Random Forest
* AdaBoost & Decision Tree

## Outcome
The Random Forest model outperformed all other models, with its predictions being relatively close to the actual values on average. Notably, the model returned a consistent R2 score of around 0.8.
# Getting Started

## Software Prerequisites
* Windows
* Python 3.10 Environment
* Jupyter Notebook

## Software Installation
* Open Anaconda Prompt
* Type and execute <code>conda create --name myenv python=3.10</code>
* Activate the new environment <code>conda activate myenv</code>
* Type and execute <code>conda install --file requirements.txt</code> to install the required packages.
* If an error occurs, run <code>conda install pywin32</code> before running the previous line again
* Open the Jupyter notebook <i>ML_final</i>
