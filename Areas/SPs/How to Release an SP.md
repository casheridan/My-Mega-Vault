### How to Release an SP
1. Open up a Windows Box
2. Open Feature Tracker
3. Find the feature (Hot List it as well to easily access it)
4. Check if it is in the merged status
5. If not, promote it by right clicking and selecting "Promote"
6. When it is merged Double Click to open the more option window
7. Grab the feature number from the Xref feature box on the first page.
8. Go to the next stage in the pipeline (2018.08_SVC_DEV -> 2018.08_SVC_STAGING -> 2018.08_SVC_SANDBOX)
9. When it is promoted to SANDBOX and is in the "Ready for Package" status provision an EOD that has the same name the release timing for the Feature which can be found in the double click window at the bottom.
10. When it is provisioned (5-45 mins.) do [[App Testing]] and use the concepts for that server (2042 in our case now)