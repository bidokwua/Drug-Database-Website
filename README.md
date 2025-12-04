# CS257-Team Project: Drug Usage in the United States
Team Members: Rachel Punter, Eileen Liu, Ayobami Bidokwu, Tume Emmanuel Dzelamonyuy

## Project Overview
This project analyzes drug usage data across U.S. states and years. Users can search the dataset through the command line or through our Flask-based web interface.

## My Contribution (Ayobami Bidokwu)
- Migrated the project into my personal GitHub repository
- Replaced all team database credentials with my own local database connection
- Cleaned and organized the entire codebase, removing unused code, unnecessary comments, and outdated functions across all files
- Assisted in running, updating, and maintaining the unit tests for the command-line functions and Flask routes
- Added input validation to prevent crashes when users submit empty queries
- Contributed to the CSS and overall front-end layout, including:
    - Helping design the initial homepage
    - Helped to the design of the results page and how the data is visually displayed to users
- Contributed to the refactoring of HTML by supporting the move to a single data_results.html template used for all substance types

## features in Drug Usage data in US 
- command lines:
    <python3 command_line.py --substance "type substance" --year "chosen year">
    <python3 command_line.py --substance "type substance" --state "chosen state">
    - Those command line carry our searching data that relates to wanted variables.
### Search_by_year
- search_by_year() is called by the command line
    <python3 command_line.py --substance "type substance" --year "chosen year">
- argument from "chosen year" would be taken as input into this function
- return a list of sublists consisting ['state name: state', 'year number: year', 'age Range: age', 'data: numbers' ]
### Search_by_state
- search_by_state() is called by the command line
    <python3 command_line.py --substance "type substance" --state "chosen state">
- argument from "chosen state" would be taken as input into this function
- return a list of sublists consisting ['state name: state', 'year number: year', 'age]

### Error case for command lines
- Command line would return usage statement and an empty list [].

### Test 
- if wants to run the test files, (test_cl.py, test_datasource.py and test_flask_app.py) to test flask_app and command_lines, run
    <python3 -m unittest discover Tests/>

### Scanability
- You can easily look at the page and just click one of the tabs to go to the search by year or state pages
- There is less space between the text and headings

### Satisficing
- Clickable buttons on the search pages to easily choose a substance type
- You can easily click one of the buttons at the top of the homepage to go to the search pages

### Muddling through
- The different pages allow users to easily click through data (data display comes up on different pages and there are different pages for how to search through the data)





Template for long-term team projects for CS257 Software Design
