# beer_ratings

This project was created using data from ruthgn's 'Beer Profile and Ratings Dataset' on Kaggle at https://www.kaggle.com/datasets/ruthgn/beer-profile-and-ratings-data-set

This dataset contains a wide range of data types, however I wanted to focus on: 
  1) what styles scored the best overall in these ratings, 
  2) whether ABV correlated with overall score, 
  3) and examine whether having more or fewer reviews had an impact on average brewery score.

Using pandas, numpy, scipy, matplotlib, and seaborn, I grouped data from the large original dataframe and aggregated relevant pieces into new dataframes that I was able to use for plotting and comparison. These new smaller dataframes also allowed me to apply Pearson correlation to see whether things like ABV and overall score were actually correlated.

## Overall Score for Style

After some EDA, I created a new dataframe called `style_data` that contained each style in our original data and found the mean and standard deviation of overall scores, and the number of reviews for each style. I then pulled the top 10 styles and the bottom 5 to create a box and whisker plot using seaborn to help me get a feel for comparing the average scores of those styles and the spread.

The top scoring styles had tighter groupings with the exception of lambic, while all of the bottom 5 styles had notably larger standard deviations. I inferred from this that beers fitting one of the top styles tend to do well just by being grouped into those styles, whereas beers fitting into the lower style categories averaged low but there were occasionally individual beers that succeeded in scoring fairly high overall.

Further work could be done here to group similar styles together (like pulling all the IPA styles together), or only showing styles that had a large number of ratings with the assumption that these would be more relevant than something like Happoshu with only 118 ratings.

## ABV and Overall Score Correlation

Using fairly straightforward scatterplots and fitting trend lines over them, I was able to see if there appeared to be any correlation between ABV and overall score. Because ABV mostly affects mouthfeel, I did the same for just the mouthfeel score.

I found a weak positive correlation between ABV and overall score, and a weak to middling correlation between ABV and mouthfeel. This basically fit my assumption that there would be some effect but not strong enough to really sway scores, but also that this effect would be stronger for the mouthfeel part of the score. In fact, I would imagine that most of the effect seen in overall score is from the incorporation of mouthfeel there.

## Does having more reviews increase or decrease a brewery's average score?

I was curious about this question because it seems to me I often see products with high ratings but a low number of participants, whereas I will trust a product more if it maybe has a slightly lower rating but significantly more reviewers. I wanted to see if that effect existed in this brewery data.

