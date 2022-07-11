## Adding a Tab to Prefmaint
> [!INFO]
We will be using the __Document Workflow Component__ as the example for this, not all components are the same as they may be called differently with *REPORT_NAME* and *REPORT_PARAM*.
>In order for our component to show up it must be properly set up in __Bedrock__ see [[Configuring our MPage Component]] for information on how to do this

---

### Prefmaint

#### Adding a Tab
1. Open Prefmaint in desired domain and open the chart TOC. *See [[Modifying PowerChart Table of Contents#Finding the Table of Contents in Prefmaint]] to find out how to get to the right place.*
2. Select __Chart__ in the tree on the left of the "Preference Form" in the "Level" box.
3. Click the __Add Tab__ button under the "Level" box. This will open "Define View(s) for Chart".
4. Find and select __Discern Report__ in the "Available Tabs." box.
5. Click the Down button or the Right Button below the "Help Text" box. This will put our new Tab at the bottom of the "Existing Tabs." box. 
6. To reorder our tab closer to the top, click the __Down__ button that is right of the "Existing Tabs." box. Click it about n times to put it down to the nth item in the chart tree.
7. Click the __OK__ button.

#### Add our Component
9. Select the nth item in the __Chart__ tree in the "Level" box.
10. Change the "VIEW_CAPTION" parameter value to the name of your Orion Component.
11. Click the plus (+) button left of the selected item in the "Level" box.
12. Select the new item below our selected item.
> To add the component to our tab we will change the **REPORT_NAME** and **REPORT_PARAM** but for the DWC (see above) we will use the \<URL\> html tag to show our component.
13. Add the tag from [[REPORT_NAME Breakdown]] to **REPORT_NAME**.
14. Click the __OK__ button or the __Apply__ button below the "Existing Preferences" box to save our changes.

### View the Changes in PowerChart
15. Open **PowerChart.exe** and find our patient (i.e. Charles Semoham).
16. In the TOC find the newly created tab with the value we put in the "VIEW_CAPTION" preference in prefmaint