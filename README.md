# PowerBi-Dashboard-HR-Analytics
This PowerBi dashboard gives employees insights to company's HR department.Measures important KPI like total working days, employees sick leaves, present days,
half days and work from home percentage. Datasets contains year 2022 data and is used to fulfill HR's requirements by leveraging Power Bi and Excel for data analysis.

Link to Dashboard
[https://app.powerbi.com/view?r=eyJrIjoiY2ZlNzZmYzUtYWExZC00YTUwLWE2MDktN2E4NzcxNzQxNWJiIiwidCI6ImE4ZDQ4NGQ1LTI5OGUtNDgyMy04NjQ5LWI1MDk0MzM0ODlmZiJ9](url)




Measures Used are written below:

1.
Total Worked Days = 
 var totaldays = count(FinalData[Value])
 var noworkingdays = CALCULATE(count('FinalData'[Value]), FinalData[Value] in {"WO","HO"})
 RETURN
 totaldays-noworkingdays

2.
WFH COUNT = SUM(FinalData[WFH])

3.
PRESENCE % = DIVIDE([Present Days],[Total Worked Days],0)

4.
Present Days = 
var presentdays=CALCULATE(COUNT(FinalData[Value]),FinalData[Value] ="P")
RETURN 
presentdays+[WFH COUNT]

5.
SL count = SUM(FinalData[SL])

6.
SL% = DIVIDE([SL COUNT],[Total Worked Days],0)

7.
WFH% = DIVIDE([WFH COUNT],[Present Days],0)

