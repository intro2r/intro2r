---
layout: default
title: Data Management
---


# Data Management

The various issues concerned with 'data' are becoming increasingly important, because of the increasing emphasis on reproducibility and replicability in science.

Making data available to reviewers and others allows them to verify your analyses and also re-use data for other purposes, in meta-analyses or other projects that you had not thought of.

Most public funding agencies (e.g., NSF [USA], NERC [UK]) require deposition of data in a data archive, as do many reputable journals. There are, also, good reasons for not making your data available, such as if they contain sensitive information about endangered species or personal information about interviewees.

Ensuring that your data are collected, managed, and stored well is therefore another skill you will have to learn as data scientists.

There are several steps in this process, that will also help you as you manage and analyse and write up your data.


## Collecting data

Quality control during data collection is important because often it is either not possible, or prohibitively expensive in terms of time and money to collect the data again.

Key things to consider:

 - **Logistical issues** Can you get all the samples you need? Is there enough time (poor data may be worse than no data)? Are there any health and safety issues?,

 - **Instrument calibration** Ensure that you know your instruments (and field techs!) are calibrated and checked regularly,

 - **Data collection templates or data sheets** Establish a good system and layout for quick and easy collection,

 - **Meta-data about the data** Are there conditions that may have affected the data?,

 - **Observer error**  Record who collected that data and check if you need to account for this,

 - **Data entry errors** Both in terms of collection (e.g., paper and pencil vs. digital) as well as entering data into a database (maybe use double-entry).


## Processing data

Once you have your raw data, it will likely need to be processed into some form of digital spreadsheet or database. 

First, keep all raw data in an **un-writeable** format. You may need to go back to it. Take digital copies of all paper field notes.

 - **Plan and design a database structure** to organize files and folders,

 - **Use consistent file format** (see below),

 - **Atomize data** One piece of data per entry/cell,

 - **Use plain-text characters and files** To ensure future-compatibility of files,

 - **Describe data in a 'readme' file** Include meta-data and information on each column,

 - **Use code to process data** Correct data entry errors, change codes, re-structure, etc. using code (e.g., R), so that you do not touch the raw data, *and* have a record of all changes made.


### File format

Use non-proprietary formats as much as possible (.txt, .csv, ...), to ensure that anyone (including you!) will be able to use and open them.


### File and folder names

Should be unique, descriptive, ordered, consistent.

Avoid spaces, which can cause problems with software.

Dates should be ISO: YYYY-MM-DD, to ensure correct ordering.


### Folders and directory structure

Organise your files in a sensible, planned, and consistent way.

Draw a folder map to aid others.


```
─ Flowering
  |
  ├─ raw_data
  |   ├─ 2015
      |    └─2015-flowering.csv
  |   ├─ 2016
  |   └─ 2017
  ├─ processed_data
  |   ├─ script-to-process-raw-flowering-data.R
  |   └─ data_all_yrs.csv
  ├─ results
  └─ figures
      └─ plot1.png
```

### Consider version control

Version control can either be via software such as Git.

Or you can impliment a simplified version yourself:

 - Add a date to each file name (YYYY-MM-DD).

 - Keep a separate file with a record of all changes associated with each file.


More details [here](../best/managing-data-files.pdf)


## Documenting data

It is important to include as much information *about* the data as possible, so that they can be understood and interpreted correctly in the long term.

Information may include: project aim, objective, and hypotheses; personnel; sponsors and funders; methods and instruments; standards used; software; known issues and limitations; intellectual property.

This kind of information is frequently referred to as *meta-data*, and is required by all data archives.




## Storing data

Data should be stored in a way that will ensure it can be found and used again.

This means using open and non-proprietary formats, as well as high redundancy and multiple back-ups (online, external devices, hard copies), and a system of responsibility for doing so.





## Sharing data

All the above systems will ensure that your data can easily be found by you and others, and easily shared, archived, and re-used.

Consider depositing data in an online archive.


 - - -



## References

Borer et al. 2009. Some simple guidelines for effective data management. *Bulletin of the Ecological Society of America*. [PDF](https://www.nceas.ucsb.edu/files/news/ESAdatamng09.pdf)

British Ecological Society. 2014. *A Guide to Data Management in Ecology and Evolution*. [Link](https://www.britishecologicalsociety.org/publications/guides-to/)

Cook et al. 2001. Best practices for preparing ecological data sets to share and archive. *Bulletin of the Ecological Society of America*. [Link](https://www.jstor.org/stable/20168543?seq=1#page_scan_tab_contents)  [Presentation](https://www.dataone.org/sites/all/documents/best_pract_cook_20100729.pdf)

Cook et al. Updated. *Best Practices for Preparing Environmental Data Sets to Share and Archive* [Link](http://daac.ornl.gov/PI/bestprac.html)

White et al. 2013. Nine simple ways to make it easier to (re)use your data. *Ideas in Ecology and Evolution* 6, 1--10. [link](https://ojs.library.queensu.ca/index.php/IEE/article/view/4608)

Wickham, H. Tidy Data. *Journal of Statistical Software* [PDF](https://www.jstatsoft.org/index.php/jss/article/view/v059i10/v59i10.pdf) [Link](https://www.jstatsoft.org/article/view/v059i10)

UK Data Archive. 2013. Managing and Sharing Data: Best practice for researchers. [Link](https://data-archive.ac.uk/media/2894/managingsharing.pdf)


## Online Resources

Ecological Society of America [data sharing](https://www.esa.org/esa/science/data-sharing/resources-and-tools/)

UK [Data Archive](http://data-archive.ac.uk/)


