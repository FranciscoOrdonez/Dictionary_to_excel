# Dictionary_to_excel
From a dictionary make a defined report in excel with year and months as columns and the balance amount on 10th., 20th., and last day of the month as rows. If the balance on 7th of September was US 120563.45, the the balance on the 10th of September would be the same. It the balance for the required date i.e 10,20th and last day is not given, the previous balance would be the desired balance.
An input dictionary might look like this:

![206311759-f7aec9e7-307b-441f-aa8e-b5c2749808e8](https://user-images.githubusercontent.com/53232113/206321369-9cd8ea81-1938-4907-bc09-e3737816e538.png)

With this dictionary as input, the requirement is to have a report in excel with the following format:
![206751543-cb2e1104-d74e-4f56-8e07-051040d77f68](https://user-images.githubusercontent.com/53232113/206757804-30192f49-c2f3-4f48-a9cc-d93b3b8a5665.png)

The approach to get the excel report from a three dimension dictionary is to loop the dictionary to get the information from year, month and amount for date, and arrange so the csv file has the correct information, and finally read the csv file into a frame and use the command: 'df_to_excel(name_excel_file)' to pass the information to an excel file.  Finally open the excel file and get the results.

