# Documentation for the NFT analysis with machine learning. 

In this project, we create machine learning models using Twitter and NFT features to predict NFT price and number of sales. 

Before running the code in the notebook, first download the NFT and Twitter data from https://tinyurl.com/NFTValuation . From the Data folder, place 'Final_Dataset_filtered.csv', 'Opensea_Features_Filtered.csv', and 'Twitter_Features_Filtered.csv' in the same folder with this jupyter notebook. 

## Datasets

The data was created and utilized by the paper "TweetBoost: Influence of Social Media on NFT Valuation" (Kapoor, 2021)

'Opensea_Features_Filtered.csv' is the NFT data between January 1st, 2021 to March 30, 2021 from OpenSea, a web3 marketplace for NFTs. There are 62,997 NFTs with unique permalink. There are 48 columns in the dataset, and these are some of the key features. 'total_sales': the total number of the NFT sales, 'total_supply': how many NFTs were created, 'num_owners': the number of people who own the NFTs, 'average_price': the average price at which the NFT was bought and sold,  'is_presale': if the asset is available for pre-sale, 'transfer': number of times the asset is transferred between owners, 'market_cap': the value of the company that created the NFT, 'price_label': Ordinal data for the average price with 5 logarithmically combined classes, where class 1 is between $10 and $100, class 2 is between $100 and $1000, and so on. 

'Twitter_Features_Filtered.csv' is the Twitter data linked with the NFT data. Some NFTs have multiple tweets by different users, and they are aggregated as mean, median, min, or max. Key features are 'followers_count_mean': average number of followers of users who tweeted about the NFT, 'friends_count_mean': average number of friends, 'listed count': The number of accounts who have added the account to their lists, 'has nft': Boolean value that's true if any user tweeted about the NFT has 'nft' in their username, 'n_likes': number of likes', 'n_replies': number of replies, 'n_hashtags': number of hashtags.

'Final_Dataset_filtered.csv' is a dataset that has all the tweets that mention NFTs. More than one of these tweets might mention the same NFT. The dataset has most of the key features mentioned above.It also has 'avg_listing_price': the price that the NFT sales start. 


We first create scatter plots to visualize relationship between the quantitative variables using matplotlib. Then, we calculatae the correlation and p-values of the variables using the scipy stats library.

Machine learning model 1: Random Forest classifier to predict price label
We use train the ML with some of the features mentioned above to predict the price label of an NFT. We rank the importance of the features in order. We used grid search model for hyperparameter tuning. The final accuracy was around 0.82.

Machine learning model 2: 

