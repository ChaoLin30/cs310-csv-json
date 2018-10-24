# csv-json

This project is meant to give me experience with two of the standard plain-text data formats that are commonly used for data interchange: CSV, and JSON. In this project, I will create converters to translate a specific kind of data (course grade data) to and from the CSV and JSON formats. This project will also give me experience with using the Git client and the JUnit testing framework within an IDE.

## Tech/framework used

Netbeans IDE

## Installation

OpenCSV and json-simple

In our subsequent assignments, we will be using OpenCSV (http://opencsv.sourceforge.net/) and its API (http://opencsv.sourceforge.net/apidocs/) to process CSV data, and json-simple (https://code.google.com/archive/p/json-simple/) to process JSON data.  The necessary library files (in the form of JAR files) can be found in the attached archive.

Before we can use these libraries, it will be necessary to install them into the JDK.  If we wish to use them in an IDE (such as NetBeans), it will also be necessary to create library entries for them in the IDE.  To install the libraries into your JDK, open the Windows Explorer, browse to the "C:\Program Files\Java" folder, then open the subfolder containing the most recent version of the JDK installed on your workstation.  All three of the JAR files from the attached archive should be copied into the "<java_home>\jre\lib\ext" subfolder of your JDK.

Once you have installed the JARs, open NetBeans and create two new libraries, one for OpenCSV and another for json-simple.  Choose "Libraries" from the "Tools" menu, click the "New Library" button, enter "OpenCSV" as the name, then click "Add JAR/Folder" and select two of the JAR files that you installed into the JDK in the previous step, "opencsv-4.0.jar" and "commons-lang3-3.6.jar" (both are required).  Click "OK" to create the library.  Then, repeat the process for json-simple: add the "json-simple-1.1.1.jar" file to the library, and use "json-simple" as the library name.

1. Fork and clone the following GitHub repository: https://github.com/jsnellen/cs310-csv-json

2.Download and install the OpenCSV and json-simple libraries.  These libraries are provided as a single collection on Blackboard; see the "Course Content" area for the library archive and for complete installation instructions.  The installation is a two-part process: the first part is to copy the library files into your JDK, and the second part is to add them as libraries in NetBeans.

3.Finally, check the NetBeans project that you cloned from GitHub to ensure that the necessary libraries are included in its classpath.  In the NetBeans project tree, right-click the project name ("cs310-csv-json"), select "Properties", and in the "Project Properties" tree, choose "Libraries" from the list of categories.  Ensure that there are four compile-time libraries added to the project: OpenCSV, json-simple, JUnit 4.x, and Hamcrest 1.x (Hamcrest is a framework for writing "matcher" rules; it is required by JUnit).  If any libraries are missing, click "Add Library" and add them from the list of libraries.  Click "OK" to commit your changes.

## Tests

To run the unit tests, right-click ConverterTest.java and choose "Run File" from the context menu.  A new output window should appear which displays the results of all four unit tests.  If your converter methods are functioning correctly, the resulting strings should exactly match the original data from the input files.

###### CSV

CSV stands for "Comma-Separated Values", and it is used to represent tabular data. The particular CSV file that we will work with is similar to the following:

 "ID","Total","Assignment 1","Assignment 2","Exam 1"
 
    "111278","611","146","128","337"
    
    "111352","867","227","228","412"
    
    "111373","461","96","90","275"
    
    "111305","835","220","217","398"
    
    "111399","898","226","229","443"
    
    "111160","454","77","125","252"
    
    "111276","579","130","111","338"
    
    "111241","973","236","237","500"
    
This file represents the grades of eight students (with the given IDs) in a course where there were two assignments and an exam.  Notice that the grades listed are represented as strings in the CSV file.  Even though this particular input data contains eight rows (plus the header row), your code should be written to support an open-ended number of rows.
    
###### JSON
    
    JSON stands for "JavaScript Object Notation", and it is used as a general-purpose format for many kinds of data, particularly in Web-based applications. The particular JSON file that we will work with is similar to the following
    
     "colHeaders":["ID","Total","Assignment 1","Assignment 2","Exam 1"],
     
        "rowHeaders":["111278","111352","111373","111305","111399","111160","111276","111241"],
        
        "data":[[611,146,128,337],
        
                [867,227,228,412],
                
                [461,96,90,275],
                
                [835,220,217,398],
                
                [898,226,229,443],
                
                [454,77,125,252],
                
                [579,130,111,338],
                
                [973,236,237,500]
                
   This file represents the exact same data as the CSV file above; it is just organized differently.  The "rowHeaders" and "colHeaders" values are lists of strings, and the "data" value is a list of integer lists. 
   
## Credit

    Jay Snellen
    https://github.com/jsnellen/cs310-csv-json
