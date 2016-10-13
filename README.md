# Logfile report
Simple command line report based on logfile from one day.

## Usage
Just use it like:
***REMOVED***
./report date
***REMOVED***
Where date is day from which you want to generate report in YYYY-MM-DD format.
For example:
***REMOVED***
./report 2016-10-10
***REMOVED***

## How it works
When running script for the first time with day it'll download log archive from
Papertrail service and unzip it to `./log_files` directory. Directory is
gitignored so don't worry about accidentally adding log file to git repo. After
getting file there's simple report generated with awk.


