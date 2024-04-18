CSE 6242 Final Project, Spring 2024, Team 73
Visualizing Risk Factors and Career Impacts of Injuries Among MLB Pitchers
Developed by Sumair Shah, Sejal Dua, Tim Ehlenbeck, Jake Hlavaty, Leon Hu, Matthew Schulz


DESCRIPTION

The code found in this directory can be run locally to recreate the analysis completed as part of the project. The directory contains the following files:
 - analysis.ipynb >> 
 - combined_data.csv >> 
 - code.txt >> documentation for code portion of assignment 

The interactive visual tool is hosted on Tableau Public and can be found at the following link: 
https://public.tableau.com/app/...

INSTALLATION

I. DATA SCRAPING

The file 'analysis.ipynb' requires the following libraries installed:
 - pandas
 - matplotlib
 - seaborn
 - sklearn

 The following command can be used to install the libraries:
 python3 -m pip install pandas matplotlib seaborn sklearn


EXECUTION


VISUALS
-INJURIES PER GAME BY MONTH
    -Explanation: Bar chart showing the trend of average injuries per game per month, by season. 
    -Chart Elements: 
        -Columns: year & month of game date
        -Rows: average number of injuries per 100 games        
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -PRE_POST = 'PRE-INJURY'
        -DAYSRK = 1 (used to only include most recent game leading up to injury)        
-COMPARING DISTRIBUTION OF RECOVERY TIME FOR XXXX INJURIES TO OTHER COMMON INJURIES
    -Explanation: Histograms with the distribution of recovery time for a selected injury (or all injuries if no selection made) compared to two other common injuries.
    -Chart Elements: 
        -Columns: Recovery days bucketed into categories
        -Rows: Distinct count of Player-Injuries
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -PRE_POST = 'POST-INJURY'
        -DAYSRK = 1 (ensures only the return date is included)
-AVERAGE RECOVERY DAYS BY INJURY TYPE
    -Explanation: Table displaying the number of injuries, average recovery days, and estimated replacement cost by injury type.
    -Chart Elements: 
        -Columns: injury count, average recovery time, total replacement cost (average recovery time in days divided by 365 multiplied by the average annual mlb pitcher's salary)
        -Rows: injury type
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -PRE_POST = 'POST-INJURY'
        -DAYSRK = 1 (used to only include return date)
-pACWR LEADING UP TO INJURY
    -Explanation: Line chart of pACWR for the most recent 10 appearances leading up to the injury, for the selected pitcher.
    -Chart Elements: 
        -Columns: Game Date
        -Rows: pACWR
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -PRE_POST = 'PRE-INJURY'
        -Flag applied to only display data for the 10 appearances leading up to a pitcher's injury
-PITCH MOVEMENT
    -Explanation: Plots Pitch Movement before & after injury, to detect if there are any notable changes in the movement of a player's pitches. Pitch type is included, providing the user the option to highlight a specific pitch type to note changes or isolate pre/post injury pitch release.
    -Chart Elements: 
        -Columns: pfx x
        -Rows: pfx z
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -Flag applied to only display data for the 10 appearances before and after a pitcher's injury
-PITCH RELEASE
    -Explanation: Plots Pitch Release before & after injury, to detect if there are any notable changes in a player's release point. Pitch type is included, providing the user the option to highlight a specific pitch type to note changes or isolate pre/post injury pitch movement.
    -Chart Elements: 
        -Columns: Release Pos x
        -Rows: Release Pos y
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -Flag applied to only display data for the 10 appearances before and after a pitcher's injury
-PRE/POST-INJURY STATISTICS
    -Explanation: Shows key statistics for a player's performance, before & after injury. User has the
    option to highlight a specific pitch type to note changes.
    -Chart Elements: 
        -Columns: PRE_POST
        -Rows: Appearances, # of Pitches, Innings Pitched, Percentage of Strikes Thrown, Total Earned Runs, & ERA
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -Flag applied to only display data for the 10 appearances before and after a pitcher's injury
-PRE/POST-INJURY PITCHES THROWN BY TYPE
    -Explanation: Shows the percentage of all pitches thrown by pitch type for the 10 appearances leading up to and after injury.
    -Chart Elements: 
        -Columns: Sum of Pitches, displayed as a percentage of the total pitches thrown pre/post injury
        -Rows: Pitch Name, PRE_POST flag
    -Filters/Exclusions Applied:
        -Excludes all Preseason & Postseason games, as determined by MLB.com schedule
        -INJURY_LOCATION <> 'Covid'
        -Flag applied to only display data for the 10 appearances before and after a pitcher's injury
