# Oh365 User Finder

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/M4M03Q2JN)

<p align="center">
  <img src="https://github.com/dievus/Oh365UserFinder/blob/main/images/oh365userfinder1.jpg" />
</p>

Oh365UserFinder is used for identifying valid o365 accounts and domains without the risk of account lockouts.  The tool parses responses to identify the "IfExistsResult" flag is null or not, and responds appropriately if the user is valid.  The tool will attempt to identify false positives based on response, and warn the user to increase timeouts between attempts.  

Oh365UserFinder can also easily identify if a domain exists in o365 using the -d or --domain flag.  This saves the trouble of copying the url from notes and entering it into the URL bar with the target domain.

## Usage
Installing Oh365UserFinder

```git clone https://github.com/dievus/Oh365UserFinder.git```

Change directories to Oh365UserFinder and run:

```pip3 install -r requirements.txt```

This will run the install script to add necessary dependencies to your system.

```python3 Oh365UserFinder.py -h```

This will output the help menu, which contains the following flags:

```-h, --help - Lists the help options```

```-e, --email - Required for running Oh365UserFinder against a single email account```

```-r, --read - Reads from a text file containing emails (ex. -r emails.txt)```

```-w, --write - Writes valid emails to a text document (ex. -w validemails.txt)```

```-c, --csv - Writes valid emails to a CSV file (ex. -c validemails.csv)```

```-t, --timeout - Sets a pause between attempts in seconds (ex. -t 60)```

```-d, --domain - Checks if the listed domain is valid or not (ex. -d mayorsec.com)```

```--verbose - Outputs test verbosely```

Examples of full commands include:

```python3 o365UserFinder.py -e example@test.com```

```python3 Oh365UserFinder.py -r emails.txt -w validemails.txt```

```python3 Oh365UserFinder.py -r emails.txt -w validemails.txt -t 30 -v y```


### Notes
Make note that Microsoft does have some defense in place that can, from time to time, provide false positives in feedback.  If you suspect that this is occurring take a pause in testing, and return and increase the duration between attempts using the -t flag.

![Oh365UserFinderScan](/images/o365UserFinderscan.png)

### Acknowledgements
This project is loosely inspired by a tool named o365Creeper developed by Korey Mckinley that was last supported in 2019, and developed in Python2.  
