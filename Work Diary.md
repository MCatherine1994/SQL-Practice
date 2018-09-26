## **Work Diary**
#### **09/13/2018:**  
```
1. python, import data from database to collection using rmongo
2. javascript-d3.js, work on timeSeries chart on the new application
  i) to support two formats of data, with single key or multiple keys
  ii) to support global changes (changes apply to all the chart on the page) on axis:
    a) with "click" event, zoom on yaxis will apply to all the charts on the page
    b) with "alt" key and "click", work on only the current single chart
```
#### **09/14/2018:**  
```
1. javascript-d3.js, work on timeSeries chart on the new application
  i) update the xaxis ticks to show the start and end date with the responsive feature
  ii) add the group feature to the small-multiple timeseries charts, so the charts are displayed by group
```
#### **09/17/2018:**  
```
1. javascript-d3.js, work on timeSeries chart on the new application
  i) update the bar chart to have a fixed height and responsive width, so the width could still be responsive to the window size change
2. React.js
  i) add the tab for the component, to switch between bar chart and map chart
```
#### **09/18/2018:**  
```
1. React.js: add the table to explain the metric and dimension of some terms related to the new application
2. Jest Test: updated the test case for new application, test the functions in the component
```
#### **09/21/2018:**  
```
1. React.js: update the property to support both year and month format and only year format on the xticks
```
#### **09/24/2018:**  
```
1. React.js: 
  i) create a dynamic dateList, when the metric change, the dateList change correspondently
  ii) if the current selected date is in the new metric's dateList, then show the bar charts based on the current date; if not, then display the most recent date in the new metric's dateList
```
#### **09/25/2018:**  
```
1. React.js: 
  i) handle the case when input data is null, but want to show not reported on the chart instead of not showing the chart. So need to add an empty dataList for those.
  ii) update the dropdown box to contain the group for each metric
```
