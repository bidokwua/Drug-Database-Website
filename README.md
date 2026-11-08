# Drug Usage in the United States

A CS257 (Software Design) team project. Our team built a command-line tool and a Flask web app for searching drug and substance usage data by U.S. state and by year.

**Team:** Rachel Punter, Eileen Liu, Ayobami Bidokwu, Tume Emmanuel Dzelamonyuy

## What it does

Users pick a substance and then filter the data by year or by state, either from the command line or in the browser.

- **Substances:** alcohol, cocaine, marijuana, tobacco
- **Years:** 2002 to 2018
- **Age groups:** 12 to 17, 18 to 25, and 26 and older, with population, counts, and rates for each

Alcohol and tobacco tables include past-year and past-month use. Cocaine has past-year use. Marijuana also includes new users.

## Setup

The app reads from a PostgreSQL database, so you need to set one up first.

1. Install Python 3, PostgreSQL, and the Python packages:
   ```
   pip install flask psycopg2-binary
   ```
2. Create a database and a user with a password, then create the tables and load the data from the project folder:
   ```
   psql -h localhost -U your_username your_database_name -f Data/Createtable.sql
   psql -h localhost -U your_username your_database_name -c "\copy Alcohol FROM 'Data/alcohol.csv' WITH (FORMAT csv)"
   psql -h localhost -U your_username your_database_name -c "\copy Cocaine FROM 'Data/Cocaine.csv' WITH (FORMAT csv)"
   psql -h localhost -U your_username your_database_name -c "\copy Marijuana FROM 'Data/Marijuana.csv' WITH (FORMAT csv)"
   psql -h localhost -U your_username your_database_name -c "\copy Tobacco FROM 'Data/Tobacco.csv' WITH (FORMAT csv)"
   ```
   The CSV files have no header row, and each table should end up with 867 rows.
3. Copy `ProductionCode/psql_config.example.py` to `ProductionCode/psql_config.py` and fill in your own database name, user, and password. That file is gitignored and should never be committed.

## Using it

### Command line

```
python3 command_line.py --substance "chosen substance" --year "chosen year"
python3 command_line.py --substance "chosen substance" --state "chosen state"
```

`--substance` is required for both searches. Any other combination of arguments prints a usage message.

### Web app

```
python3 flask_app.py
```

The app runs on port 5221. Routes:

| Route | Page |
|-------|------|
| `/` | Homepage |
| `/start_explore` | Entry page for exploring the data |
| `/about` | Background on the data |
| `/year` and `/state` | Search pages |
| `/year/<year>/substance/<substance>` | Results by year and substance |
| `/state/<state>/substance/<substance>` | Results by state and substance |

Unknown routes show a custom 404 page, and unexpected server errors show a custom 500 page. Both result pages share a single `data_results.html` template.

## Project layout

```
command_line.py     Command-line interface
flask_app.py        Flask web app
ProductionCode/     DataSource class and the database connection settings
templates/          HTML templates
static/             CSS and images
Tests/              Unit tests
Data/               CSV files and Createtable.sql
Website Demo/       Screenshots of the web app
Proposal.md         Project proposal and dataset links
user_analysis.md    CIDER analysis of users, benefits, and harms
```

## Tests

```
python3 -m unittest discover Tests/
```

The app and the command line connect to the database when they are imported, so finish the database setup before running the tests.

## My part (Ayobami Bidokwu)

- Moved the team project into my personal GitHub repository
- Helped design the homepage and the layout of the results page
- Helped improve spacing, readability, and navigation in the front end
- Helped consolidate the separate result pages into the single shared `data_results.html` template
- Helped run, update, and maintain the unit tests for the command-line and Flask components

## Front-end design notes

- **Scanability:** tabs for "Search by Year" and "Search by State" and clearer spacing make pages easier to skim.
- **Satisficing:** buttons for choosing a substance and for moving between search pages keep the path to results short.
- **Muddling through:** each search has its own page, and results open on a separate page to avoid clutter.

## Known limits

The dataset only covers 2002 to 2018 and three age groups, so results should not be treated as a complete picture of drug use. Our CIDER analysis in `user_analysis.md` lists further limits, including English-only text and color-contrast concerns.