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

## Release coverage

This repository contains scripts tested for the following PATSTAT versions (see the releases in this repository for corresponding versions):
* Spring 2022*
* Fall 2022*
* Fall 2023
* Spring 2024

Releases marked with an asterisk have one or more point releases available for bugfixes. Always use the latest release for your version of PATSTAT.

### Help needed

If you have access to the versions of the data for which we do not yet have coverage, please respond to the open issue to indicate whether the release works, or whether changes are needed. If you are able, please submit a pull request with the changes needed for compatibility.

Many thanks to the contributors who have donated their time and expertise to this project (in sequential order):

1. @complexly (spelling error fix)
2. @vlejd (fall 2023 version)
3. 2. @vlejd (spring 2024 version)

## HOWTO

1. Run the `insert_data_to_patstat.sh` shell script. Enter the values as
   prompted. The script will create the schema and load the data from the CSV
   files, and then create rudimentary indexes. The script may run for a few
   hours.
2. Run the `count_rows_in_patstat.sh` script. This script will count the rows in
   each patstat table. Compare those with the values provided in the EPO dump,
   under the `TestScripts` directory to verify that the database is complete.

## Reference

The ERD for this database structure matches that given in the EPO data
catalogue, included here for reference:

![patstat-erd](https://github.com/user-attachments/assets/3d4dbe0f-d0f2-4ef7-a533-55767c92e8e0)

