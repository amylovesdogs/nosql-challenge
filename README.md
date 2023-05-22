# nosql-challenge
DU Data Analysis, Module 12, NoSQL Challenge
The setup: The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, *Eat Safe, Love*, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Part 1: Database and Jupyter Notebook Set Up
Data is stored in **Resources/establishments.json**, a json file. Load the database into MongoDB using the following command at the command line: `mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json`

The python code in **NoSQL_setup.ipynb** sets up the uk_food database with an establishments collection.

## Part 2: Update the Database
 **NoSQL_setup.ipynb** updates the establishments collection as follows:
1. Adds a new Halal restaurant called Penang Flavours, putting it under the business type Restaurant/Cafe/Canteen.
2. Removes any establishments from withing the Dover Local Authority.
3. Converts latitude, and longtitude from strings to decimal numbers.
4. Converts RatingValue from strings to integer numbers.

## Part 3: Exploratory Analysis
**NoSQL_analysis.ipynb** explores the following questions for *Eat Safe, Love* magazine:
1. Which establishments have a hygiene score equal to 20?
2. Which establishments in London have a RatingValue greater than or equal to 4?
3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
Unless otherwise stated, for each question:

For all questions, except #3, count_documents is used to display the number of documents contained in the result.

The first document in the results is displayed using pprint.

The results are converted to a Pandas DataFrame, the number of rows in the DataFrame are printed, and  the first 10 rows display (except in #3 where 5 rows are shown).

Notes:
* RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
* The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.


