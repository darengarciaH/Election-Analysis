# Election-Analysis

## Overview of Election Audit
Tom is a Colorado Board of Elections employee who is looking to audit congressional district election data and reporting statistics such as the list of candidates, their percentage share of the vote, the number of votes that each candidate obtained, and the winner of the election. His manager, Seth, wants him to automate the process using Python instead of the usual Excel. Furthermore, Tom needs to report statistics reported at the county level, including turnout for each county, the percentage share of votes attributed to a particular county, and the county with the largest turnout. 

## Election Audit Results

### Results by County
For this congressional district election, a total of 369,711 votes were cast. In this congressional district, we have three counties that report voter turnout: Denver, Jefferson, and Arapahoe counties. 
  * Denver County reported the ***largest*** **vote count** with **82.8% of the vote**, totaling **306,055 votes**. 
  * Jefferson County cast a total of **38,855 votes**, which accounts for **10.5% of the total vote**.
  * Arapahoe County reported the lowest vote count with **6.7% of the total vote**, totaling **24,801 votes**.

### Results by Candidate
The votes that came in from these three counties were cast towards three candidates: Diana DeGette, Charles Casper Stockham, and Raymon Anthony Doane.
  * Diana DeGette was the ***ample*** **winner**, having received **73.8% of the total vote** and amassing **272,892 votes**. 
  * Charles Casper Stockham came in a distant second with **23.0% of the total vote**, with **85,213 votes**. 
  * Raymon Anthony Doane only came in with **3.1% of the vote** for a total of **11,606 votes**. 

### Election Results
<img width="305" alt="Screen Shot 2021-11-11 at 1 18 53 PM" src="https://user-images.githubusercontent.com/92702922/141356059-6cbb6cd5-c5ae-441d-8bc8-12d51db4738e.png">

## Election Audit Summary
Since this script reads in a comma-separated value dataset that displays ballot ID's, candidate choice, and county for every vote cast, this script can easily be replicated and slightly modified to be applied for future elections, as it outputs voting breakdown by government unit and candidate, as well as the government unit with the largest turnout and the candidate winner of the race. Simple modifications include:

* modifying the file names that are input and output in the script, as seen here: `
  # Add a variable to load a file from a path.
  file_to_load = os.path.join("Resources", "election_results.csv")
  # Add a variable to save the file to a path.
  file_to_save = os.path.join("analysis", "election_results.txt")`

* *potentially* altering lines in the script that reference specific columns of data to make sure they read the correct candidate or county name for every row of data (votes), as shown below, depending on the format of the rows and columns of the file that is read into our script. Here, `row[1]` references the second column of the dataset for any particular row (which in this case is the name of the county) while `row[2]` references the third column of the data for any row (in this case, the name of the candidate). `
  # Get the candidate name from each row.
  candidate_name = row[2]
  # Extract the county name from each row.
  county_name= row [1]`
  
* renaming variables as the ones seen below to reflect Colorado counties, cities, and senatorial districts for local, municipal, and even presidential elections, also depending on the format of the data that is read into our script: `
county_list = []
county_votes= {}
winning_county= ""
winning_turnout= 0
winning_cpercentage= 0`

With these simple modifications, this code can easily be applied to reading datasets that have a large number of votes regardless of the type of election, as it will display the necessary information that is required for any level of election.
