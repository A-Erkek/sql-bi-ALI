
Command-line tool that cleans messy CSV files: empty rows, extra spaces, duplicates.
## Usage
python cleaner.py data/sample.csv outputs/clean.csv
Cities are capitalised (lyon -> Lyon)
## Cleaning steps
1. Drop empty rows
2. Strip whitespace in cells
3. Capitalise city names
4. Remove duplicate rows
