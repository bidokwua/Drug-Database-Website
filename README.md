# Drug Usage in the United States

A CS257 (Software Design) team project. Our team built a command-line tool and a Flask web app for searching drug and substance usage data by U.S. state and by year.

**Team:** Rachel Punter, Eileen Liu, Ayobami Bidokwu, Tume Emmanuel Dzelamonyuy

## What it does

Users pick a substance and then filter the dataset by year or by state, either from the command line or in the browser.

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
ProductionCode/     DataSource class with the search functions
templates/          HTML templates
static/             CSS and static files
Tests/              Unit tests
Data/               Dataset files
Proposal.md         Project proposal and dataset links
user_analysis.md    CIDER analysis of users, benefits, and harms
```

## Tests

```
python3 -m unittest discover Tests/
```

## My part (Ayobami Bidokwu)

- Moved the team project into my personal GitHub repository
- Helped design the homepage and the layout of the results page
- Helped improve spacing, readability, and navigation in the front end
- Helped consolidate the separate result pages into the single shared `data_results.html` template
- Helped run, update, and maintain the unit tests for the command-line and Flask components

## Front-end design notes

- **Scanability:** tabs for "Search by Year" and "Search by State" and clearer spacing make pages easier to skim.
- **Satisficing:** buttons for choosing a substance and for moving between search pages keep the path to results short.
- **Muddling through:** each search has its own page and results open on a separate page to avoid clutter.

## Known limits

The dataset only covers specific years and age groups, so results should not be treated as a complete picture of drug use. Our CIDER analysis in `user_analysis.md` lists further limits, including English-only text and color-contrast concerns.