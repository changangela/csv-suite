# csv-suite

## Usage

* ```nf``` returns the number of fields in the CSV file
* ```fc``` returns the column position of the specified header string (case insensitive)
* ```fr``` returns the row number of the header row in the CSV file
* ```xml``` parses entire CSV file and generates appropriate XML file
* ```json``` parses entire CSV file and generates appropriate JSON file
* ```qtrim``` trims line breaks within quotations and returns the generated file (required for awk line by line parsing)
```bash
$ awk -f nf "filename.csv"
$ awk -v fieldName="header string" -f fc "filename.csv"
$ awk -v numFields=[unsigned int] -f fr "filename.csv"
$ awk -v del="deliminator" -f qtrim "filename.csv" > "fileoutname.csv"
```
- run ```./convert.sh``` for direct conversion to XML
- run ```./convert.sh``` for direct conversion to JSON
```bash
$ awk -f qtrim in.txt > processed.txt
$ hr=$(awk -f fr processed.txt)
$ awk -v headerRow=$hr -f xml processed.txt > out.xml
$ rm processed.txt
```
