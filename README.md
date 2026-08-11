Goal: Create csv from this year’s Survey123 data which matches the previous conventions to allow smooth integration into R code. 

Overview: The 20XX-ALL data files must be created from the Survey-123 Excel by copying and pasting the relevant data into a single sheet. This makes the analysis of the data much simpler. Use the following conventions to ensure consistency among data between years




Prepare excel spreadsheet
Background: When downloading the data from Survey123 - each species point is listed in its own sheet(separated by native and non-native) without the transect ID. You need to put the transect ID on each data point for the Native, Non-native, and Other cover sheets. You can do this using the “parent global ID”. Each data point has a parent global ID(column G) which matches the “Global ID”(column B) of the transect sheet( “CCBER_VegMonitoring_Quadrat”).  Matching these you can add the transect to each data point. 

Step 1. Retrieve Data. 
In survey 123, filter site for North Parcel and current year's data. 
Download entire data set as excel spreadsheet

Step 2a. Clean Data from native, non-native, and species cover tabs. 
There are a number of unlisted species and species with 0 percent cover. Clean these out 

Remove empty rows from Native, Nonnative, and Other cover sheets
Add filter to top row
Filter out cover=0 
**Not necessary to delete each individual row**
Filter out species = “(blank)”
Fill in unlisted species 
Filter for only “unlisted species” 
Ensure species are correctly spelled and in the format Genus_species
**do not forget the underscore as opposed to space as it keeps data consistent**
Copy the unlisted species of to the Species column
Repeat until there are no “unlisted” species
Remove species filter. Keep 0 Filter on

Step 2b. Clean data from transect numbers
Vernal pool ID numbers are entered manually so ensure that they were correctly entered 
Create a pivot table of CCBER_Quadrat_monitroting sheet(1st sheet in download) 
Put VP name or number in rows 
Ensure there are no slight alterations of IDs(e.g. VP-8 vs 8) and all IDs are accounted for with no extras
Adjust the data in Survery123 for accuracy

Step 2c. Clean data from non-VP transect numbers
Upland/Wetland?Bioswale Transect IDs are recorded in a different column. Transfer them into VP Transect ID column 
Filter “NP Transect Name/Number” column for non-blank entries 
Filter each non-VP transect one at a time 
Copy entries from NP Transect to “Vernal Pool Name or Number”
Repeat for each Non-VP transect
     
Step 3. Add Transect information to native, non-native, and other cover sheets
In “native_plants_begin” sheet, add a new column to the end titled “transect” 
Create an equation which matches the parent global id of native plant sheet to the global id of summary sheet(1st sheet in spreadsheet) and retrieves the location ID 
=XLOOKUP(G2,CCBER_VegMonitoring_Quadrat_0!B:B,CCBER_VegMonitoring_Quadrat_0!F:F,"ERROR",0)
This equation may work but you may have to change some references depending on how data was downloaded. 
Apply to entire column 

Step 4: Add a Cover Type column to native, non-native, and other cover sheets
Add a column to end of native,non-native, and other sheets titled “cover type” 
 Enter “Native”, “Exotic” or “Other” for entire column for each sheet

Move Data to New CSV
Now we will create a new document which will match the other 20XX-ALL documents and contain only clean transferred data. 

Step 5. Open a new spreadsheet titled “20_ _-ALL” for current year
Step 6. Copy native data from original sheet to new empty sheet 
Only copy the columns for species, cover, transect, and cover_type(lower case matters) in that order. Rename columns as needed
Retitle the columns if necessary to species, cover, transect, and cover type
Step 7. Repeat above process for non-native and other cover, pasting beneath the native cover data.  
Step 8. Add remaining other cover (Bare ground/Thatch/Mowed thatch) 
Bare Ground and Thatch do not have their own sheet so you’ll have to take this from the CCBER_VegMonitoring_Quadrat Sheet. Each quadrat has it’s own value but we will simply enter in the total for the transect. It will need to be entered manually 

In 20XX-ALL sheet, Add 3 *rows* for each transect with “species” named (case matters)
Bare_ground
Thatch 
Mowed_thatch 
Enter other for cover_type 
Using previously made pivot table 
Set rows to “Vernal Pool Name or Number” 
Set values to Sum Bare Ground, Sum Thatch, Sum Mowed/Trimmed 
Should show each transect with Bare ground/Thatch,and Mowed Trimmed for whole transect 
Copy pivot table contents 
Paste (transposed) into 20_ _-ALL wherever convenient 
This is temporary step to making filling blank cells easier. 
Copy and paste cover values into appropriate cells for bare_ground/thatch/mowed_thatch that were recently created being sure to match the correct transect 
Remove transposed data from sheet 
Step 9. Save as .csv. Done! 


—------------------------- See below for some additional notes on date from previous years-----------------------------------

“All” Data Conventions 
. 

Note on other data files* = There are many other data files for previous years. I think I just downloaded each transect separately to transfer into the all. It is very time consuming. See below for creating “All” excel document. 

Relevant Data and Column names 
Column A - Species 
Data = the name of the species as it is presented when exported from Survey123(Genus_species) 
Column B - Cover 
The percent cover of that species for that data point 
Column C - Transect 
Name of the transect(see below) 
Column D - Cover Type 
Native, exotic, or other 
Column E - Year 
The year that data was taken 







