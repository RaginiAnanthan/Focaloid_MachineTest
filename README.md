# Focaloid_MachineTest
machine test

On running the application the user lands to a home page :

HomeComponent :
- 2 input fields
- one for adding values to the array(only accepts numeric inputs) using the add button provided below the input text field. 
- also contains a reset button to clear the array values
- next input is for adding a value (any character/string can be added)

- on clicking the save button the sum of array input and the value input will be saved in local storage
- if the array sum and the value provided are same, will be redirected to the admin page
- else will be redirected to the chart view page

AdminPanelComponent : (Protected) 
- blank page with a welcome message 
- activeted only if the local storage sum and value are same

ChartViewComponent : echart with with user name on Xaxis, and year of birth on Y axis. Tooltip option is provided so that on hovering over the coordinates, data can been seen. Also, a markerLine is drawn with minimum, maximum nd average years

The landing page also contains a Log out option
Also a 'User Home' button is provided to view the user details

UserHomeComponent :
- contains two comoponents : UserSelectionComponent and UserListingComponent

UserSelectionComponent :
- lists all the users data from the json file users.json file in the assets folder with a selection option
- a Mat-table is used to show the data
- a custom pipe, AgeCalculation pipe is used to convert the DOB to age which shows erraneous DOBs as 'NA' 
- on clicking the apply filter button after choosing the age group from the dropdown, list gets filtered based on the selection
- on clicking send data, the selected data gets stored in the BehaviorSubject which can be retrieved any time 

UserListingComponent :
- lists all the data that was previously selected from UserSelectionComponent and stored in BehaviorSubject

Log out button :
- on clicking the log out button, the values from the local storage will be removed and redirected to the home page

ngx-spinner is used to show the loading animation if any http requests are triggered


