# CS257 - Team Project: Drug Usage in the United States
### Team Members: 
Rachel Punter
Eileen Liu
Ayobami Bidokwu
Tume Emmanuel Dzelamonyuy

## Project Overview
This project analyzes drug usage data across U.S. states and years. 
Users can search the dataset through the command line or through our Flask-based web interface.

## My Contribution (Ayobami Bidokwu)
- Migrated the full team project into my personal GitHub repository
- Replaced all team database credentials with my own local connection
- Cleaned and reorganized the entire codebase across all files
    - Removed unused code
    - Removed unnecessary comments
    - Removed outdated functions
    - Improved structure and clarity
- Assisted in running, updating, and maintaining all unit tests for the command-line and Flask components
- Added input validation to prevent website crashes when users submit incomplete searches
- Contributed to CSS and front-end layout, including:
    - Helping design the initial homepage
    - Helping design how the results page displays the data
    - Improving spacing, readability, and UI flow
- Contributed to HTML refactoring by helping move the project to a single shared data_results.html template used for all substance types

## features in Drug Usage data in US 

### Function Overview
- Command Line Usage:
<python3 command_line.py --substance "type substance" --year "chosen year">
<python3 command_line.py --substance "type substance" --state "chosen state">
- These commands return the drug usage data filtered by the selected variable.

### Search_by_year (substance, year)
- search_by_year() is called by the command line
    <python3 command_line.py --substance "type substance" --year "chosen year">
- argument from "chosen year" would be taken as input into this function
- return a list of sublists consisting ['state name: state', 'year number: year', 'age Range: age', 'data: numbers' ]

### Search_by_state (substance, state)
- search_by_state() is called by the command line
    <python3 command_line.py --substance "type substance" --state "chosen state">
- argument from "chosen state" would be taken as input into this function
- return a list of sublists consisting ['state name: state', 'year number: year', 'age]

### Error case for command lines
- Command line would return usage statement and an empty list [].

### Test 
- if wants to run the test files, (test_cl.py, test_datasource.py and test_flask_app.py) to test flask_app and command_lines, run
    <python3 -m unittest discover Tests/>
## Front-End Design Notes

### Scanability
- Users can easily click tabs to navigate to “Search by Year” or “Search by State”
- Improved spacing makes the text and headings easier to read

### Satisficing
- Buttons allow easy selection of substance type
- Homepage buttons help users quickly move to the search pages

### Muddling through
- Each function has its own page, making it easy to explore the data
- The results appear on separate pages to avoid clutter

## Refactoring
- Removed old commented-out code throughout the entire project
- Combined multiple old HTML files into one universal data_results.html
- Improved user navigation by simplifying layout and adding clear pathways between pages




Template for long-term team projects for CS257 Software Design
