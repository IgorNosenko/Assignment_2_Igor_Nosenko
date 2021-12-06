# Assignment_2_Igor_Nosenko
## DiceRobot-REF
### Robot calculate how many RPA jobs are on dice.com portal in the top 10 cities of US by population.
### Robot realized as Dispatcher-Performer model, based on the REFramework. Dispatcher robot realized separately as Dispatcher Workflow.
### Dispatcher workflow reads top-10 US cities by population from "https://www.moving.com/tips/the-top-10-largest-us-cities-by-population/" 
### and sends list of cities Orchestrator as Queue.
### Main workflows:
### DiceCom_Open - This workflow opens dice.com page and sets all constant filters.
### TravelMath_Open - This workflow opens travelmath.com and goes to "Driving calculator" page.
### CreateExcelFile - Creating empty transite Excel file with 2 columns - "City" and "Number of jobs" - for saving results of searching.
### GetTransactionData - Get a transaction item from a Orchestrator queues. 
### DiceCom_AddTransaction - This workflow sets additional item filters and getting search results from dice.com.
### TextValidation - Validation of searching results by job filter text
### DistanceValidation - Validation of searching results by distance filter. This workflow starts if text validation finished successfully.
### AddCityResults_toFile - This workflow creates a new row with 2 variables - city name and number of jobs and saves results to the transite Excel file. 
### ExcelFileManipulation - This workflow working with Excel file in which gethered results of job searching. It sorts file by "Number of jobs" column by descending,
### highlights top-3 rows and borders all data. Also we add current time to file name and save results to the new Excel file.
### SendingEmail - Sending e-mail with searching results to the list of mails saved in Config file.

#### Requirements: Microsoft Windows 10 64-bit, UIPath  Studio 2021.10.3 - 10/26/2021 Community License, UIPath.Excel.Activities=2.11.4, UIPath.Mail.Activities=1.12.3, UIPath.Testing.Activities=1.4.3, Chrome browser, Microsoft Excel, Microsoft Outlook.
