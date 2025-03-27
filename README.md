Project Overview

This project connects:

A Google Form: for collecting venue information
A Google Sheet: which stores and organizes confirmed and non-confirmed jazz venues
The script:

Populates dropdowns with neighborhood + venue names
Removes duplicates
Sorts entries alphabetically (with "N/A" neighborhoods at the bottom)
Logs each submission in a dedicated response sheet

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Files and Functions

updateDropdowns()
Purpose:
Populates two dropdown fields in the form:

"Names of Jazz Venues (confirmed locations)"
"Names of Jazz Venues (not confirmed locations)"
Data Sources:

Confirmed Jazz Venues sheet
Non confirmed Jazz Venue sheet
How It Works:

Reads venue name (column B) and neighborhood (column J)
Removes duplicates
Formats each entry as:
Neighborhood - Venue Name
Sorts venues alphabetically (placing "N/A" neighborhoods last)
Updates the dropdown fields in the form
onFormSubmit(e)
Purpose:
Logs each form submission to a sheet called "Form Responses" in the same spreadsheet.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////

How It Works:

Extracts:
Timestamp
User selection (confirmed vs. non-confirmed)
Selected venue
All other form responses
Creates the "Form Responses" sheet if it doesn't exist
Appends each response as a new row

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Requirements

Google Form ID: 1reuAZF3XJ7csb_3ZfXPMnQ3myYg55zNp96rBSpGDsUk
Google Sheet ID: 16BdfnBN10f0_c7jAslP9Jgrd1S--rJd3n9liuVWGiEk
Must have two sheets named exactly:

Confirmed Jazz Venues
Non confirmed Jazz Venue


//////////////////////////////////////////////////////////////////////////////////////////////////////////////////

How to Use?

Open Google Apps Script
Paste this script into the editor
Make sure your Google Form and Google Sheet IDs match

Run updateDropdowns() manually or trigger on edit/time-based trigger (basically make it either activate daily or activate per user input
Set up onFormSubmit(e) as an installable trigger:
Edit → Current Project’s Triggers → Add Trigger
Choose function: onFormSubmit
Choose event type: On form submit

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////
Example Dropdown Output

Downtown - Wally's Cafe
Roxbury - Slade's Bar & Grill
N/A - Unknown Venue
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Notes

Dropdowns will always reflect the latest state of the Sheet.
If no neighborhood is provided, it defaults to "N/A".
Sorting ensures cleaner UX on the form side.
