# Logfile report
Simple command line report based on logfile from one day.

## Papertrail token
In order for `client` to be able to get files from Papertrail it needs to have
correct API token. You can get it from Papertrail dashboard. Then just put it in
`.token` file in root directory. For example:

```
echo "YOUR_TOKEN" > .token
```

## Usage
Just use it like:
```
./report date
```
Where date is day from which you want to generate report in YYYY-MM-DD format.
For example:
```
./report 2016-10-10
```

## How it works
When running script for the first time with day it'll download log archive from
Papertrail service and unzip it to `./log_files` directory. Directory is
gitignored so don't worry about accidentally adding log file to git repo. After
getting file there's simple report generated with awk.

## Known issues
- some requests are marked as failed by heroku (those with `code=XX`) and are
  filtered out right now. It's `~3000-4000` requests per day.
