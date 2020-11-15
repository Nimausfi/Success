import os
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import itertools
import collections
import tweepy as tw
import nltk
from nltk.corpus import stopwords
import re
import networkx
import warnings
warnings.filterwarnings("ignore")

sns.set(font_scale=1.5)
sns.set_style("whitegrid")


tweets = open ('Add your file here (.txt is preferred)')

all_tweets = [tweet for tweet in tweets]

all_tweets[:5]

def remove_url(txt):

    return " ".join(re.sub("([^0-9A-Za-z \t])|(\w+:\/\/\S+)", "", txt).split())


all_tweets_no_urls = [remove_url(tweet) for tweet in all_tweets]
all_tweets_no_urls[:5]

ex_list = ["Word1", "word1", "word1", "word2", "word2", ","]


set(ex_list)

# Note how capitalization impacts unique returned values
words_list = ["Word1", "word1", "word1", "word2", "word2", ","]

# Make all elements in the list lowercase
lower_case = [word.lower() for word in words_list]

lower_case

set(lower_case)

all_tweets_no_urls[0].split()

all_tweets_no_urls[0].lower().split()

words_in_tweet = [tweet.lower().split() for tweet in all_tweets_no_urls]
words_in_tweet[:2]



all_words_no_urls = list(itertools.chain(*words_in_tweet))

# Creating the counter
counts_no_urls = collections.Counter(all_words_no_urls)

counts_no_urls.most_common(10)

clean_tweets_no_urls = pd.DataFrame(counts_no_urls.most_common(10),
                             columns=['words', 'count'])

clean_tweets_no_urls.head()
print (clean_tweets_no_urls)

fig, ax = plt.subplots(figsize=(8, 8))

# Plotting the bar graph
clean_tweets_no_urls.sort_values(by='count').plot.barh(x='words',
                      y='count',
                      ax=ax,
                      color="purple")

ax.set_title("Common Words Found in Tweets (Including All Words)")

plt.show()
