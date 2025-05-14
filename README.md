# Performance-Data
Dataset

Primary Data source: Opta STATS 

The Dataset contains names and data of 628 English Premier League footballers. It has 8 columns (two categorical and six numerical). The team and Player Name give identification details while appearances, substitutions, goals, penalties, yellow cards, Red Cards are numerical variables that represnt their on the pitch statistics. The numerical variables that represents variables are used by the clustering algorithm to assign cluster labels to each player.


Clustering Footballers based on Performance data
Import Necessary Libraries 

#importing the necessary libraries 

himport pandas as pd 
import numpy as np
import matplotlib.pyplot as plt 
import seaborn as sns
from scipy import stats
from sklearn.preprocessing import OneHotEncoder, StandardScaler
from sklearn.decomposition import PCA
import scipy.cluster.hierarchy as sch

import os
os.environ['OMP_NUM_THREADS'] = '1'

from sklearn.cluster import KMeans 

#reading the file into a dataframe
df = pd.read_csv('all_players.csv')

#viewing the first five rows 
df.head()

#viewing the number of columns and rows 
df.shape

#viewing the column data types 
df.info()

#checking for rows with null values 
df.isnull().sum()

#checking for rows with empty strings
df.eq(' ').sum()

#viewing summary of numerical columns 
df.describe()

#viewing correlation plot for all variables
sns.pairplot(df.iloc[:,[2,3,4,5,6,7]])
