# HR Analytics Dashboard


## Problem Statement

This dashboard helps the HR team and management team to understand the office availability of the employees. It helps the management team to 
developed and implemented HR analytic strategies to enhance decision-making processes.Helps to  give insights regarding the daily  employees which are on leave , or working from home or are  working from office  .Caculated charts which will show which months having more employees on leave  which will help us to accurately plan release dates of project when is the better time to take a project and prepare a plan of execution for the project 




### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a xlsx file.

- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.

- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".

- Step 4 : It was observed that in none of the columns have errors & empty values except the total total presents and other few junk columns which are not important for our analysis.

- Step 5 : To analyze the office attendance more efficiently we have unpivoted the data based on employeename and employee id and also removed the 	junk columns 
- Step 6 : Here we have multiple sheets of atttendence for each month and have applied transformation on one sheet  
- Step 7 : Created a function on top of all the transformation applied  on one sheet and applied  on all the sheets , which will give a single sheet having data of all sheets 


        
- Step 8 : New measure was created for number total days.

Following DAX expression was written for the same,
        
        NO_OF_NON_WORKING_DAY = CALCULATE(DISTINCTCOUNT('Attendance Sheet 2022-2023_Masked xlsx'[date]),'Attendance Sheet 2022-2023_Masked xlsx'[attendance] IN {"WO"},'Attendance Sheet 2022-2023_Masked xlsx'[date])
        
A card visual was used to represent number total days.

![Snap_Count](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/601a94dd-debb-4691-9127-26e02861f4b1)

        
 - Step 9 : New measure was created to get total employees,
 
 Following DAX expression was written for the same,
 
        total_employees = CALCULATE(DISTINCTCOUNT('Attendance Sheet 2022-2023_Masked xlsx'[Emp Name]),'Attendance Sheet 2022-2023_Masked xlsx'[attendance]<>{"WO"} || 'Attendance Sheet 2022-2023_Masked xlsx'[attendance]<>{"HO"} )
 
 A card visual was used to represent this perecntage.
 
 ![Screenshot 2024-05-26 152824](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/2c12633a-5995-413b-b568-a36eb14ab590)


 
 - Step 10 : New measure was created to calculate number of working day .
 
 Following DAX expression was written for the same,
 
         NUMBER_OF_WORKING_DAYS = CALCULATE(DISTINCTCOUNT('Attendance Sheet 2022-2023_Masked xlsx'[date]),'Attendance Sheet 2022-2023_Masked xlsx'[attendance] <>{ "WO"},'Attendance Sheet 2022-2023_Masked xlsx'[date])
    
 
 ![image](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/1623d5c2-14de-4907-8fd3-1ec5309f4cd3)

 
 - Step 11 : New measure was created to calculate number of non working day .
 
 Following DAX expression was written for the same,
 
         NO_OF_NON_WORKING_DAY = CALCULATE(DISTINCTCOUNT('Attendance Sheet 2022-2023_Masked xlsx'[date]),'Attendance Sheet 2022-2023_Masked xlsx'[attendance] IN {"WO"},'Attendance Sheet 2022-2023_Masked xlsx'[date])
 
  
![Screenshot 2024-05-26 152440](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/4f77c25d-5019-449c-b1b9-bfcdf3cf07f6)

# Insights

A  report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] 

   Number of employees  = 99
   Number  of working day = 65
   Number of non working day = 25

           
### [2] perecntage of leave by day

     Day having maximum no of leave is Friday - 88.50(23.33%)
	 Day having least no f leave is Tuesday -- 66(17.43%)
  
	These ratings will change if different visual filters will be applied.  


  
### [3] trend of employee present by date

 ![image](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/49beaea7-2b3e-4dad-8126-cfc8fe515ace) 

### [4] Trend of workfrom home bydate
![image](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/c29e9945-7b91-4e2f-9043-5d8fc957f417)


### [5] Stacked Column Chart for employee availlability details vs dates
![image](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/dc9ac40f-12cd-4aef-b872-127f21f569b4)

### [6] each person attendance details 

 ![image](https://github.com/9475Abhinaba/HR-Analytics/assets/169307645/75e1613a-f201-44ff-ac9d-c0155b470ab8)

 
