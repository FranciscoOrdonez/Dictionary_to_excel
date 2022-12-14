# Dictionary_to_excel
From a dictionary make a defined report in excel with year and months as columns and the balance amount on 10th., 20th., and last day of the month as rows. If the balance on 7th of September was US 120563.45, the the balance on the 10th of September would be the same. It the balance for the required date i.e 10,20th and last day is not given, the previous balance would be the desired balance.
An input dictionary might look like this:

![206311759-f7aec9e7-307b-441f-aa8e-b5c2749808e8](https://user-images.githubusercontent.com/53232113/206321369-9cd8ea81-1938-4907-bc09-e3737816e538.png)

With this dictionary as input, the requirement is to have a report in excel with the following format:
![206751543-cb2e1104-d74e-4f56-8e07-051040d77f68](https://user-images.githubusercontent.com/53232113/206757804-30192f49-c2f3-4f48-a9cc-d93b3b8a5665.png)

The approach to get the excel report from a three dimension dictionary is to loop the dictionary to get the information from year, month and amount for date, and arrange so the csv file has the correct information, and finally read the csv file into a frame and use the command: 'df_to_excel(name_excel_file)' to pass the information to an excel file.  Finally open the excel file and get the results.
![207450064-7f97d76d-df0b-48aa-8339-75db1fef2426](https://user-images.githubusercontent.com/53232113/207450295-68df401d-ef93-48e9-9fa4-98556b2326f7.png)

1. Create dictionary and initiate lists.  The initial dictionary is created as an input to the project. This dictionary has three levels, one is the year level, the second in the month level and the third is the day level where the value is located.  An example could be dict = {'year': {'month': {'day':value}}}. For that there is a need to create a dictionary equivalent from month number to name of the month as "dict_month = {'01':'JAN','02':'FEB'......}'.  Also there is a need to create five lists which are and empty year's list named "list_year',and emmpty  month's list "list_month", and three day's list with a initial description description  for the 10th day of the month ('list_10'), for the 20th, day of the month('list_20') and the last day of the month('list_30').  The idea of these lists is to append every year, every month and every day that appears in the initial dictionary as to create an input for each line of the csv file.
2. Open csv file to write.  Once we have the empty lists ready, the scv file in write mode has to open and create a scv writer object.
3. Loop dictionary for year. First is necesary to create a loop in the dictionary with the year value and the rest which in this case is the months, days and values for each year.
4. Loop dictionary for month.  This second loop gets the month value and the rest which is the days and values for each month. At this point, for each month, the year's list is appended with the year value and the month's list is appended with the month's name. Here initializes the three lines for the 10th., 20th. and last day lists.
5. Loop dictionary for days and values.  This third loop gets the days values and check which is the last day for 10th, 20th and final days of the month. 
6. Find values of 10th,20th and final days. Review which values have to go in lines 10th, 20th. and final.  If the balance on 7th of September was US 120563.45, the the balance on the 10th of September would be the same. It the balance for the required date i.e 10,20th and last day is not given, the previous balance would be the desired balance.
7. Append values for 10th, 20th, and final days.  The the lists are appended for every month in the dictionary.  
8. Write in csv file year, month and values for days.  The values appended in year, month and 10th, 20th, and final days are written in the csv file.
9. Read csv file into dataframe df.   Once the information of the dictionary is collected in five rows of the csv file(year, month, 10th day, 20th. day and final day), the file is read and converted into a dataframe df.  At this point the information of the dictionary is now in a pandas dataframe.
10. Create header for year and month.  Now, there is a way to create a header with the first two lines of the dataframe,so the first line is the year, and the second line is the month.
11.  Create index for first column. The first column is the description of lists: 'BALANCE AS ON 10TH', 'BALANCE AS ON 20TH'  and 'BALANCE AS ON LAST DAY'.
12.  Send dataframe to excel.  With the header and index created and the information of the dataframe, the data is moved from the dataframe to a created excel file.
13.  Open excel file and check results.  Here we go to excel, open the created file, and get the results. There are five lines on the file, two are the headers with year and month, and the last three are the results per month of balances as on 10th. day, balances as on 20th. day, and balance as on last day of the month, as shown above.

The code information of this project is shown [here](code).
