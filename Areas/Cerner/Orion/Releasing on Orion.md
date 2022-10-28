## Releasing on Orion w/ Jenkins
---

1. Find what version you are releasing
2. Sign TxP (Transfer to production) form
3. Go to Jira2
4. Find release review (might be named "\[record_locations_server] Release Review 1.5.0")
5. Move release review to "Issue Done" status
6. Move any other associated jira stories to "Issue Done" as well under that tag
7. Go to Jenkins (make sure to have it in master)
8. Go to master branch
9. Schedule a build
10. Click "Build"
11. Build will begin, wait for it to finish
12. Input requested will be in the console, click it.
13. Make sure all boxes are checked
14. Click "Proceed"
15. Contact Devendra about it to enter his creds into Jenkins.
16. Artifact should be released now

### Rigmarole - More manual, less perfered
---

release cmds:
- rigm release prepare -r #.#.# | auto bump project to next version, creates tag (needs unprotected master branch)
- rigm release artifact -r #.#.# | releases the artifact (if fails it's because it runs wrong break command, update this command from rake db:migrate deploy -> rake deploy)