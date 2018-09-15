---
layout: default
title: Importing data
---

# Importing Data

# 1. Get some data

*Oh, look! It's a Harry Potter dataset! We haven't seen one of those for a while ...*

**Table 1.** Box office history for all Harry Potter movies. 

| Release Date | Movie                                         | Production Budget | Domestic Opening Weekend | Domestic Box Office | Worldwide Box Office |
|--------------|-----------------------------------------------|------------------|------------------------|--------------------|---------------------|
| Nov 16, 2001 | Harry Potter and the Sorcerer’s Stone         | $125,000,000     | $90,294,621            | $317,575,550       | $974,755,371        |
| Nov 15, 2002 | Harry Potter and the Chamber of Secrets       | $100,000,000     | $88,357,488            | $261,987,880       | $878,979,634        |
| Jun 4, 2004  | Harry Potter and the Prisoner of Azkaban      | $130,000,000     | $93,687,367            | $249,538,952       | $796,688,549        |
| Nov 18, 2005 | Harry Potter and the Goblet of Fire           | $150,000,000     | $102,685,961           | $290,013,036       | $896,911,078        |
| Jul 11, 2007 | Harry Potter and the Order of the Phoenix     | $150,000,000     | $77,108,414            | $292,004,738       | $942,943,935        |
| Jul 15, 2009 | Harry Potter and the Half-Blood Prince        | $250,000,000     | $77,835,727            | $301,959,197       | $935,083,686        |
| Nov 19, 2010 | Harry Potter and the Deathly Hallows: Part I  | $125,000,000     | $125,017,372           | $295,983,305       | $960,283,305        |
| Jul 15, 2011 | Harry Potter and the Deathly Hallows: Part II | $125,000,000     | $169,189,427           | $381,011,219       | $1,341,511,219      |
| Nov 18, 2016 | Fantastic Beasts and Where to Find Them       | $180,000,000     | $74,403,387            | $234,037,575       | $803,798,342        |




# 2. Preparing your data

