The Scenario: "The Rogue Buyer" Detection
The Client: A major wholesale distributor in India.
The Problem: The client has a database of 440 regular buyers (Hotels, Restaurants, and Retailers). While most clients follow predictable purchasing patterns, they suspect a few "Rogue Buyers" are placing unusual, high-volume orders that don't fit any category. These outliers are causing inventory shortages for regular customers.
The Goal: 1. Group regular customers into logical segments for targeted marketing.
2. Identify and "isolate" the rogue buyers so they don't skew the business data.
The Dataset: Wholesale Customers
This is a classic dataset from the UCI Machine Learning Repository.
Features: Annual spending on Fresh, Milk, Grocery, Frozen, Detergents_Paper, and Delicassen.
Challenge: The data has significant outliers and non-spherical clusters.


Your Technical Task
Step 1: Preprocessing (The Foundation)
Clustering is distance-based. If "Fresh" spending is 50,000 and "Delicassen" is 500, the algorithm will ignore the Delicassen data.
Action: Apply StandardScaler to normalize the features.
Step 2: K-Means (Segmenting the Regulars)
Action: Use the Elbow Method to find the optimal $K$.
Observation: Notice how K-Means struggles with outliers. It will likely force a "Rogue Buyer" into a regular group, pulling the cluster center toward the outlier and making the group less accurate.
Step 3: DBSCAN (Catching the Rogues)
Action: Use a K-Distance Plot to find the optimal eps (Epsilon).
Action: Run DBSCAN.
Key Insight: Unlike K-Means, DBSCAN will label outliers as Noise (-1). These are your "Rogue Buyers."
