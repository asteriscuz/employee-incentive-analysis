# Employee Absenteeism-Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/9ce46da0-b48f-4161-89fd-ff12571ab73b/1e069cd472b7b782d12b?experience=power-bi
## Problem Statement

HR has asked to help them calculate a wage increase or annual compensation for non-smoking employees with a budget of $983,221. It provides the company with a list of healthy employees with low absenteeism for a bonus program. They have asked for a dashboard to understand absenteeism at work based on an approved wireframe.  

### Steps followed 

- Step 1 : Load data into SQL Server, dataset is a csv file.
- Step 2 : Left join the three tables ‘Absenteeism’, ‘Reasons’, and ‘Compensation’.
- Step 3 : Select the relevant columns to understand the reasons for absenteeism
- Step 4 : The following optimized query was used to get the final output:
select a.ID, #(lf)r.Reason, #(lf)Month_of_absence,#(lf)a.Body_mass_index,#(lf)CASE WHEN Body_mass_index < 18.5 then 'Underweight'#(lf)WHEN Body_mass_index between 18.5 and 25 then 'Healthy'#(lf)WHEN Body_mass_index between 25 and 30 then 'Overweight'#(lf)WHEN Body_mass_index > 30 then 'Obese'#(lf)ELSE 'Unknown' END as BMI_Catgeory,#(lf)CASE WHEN Month_of_absence IN (12, 1, 2) Then 'Winter'#(lf)WHEN Month_of_absence IN (3,4,5) THEN 'Spring'#(lf)WHEN Month_of_absence IN (6, 7, 8) Then 'Summer'#(lf)WHEN Month_of_absence IN (9, 10, 11) Then 'Fall'#(lf)ELSE 'Unknown' END as Season_Names,#(lf)Month_of_absence,#(lf)Day_of_the_week,#(lf)Transportation_expense,#(lf)Education,#(lf)Son,#(lf)Social_drinker,#(lf)Social_smoker,#(lf)Pet,#(lf)Disciplinary_failure,#(lf)Age,#(lf)Work_load_Average_day,#(lf)Absenteeism_time_in_hours#(lf)from [Absenteeism_at_work-1] a#(lf)left join compensation c on a.ID = c.ID#(lf)left join Reasons r on a.Reason_for_absence = r.Number;"])
- Step 5 : Load data into Power BI Desktop, dataset is a csv file.
- Step 6 : Use the above query on Power BI to filter and get only the relevant columns.
- Step 7 : In the report view, under the view tab, theme was selected.
- Step 8 : Since the data contains various metrics, thus in order to represent these in relation to absenteeism, new visuals were added using the three pie charts in the visualizations pane in report view. 
- Step 9 : Visual filters (Slicers) were added for four seasons named Summer, Winter, Fall, Spring.
- Step 10 : Two line charts were added to the canvas, one representing absenteeism by months, and one representing absenteeism by days.
- Step 11 : A scatter plot was also added to the report, representing the work load in an average day and the average of transportation expense. 
- Step 12 : Card visuals were added to show the average hours of absenteeism among the employees. 
- Step 13 : Minor touches were made to the report to make it visually appealing and make the text readable. 
 - Step 14 : The report was then published to Power BI Service.

# Snapshot of Dashboard (Power BI Service)
![Image](https://github.com/user-attachments/assets/4c92d4eb-458f-4f9f-8345-57d52dee1aaa)
 
 # Report Snapshot (Power BI DESKTOP)

![Image](https://github.com/user-attachments/assets/39fb8dbb-068b-4fdf-9617-0dca90c5a7ee)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Average absenteeism in hours = 6.92 

   Total number of hours of absenteeism in the year = 4773

Extra bonus given to non-smokers=$ 983,221/(8*5*52*686) = increase of $0.68 per hour for employee

Total extra amount given to an employee in an year = 8*5*52*0.68 = $1,414. 