## Set up your spreadsheet the best way

 - First row is usually for the column names (header).
 
 - First column is often used to identify the sampling unit.
 
 - Comments and meta-data kept in separate file or as commented-out rows at top of datasheet.

 - See Best Practice lecture on [data management](http://www.simonqueenborough.info/R/best-practice/dataManagement.pdf).
 

## Data needs to be readable by R

 - Column names: short vs long, spaces vs periods
 
 - Avoid symbols that have specific meaning in R: comments  ``` # ```, and single quote/apostrophe ``` ' ```.
 
 - Avoid using the column delimiter within field (e.g., TAB or comma).
 
 - Avoid other symbols unless within text fields:  ``` ? ```,  ``` $ ```,  ``` % ```,  ``` ^ ```,  ``` & ```,  ``` * ```,  ``` ( ```,  ``` ) ```,  ``` - ```,  ``` , ```,  ``` < ```,  ``` > ```,  ``` / ```,  ``` | ```,  ``` \ ```,  ``` [ ``` , ``` ] ``` , ``` { ```,  ``` } ```.

 - Use international standards for specific fields (e.g., [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) for dates: YYYY-MM-DD).

 - Check numeric field for extra characters, spaces etc. that would indicate to R that it is character.
 
 - Check empty fields: are they empty or do they have invisible white space?

 - Either remove text fields with more than one word, or prepare to specify the column separator when you read the data in.
 
 - Check for extra columns/rows in the spreadsheet.

 - Make sure that any missing values in your data set are indicated with NA (or your code of choice).


| ReleaseDate | Movie                                         | ProductionBudget_USD | DomesticOpeningWeekend_USD | DomesticBoxOffice_USD | WorldwideBoxOffice_USD |
|--------------|-----------------------------------------------|------------------|------------------------|--------------------|---------------------|
| Nov 16, 2001 | Harry Potter and the Sorcerers Stone         | 125000000     | 90294621            | 317575550       | $974,755,371        |
| Nov 15, 2002 | Harry Potter and the Chamber of Secrets       | 100000000     | 88357488            | 261987880       | 878979634        |
| Jun 4, 2004  | Harry Potter and the Prisoner of Azkaban      | 130000000     | 93687367            | 249538952       | 796688549        |
| Nov 18, 2005 | Harry Potter and the Goblet of Fire           | 150000000     | 102685961           | 290013036       | 896911078        |
| Jul 11, 2007 | Harry Potter and the Order of the Phoenix     | 150000000     | 77108414            | 292004738       | 942943935        |
| Jul 15, 2009 | Harry Potter and the Half-Blood Prince        | 250000000     | 77835727            | 301959197       | 935083686        |
| Nov 19, 2010 | Harry Potter and the Deathly Hallows: Part I  | 125000000     | 125017372           | 295983305       | 960283305        |
| Jul 15, 2011 | Harry Potter and the Deathly Hallows: Part II | 125000000     | 169189427           | 381011219       | 1,341511219      |
| Nov 18, 2016 | Fantastic Beasts and Where to Find Them       | 180000000     | 74403387            | 234037575       | 803798342        |



## Use a standard file format

 - Specific data often have specific standard format (e.g., phylogenetic tree as [Newick](http://evolution.genetics.washington.edu/phylip/newicktree.html), nucleotide sequence as [FASTA](http://zhanglab.ccmb.med.umich.edu/FASTA/)).

 - For tabular data use plain-text files:
    - Non-proprietary.
    - Can be opened in any almost any software.
    - Future-compatible.


## Known issues with Excel (and other spreadsheet software)

 - **Auto-complete** can introduce errors (especially with numbers).

    - Type out numbers fully.
    - 
 
 - **Auto-formatting** Excel will often reformat input, especially dates.
 
    - Use separate columns for YYYY, MM, DD, HH, MM, etc. that could be auto-formatted 
 
 
 - **Significant figures** Excel will not always save, paste, or display the full number in a cell. 
 
    - Make cells as wide as they need to be to fit entire values inside.
    - Copy and paste to text file.


See [here](http://scienceblogs.com/principles/2009/03/18/why-does-excel-suck-so-much/) and [here](http://www.burns-stat.com/documents/tutorials/spreadsheet-addiction/) for more details on Excel and spreadsheets. TL;DR: Do not use spreadsheets for anything apart from entering data!


 - - -
 
 
# 3. Read your data in to R

R has several functions to read data in.

The ``` read.table() ``` function has the fewest defaults.

The others set typical defaults for the separator/delimitor character, and the decimal character.

You can easily set these in a call to ``` read.table() ```, too.


## File type: .txt | delimitor: white space (one or more spaces, tabs, newlines or carriage returns) | no header

``` read.table() ```

```
df <- read.table("my_data.txt", header= TRUE)
```


## File: .csv | delimitor: comma | decimal: period | header

``` read.csv() ```

```
df <- read.csv("my_data.csv")
```

## File: .csv | **delimitor: semi-colon** | **decimal: comma** | header

``` read.csv2() ```

```
df <- read.csv2("my_data.csv")
```


## File: .txt | delimitor: tab | **decimal: period** | header

``` read.delim() ```

```
df <- read.delim("my_data.txt")
```


## File: .txt | delimitor: tab | **decimal: comma** | header

``` read.delim2() ```

```
df <- read.delim2("my_data.txt")
```






 - - -
 
# 4. Common issues importing data

## i. The number of columns are not what you expected

Often a separator problem (i.e., R is using a different separator character/s to the separator you think/want).

*Solution*: Specify the ``` sep = "" ``` argument to your ``` read.foo() ``` function call.

## ii. There are a **lot** more columns than you expected!

And often these cells are filled with NA's.

Did you save.as within Excel?

It is likely you have some whitespace entered into cells to the right of the data in the spreadsheet, and Excel saved all those columns as well.

*Solution*: Select and delete all columns to the right of your data OR (better) copy and paste data into a plain-text file.


## iii. White space in factors

You should have already removed extra white space from your data.

To check:

 - In Excel sort *all* the data by the factor columns and check that both ends are the same.
 - In R, run ``` table() ``` on the columns of interest, this will highlight any differences.
 
Further, the default separator character in R (``` sep = "" ```) is generic white space, i.e., one or more spaces, tabs, newlines or carriage returns. If you change the separator, this default is gone.


*Solution*: Check your data for white space and remove it before you read it in, or you can set another argument to TRUE (``` strip.white = TRUE ```), to remove extra white space.


## iv. Columns are not the kind of data you expect

If R sees numbers in a column, it will assume that it is numeric or integer.

If any other character is present, it will assume it is a character or factor variable.

Thus any comments or text (e.g., "missing", "about 2", "?", etc.), will cause the entire numeric column to be treated as character.

Use ``` summary() ``` or ``` table() ``` to check all your columns carefully. Are they correct?

*Solutions*:

 - Specify or correct missing value characters.
 - Specify or correct decimal character (period vs comma).



 - - -
 
 # Further Reading
 
 Borer, et al. 2009. [Some simple guidelines for  effective data management](http://www.zoology.ubc.ca/biol548/readings/borer%20et%20al%202009%20besa%20-%20effective%20data%20management.pdf). *Bulletin of the ESA* **90**, 205--214.
 
 White et al. 2013. [Nine simple ways to make it easier to (re)use your data](http://queens.scholarsportal.info/ojs/index.php/IEE/article/view/4608). *Ideas in Ecology & Evolution* **6**. doi: https://doi.org/10.4033/iee.v6i2.4608 
 
 
 


