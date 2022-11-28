### Finding a Patient to Use
1. In order to continue, please be in an EOD
2. In the Start menu, type `discernvisualdeveloper` exactly and click open
3. Type in the username and password on the popup (user: system | pass: system)
4. Hit ctrl+c or 'File -> New'
5. Select 'Ad Hoc Query'
6. Add any name to 'File Name'
7. Click **OK**
8. Click **Close** on the popup
9. Put this line `SELECT * FROM encounter e WHERE e.active_ind = 1 ORDER BY e.updt_dt_tm desc WITH maxrec = 10` into the text box replacing the `SELECT WITH NOCOUNTER, SEPARATOR=" ", FORMAT`
10. Run the Ad Hoc Query ctrl+q or 'Build -> Run Ad Hoc Query...'
11. 10 Results should appear with 10 patients and all of their appropriate data