Improved Search Metadata Tag Generator v2.0.2
Nicholas Boni
Staff Content Curator
January 26, 2023

INSTRUCTIONS

1. Tag your portfolio in the Excel workbook.
2. Copy columns DOCUMENTID, STRIPE_S,GROUPING1_S,GROUPING2_S,GROUPING3_S,GROUPING4_S,GROUPING5_S,TAGSGENERIC_S into a .txt file and save it to the same directory as NewUntaggedQueryGenerator.exe. Make sure that groupings.txt also exists in the same directory.
3. Run NewUntaggedQueryGenerator.exe.
4. Open "output.txt". This file is organized by the tag you are entering, and a list of all docIDs to which you will apply that tag. This list of docIDs is prepared into a query, which you can enter directly into Search Metadata.
5. Open Search Metadata and set the proper configuration.
6. Copy the first query into the search bar and click Search.
7. Click Select All >> Bulk Update.
8. Choose the appropriate grouping, and enter the tag into the New Value box. Click OK.
9. Click Select All >> Save.

Repeat steps 6-9 until you reach the end of query.txt.

10. Enter the last query in output.txt, ALL DOC IDS TAGGED.
11. Click Select All >> Add Doc(s).

KNOWN ISSUES

Because "sw" is both a stripe_s value and a grouping1_s value, the program gets confused and always classifies it as stripe_s. When tagging documents as sw, double-check to make sure you are assigning sw to the correct tag grouping.



I made groupings.txt by hand from Curator Tag Collaboration Hierarchy.xlsx, so it needs to be manually updated whenever a new tag is added to the spreadsheet.

To update groupings.txt:

1. Open Curator Tag Collaboration Hierarchy.xlsx.
2. Open a blank .txt file.
3. In the .txt file, type the grouping name you are copying over (e.g., stripe_s)
4. Copy only the values (not the header) from the "Tag" column in Curator Tag Collaboration Hierarchy.xlsx. They should show up with one tag per line.
5. Beneath the final tag for that grouping, add a *.

Repeat steps 3-5 until all groupings have been added.

Example:

stripe_s
tbd
rf
sw2
test
sw
custed
daq
embed
acad
ast
*
grouping1_s
hw
sw
service
...

COMMON ISSUES AND TROUBLESHOOTING

If the exe window just disappears, there was an unhandled error in the execution of the program. To see the error:

1. Shift+Right Click in the directory where the exe lives >> Open PowerShell window here.
2. Enter .\newuntaggedquerygenerator.exe
3. Reproduce the issue.

A Python error message should pop up in the terminal.

IndexError: list index out of range
This likely means that your input data txt file does not have enough columns. Make sure that when you copy your Excel columns into your .txt file, you include ALL of the following columns (even if they have blank entries):
DOCUMENTID STRIPE_S GROUPING1_S GROUPING2_S GROUPING3_S GROUPING4_S GROUPING5_S TAGSGENERIC_S



If you have an issue that is not detailed here, take a screenshot of the error in the terminal and send it to Nicholas Boni on Teams or at nicholas.boni@ni.com .