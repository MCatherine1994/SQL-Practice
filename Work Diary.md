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
#### **09/26/2018:**  
```
1. React.js: 
  i) handle the case when input data is null, but want to show the missing cases on bar chart. On the time series, delet the null data among not null data, so the time series chart won't have a drop.
  ii) update the function that reformat the input data to return {timeSeries: timedata, barChart: bardata, xdomain: xdom, ydomain: ydom}
```
#### **09/27/2018:**  
```
1. d3.js: 
  i) update the ticks on yaxis to allow both integer and decimals.
2. Research:
  i) page tutorial 
  ii) any npm slider package
```
#### **10/01/2018:**  
```
1. React:
  i) installed and tried two React slider package rc-slider and react-rangeslider
  ii) update the slider and tooltip to support the case with month and year (discrete value) 
```
#### **10/03/2018:**  
```
1. React:
  i) installed and tried to use intro.js to create the web tour
```
#### **10/05/2018:**  
```
1. React.js & d3.js:
  i) Update the axis for the horizon chart to responsive to the window.pitch event, like adding the current date while mouse move and remove it when mouse out, also set the opacity corresponding
```
#### **10/08/2018:**  
```
1. React.js:
  i) Work with the package rc-slider and have the slider running as expected, added a player button, and added the feature that when click the player button, it will automatically go thourgh each avaliable value on the slider (a good demo feature)
2. Jest:
  i) Updated the test cases for slider component
```
#### **10/09/2018:**  
```
1. React.js:
  i)add the full mon and year to the start and end date on the slider
2. Jest:
  i) Updated the test cases for slider component
```
#### **A brief summary:**  
```
last updated date (react component)
more features on time series chart (zoom in and out chart by clicking on axis ticks, mouse move on chart to see highlight x, y values on axis)
unit test with jest and enzyme
rss subscribe
donut chart
bar chart (stacked bar chart, filtered bar chart)
demo pages
small multiples chart
filter component using React Select
new application interjurisdictional page (mongo collection, python code)
slider (with rc-slider package)
web tour (with reacttour package)
new application bc map generator (with different layers, reverse and change color, drop file, guided tour, filter selector with dynamic option list read from the drop file)
integration test
aplly slider to existing application page for bubble chart (call meteor method to run in database)
function test with puppeteer
```
#### **10/31/2018:**  
```
1. React.js:
  i) Finshed writing of slider and web tutorialr, tested webtour on a small application and on a main application, fixed the old bugs for uikit off-canvas
2. Jest:
  i) Work on the integration test of the web tutorial and slider
```
#### **11/02/2018:**  
```
1. React.js:
  i) Added the slider on one of the main application to actually work with the data and map
```
#### **11/05/2018:**  
```
1. React.js:
  i) Work on the new project, the map for the bc province using GitLab
  ii) Update boundary files to be in Geojson format
```
