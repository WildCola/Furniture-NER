# Furniture-NER
NER used for detecting product names from furniture web stores

## About my solution
- model: for this task, I decided on using bert-base-uncased; initially I tried using distilbert-base-uncased, which is a smaller and faster version of BERT, but I got much better results on the larger model
- data annotation: in order to create the data for training and testing the model I used the matcher from the spaCy library and had ChatGPT generate a list of furniture products to add to my matcher, afterward I read the HTML data from the given URLs, cleaned it and used the matcher to label the furniture products; for labeling I decided on the BIO format because some of the products were made up of multiple consecutive words and this was a very simple way of resolving that issue
- data imbalance: the data was extremely imbalanced towards the Outside class as most of the text from the web pages was not product names; to address this issue, I used a weighted loss function where weights were automatically set based on the class frequencies
