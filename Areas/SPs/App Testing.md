## How to do App Testing for an SP
---

1. Provision an EOD (Environment On Demand) for the current release name (i.e. 2018.06.22)
2. Open and RDP to the FatClient that is generated (note the s18xx ip)
3. Once in the RDP, open a terminal
4. Find the s18xx ip and type `testdns s18xx` (replace the x's with the letters found earlier)
5. Take note of the domain found
6. Open a PuTTy and input the domain found last step
7. Enter the credentials as so (username: root | password: cerner)
8. If a dialogue pops up click **yes**
9. A PuTTy terminal will appear and we can start the server (i.e. 2042)
10. Type `scp` (user: system | domain: s18xx | password: system)
11. Once in scp type `server -entry 2042`
	1. If nothing pops up type `start 2042`
	2. If something pops up type `cycle -entry 2042`
12. After starting the server and checking that it is running, change the directory to $cer_temp with 'cd $cer_temp'
13. Find the logs generated with `ls -lart | grep 2042`
14. 4 logs will appear. Check to see if the latest one is not failing with `cat cmb_2042_01.out`, if everything looks right continue to apptest
15. Type `apptest` use the creds: (user: system | domain: s18xx | password: system)
16. Then follow the **Credentials (in order)** section to continue.

Final note, if this is for system testing (highly likely), don't forget to grab evidence

---

#### What to :
Application and Task #: 3202004
Request #: 964764
PERSON_ID: 18023313 | To find use [[Finding a Patient to Use with DVD]] for this in the EOD
ENCOUNTER_ID: 12345 | Can use the same steps in [[Finding a Patient to Use with DVD]] to find a viable ENCNTR_ID as well if needed
CONCEPT: allergies

Say no to any y/n combinations, put 0, enter for anything not known or needed

You can also search the GitHub org for the Request #, find a .csi (crime scene investigation), and check what is going to appear when an apptest is run for that Request #.


