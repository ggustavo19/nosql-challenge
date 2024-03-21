<html>
  
</head>
<body>
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
    <h2>Part 2: Update the Database</h2>
    <ol>
        <li>Use NoSQL_setup_starter.ipynb for this section of the challenge.</li>
        <li>The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. Make the following changes to the establishments collection:</li>
        <li>An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.</li>
        <li>Update the new restaurant with the BusinessTypeID you found.</li>
        <li>The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.</li>
        <li>Some of the number values are stored as strings, when they should be stored as numbers.
            <ol>
                <li>Use update_many to convert latitude and longitude to decimal numbers.</li>
                <li>Use update_many to convert RatingValue to integer numbers.</li>
            </ol>
        </li>
    </ol>
    <h2>Part 3: Exploratory Analysis</h2>
    <ol>
        <li>Use NoSQL_analysis_starter.ipynb for this section of the challenge.</li>
        <li>Some notes to be aware of while you are exploring the dataset:</li>
        <li>Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors.</li>
        <li>Which establishments have a hygiene score equal to 20?</li>
        <li>Which establishments in London have a RatingValue greater than or equal to 4?</li>
        <li>What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?</li>
        <li>How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.</li>
    </ol>
</body>
</html>
