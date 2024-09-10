# FTC Comment Harvesting

Download comment attachments submitted to FTC in response to the Advanced Notice of Rulemaking on Commercial Surveillance and Data Security

## Getting Started

### Pre-requisites
- Install Python 3.11.9 ([MacOS](https://www.python.org/ftp/python/3.11.9/python-3.11.9-macos11.pkg), [Windows](https://www.python.org/ftp/python/3.11.9/python-3.11.9-amd64.exe))
- Install [`pip`](https://pip.pypa.io/en/stable/installation/)

### Installation
First, clone this repository.  Then, at the command line, navigate to the folder containing this file and initialize a new virtual environment by executing the following lines of code:

`python -m venv .venv`  
`source .venv/bin/activate` (if MacOS/Unix) OR `.venv\Scripts\activate` (if Windows)

Finally, install dependencies into the newly created virtual environment by running this additional line:

`pip install -r requirements.txt`


## Execution Notes
Open and run `parse.ipynb`.  It will create a `/downloads` subdirectory and save all attachments there.  Downloading will take approximately 2 hours to complete.  Check the generated results file (`results.csv`) to identify any issues with the download process.

## Data Notes

A copy of the downloaded attachments is available on OneDrive at `YLS Data/Documents/Efforts/ftc-comments`

There are two issues of note when working with the downloaded attachments.

1. By default, attachment files are renamed to match the corresponding `Document ID` in the source dataset (`data.xlsx`).  If multiple attachments were listed for a comment submission (i.e., each row in the source dataset), sequential suffixes were appended to each attachment file.  For example, FTC-2022-0053-0164 has two attachment files listed in the source dataset, which are saved respectively as FTC-2022-0053-0164_1 and FTC-2022-0053-0164_2
2. Some of the rows in the original do not appear to start with a conventional `Document ID` beginning with FTC-, but may nonetheless still have attachments listed.  These should be reviewed and, if necessary, downloaded manually.
