<html lang="en">
<body>
    <p>The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.</p>
    <h2>Part 1: Database and Jupyter Notebook Set Up</h2>
    <ol>
        <li>Use NoSQL_setup_starter.ipynb for this section of the challenge.</li>
        <li>Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.</li>
        <li>Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).</li>
        <li>Create an instance of the Mongo Client.</li>
        <li>Confirm that you created the database and loaded the data properly:
            <ol>
                <li>List the databases you have in MongoDB. Confirm that uk_food is listed.</li>
                <li>List the collection(s) in the database to ensure that establishments is there.</li>
                <li>Find and display one document in the establishments collection using find_one and display with pprint.</li>
            </ol>
        </li>
        <li>Assign the establishments collection to a variable to prepare the collection for use.</li>
    </ol>
    <h3>Part 2: Update the Database</h3>
    <ol>
        <li>Use NoSQL_setup_starter.ipynb for this section of the challenge.</li>
        <li>The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. Make the following changes to the establishments collection:
            <ol>
                <li>An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis.</li>
                <li>Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.</li>
                <li>Update the new restaurant with the BusinessTypeID you found.</li>
                <li>The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.</li>
                <li>Some of the number values are stored as strings, when they should be stored as numbers.</li>
                <li>Use update_many to convert latitude and longitude to decimal numbers.</li>
                <li>Use update_many to convert RatingValue to integer numbers.</li>
            </ol>
        </li>
    </ol>
    <h4>Part 3: Exploratory Analysis</h4>
    <p>Eat Safe, Love has specific questions they want you to answer, which will help them find the locations they wish to visit and avoid.</p>
    <p>Use NoSQL_analysis_starter.ipynb for this section of the challenge.</p>
    <p>Some notes to be aware of while you are exploring the dataset:</p>
    <ul>
        <li>RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.</li>
        <li>Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.</li>
        <li>The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.</li>
    </ul>
    <p>Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors:</p>
    <ol>
        <li>Which establishments have a hygiene score equal to 20?
            <ol>
                <li>Use count_documents to display the number of documents contained in the result.</li>
                <li>Display the first document in the results using pprint.</li>
                <li>Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.</li>
            </ol>
        </li>
        <li>Which establishments in London have a RatingValue greater than or equal to 4?
            <ul>
                <li>Hint: The London Local Authority has a longer name than "London" so you will need to use $regex as part of your search.</li>
            </ul>
        </li>
        <li>What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
            <ul>
                <li>Hint: You will need to compare the geocode to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.</li>
            </ul>
        </li>
        <li>How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
            <ul>
                <li>Hint: You will need to use the aggregation method to answer this.</li>
            </ul>
        </li>
    </ol>
</body>
</html>

