# Match Records & League Datasets

This sub-directory contains the structured datasets required to run the Serie A statistical analysis.

### Content
* **Season 2008-09 Match Logs**: CSV/TXT files containing every match played during the season, including home/away teams and final scores.
* **Metadata**: Reference files for team IDs and stadium codes used to link match results with specific clubs.

### Data Format & Structure
The analysis engine expects data in a specific delimited format. Each entry typically follows this structure:
`Match_ID; Home_Team; Away_Team; Home_Goals; Away_Goals`

### Usage for Analysis
These files are used as the primary input for the `DigitalSerieA` scripts. To maintain the accuracy of the standings, ensure that no duplicate match records are introduced and that goal counts are formatted as integers.
