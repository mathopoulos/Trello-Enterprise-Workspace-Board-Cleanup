# Trello-Enterprise-Workspace-Board-Cleanup
This is an open source script to help you clean-up Enterprise Workspaces & Boards that have not be used in the last x days. It looks through all of your Enterprise Workspaces, pulls each board, checks if it has been active in the last X days, and if it has not been then move that board to the "Archive Workspace." Once checking all boards in the Enterprise, it looks through all Enterprise Workspaces and deletes any Workspace that has 0 boards. For more details on how exactly to use this script, see details below. 

---
### User Paramaters 
There are 3 variables that the user must input for the script to work:
- **API Token** - This is the API token used to authenticate that the script has permission to run the needed operations against the chosen Enterprise. The API token must be tied to a user of the Enterprise with Enterprise Admin Permissions. Make sure that your API token includes write permissions. See the [Trello API documentation](https://developer.atlassian.com/cloud/trello/guides/rest-api/api-introduction/)
 for more details. 
- **API Key** - This is the API Key used to authenticate that the script has permission to run the needed operations against the chosen Enterprise. The API token must be tied to a user of the Enterprise with Enterprise Admin Permissions. See the [Trello API documentation](https://developer.atlassian.com/cloud/trello/guides/rest-api/api-introduction/)
- **Enterprise ID** - This is the ID of the Enterprise that the user would like to run the script against. See the [Trello API documentation](https://developer.atlassian.com/cloud/trello/guides/rest-api/api-introduction/)
 
In addition there below are a few customizations you can make if you would like. 
- **daysSinceLastActive** - This variable defines how you want to define activity and will impact which users will get deactivated from the Enterprise. If a user has not been active in the last X days (aka X days or more) then they will be deactivated. This will remove them from all Enterprise Workspaces and take away their Enterprise seat. 


---
### Outputs
When this script is run, it will output two different report files:
- **Workspace report** - This is the CSV file that captures all Enterprise Workspaces and whether or not they were deleted. 
- **Boards report** - This is the CSV file that is generated after to keep track of all Enterprise boards, when the last time they were active, and whether they were moved to the Archive Workspace. 

## Have Questions?
Post on the Atlassian Community [here](https://community.atlassian.com/t5/Trello/ct-p/trello) and tag @Alexandros Mathopoulos.
