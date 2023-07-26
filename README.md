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
- **closeMoveInactiveBoards** - If this is set to true then boards that have not been active in the last X days will be closed/archived. If all the boards in a Workpace are closed then those boards will be moved to the Archive workspace.
- **deleteEmptyWorkspaces** - This is a boolean that if set to true will look through Workspaces and if they only have closed boards, move all those boards to the archive workspace and then delete that empty workspace.
- **daysSinceLastActive** - This variable defines how you want to define activity and will impact which users will get deactivated from the Enterprise. If a user has not been active in the last X days (aka X days or more) then they will be deactivated. This will remove them from all Enterprise Workspaces and take away their Enterprise seat.
- **archiveWorkspace** - This is the id of the workspace you would like to move closed/archived boards too. Only boards that that are in a workspace with no open/active boards will be moved. 
- **testRun** - This is a boolean that if set to true will run the script in test mode. In test mode, no boards will be closed and no workspaces will be deleted.





---
### Outputs
When this script is run, it will output two different report files:
- **Workspace report** - This is the CSV file that captures all Enterprise Workspaces and whether or not they were deleted. 
- **Boards report** - This is the CSV file that is generated after to keep track of all Enterprise boards, when the last time they were active, and whether they were moved to the Archive Workspace. 

## Have Questions?
Post on the Atlassian Community [here](https://community.atlassian.com/t5/Trello/ct-p/trello) and tag @Alexandros Mathopoulos.
