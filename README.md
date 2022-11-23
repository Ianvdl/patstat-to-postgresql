## Introduction

These scripts are based on those developed at altay-oz/load_patstat. 

The bulk downloads provided by EPO are served as batches of zip files. This
script assumes you have already downloaded and extracted these zip files, and
have a directory containing all the CSV files (the script will ask for this
directory - `CSV_FILES_DIR` - when run).

The script will also prompt for the password for the `patstat` postgresql user.
By default, a `patstat` user and database is assumed, and data is loaded into
the `public` schema. The script assumes that the postgresql database is running
on localhost.
