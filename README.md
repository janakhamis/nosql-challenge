# Eat Safe, Love: MongoDB and Python Data Analysis

This project analyzes and manages data from UK food locations using MongoDB and Python. The data from the establishments.json file is imported into a MongoDB database for storage and queried using Python's PyMongo library. The project includes cleaning data, updating databases, and doing exploratory analysis to answer critical questions for the fictional magazine Eat Safe, Love (Challenge 12).

---

## Setup Instructions

### Prerequisites
- MongoDB installed locally or accessible via a remote server.
- Python 3.x installed with the following libraries:
  - `pymongo`
  - `pandas`
  - `pprint`

### Database Setup
1. **Import Data**  
   Use the following command to import the data into MongoDB:
   ```bash
    mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json

2. **Database Details**
- **Database Name**: `uk_food`
- **Collection Name**: `establishments`

---

## Notebooks

### `NoSQL_setup_starter.ipynb`
#### Features:
1. **Added a New Restaurant**
   - Inserted a new document for a restaurant, *Penang Flavours*, into the database.
2. **Updated the BusinessTypeID**
   - Retrieved the `BusinessTypeID` for "Restaurant/Cafe/Canteen" and updated the new restaurant's document.
3. **Removed Establishments in Dover**
   - Identified and deleted all documents where the `LocalAuthorityName` was "Dover."
4. **Data Cleaning**
   - Converted latitude and longitude fields from strings to decimals.
   - Converted the `RatingValue` field from strings to integers.

---

### `NoSQL_analysis_starter.ipynb`
#### Exploratory Analysis:
1. **Hygiene Score of 20**
   - Queried establishments with a hygiene score of 20.
   - Converted the results into a Pandas DataFrame and displayed the first 10 rows.
2. **High Ratings in London**
   - Found establishments in London with a `RatingValue` greater than or equal to 4.
   - Used regex to handle variations in the Local Authority name.
   - Converted results to a DataFrame and displayed the first 10 rows.
3. **Top 5 Establishments Near "Penang Flavours"**
   - Retrieved establishments with a `RatingValue` of 5 within 0.01 degrees of the latitude and longitude of *Penang Flavours*.
   - Sorted results by the lowest hygiene score.
   - Displayed the top 5 results.
4. **Local Authorities with Hygiene Score of 0**
   - Used the aggregation framework to:
     1. Match establishments with a hygiene score of 0.
     2. Group results by Local Authority and count the establishments.
     3. Sort by the count in descending order.
   - Converted the results into a DataFrame and displayed the top 10 Local Authorities.

---

## Results and Insights
- The data cleaning process ensured consistency in data types for analysis.
- Key insights were found about establishments with high ratings, poor hygiene scores, and local authority areas with the most problematic establishments.
- Developed reusable and efficient queries to explore the data.

---

## How to Run

### 1. Install Dependencies
      pip install pymongo pandas


### 2.	Import the data:
    mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json

### 3.	Open the notebooks:
-	NoSQL_setup_starter.ipynb: For database setup and updates.
-	NoSQL_analysis_starter.ipynb: For data analysis.


