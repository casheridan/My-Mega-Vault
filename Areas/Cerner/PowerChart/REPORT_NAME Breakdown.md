## REPORT_NAME Breakdown
> [!INFO] For our __Document Workflow Component__ we will have this line as our *REPORT_NAME*: 
> `<URL>$DM_INFO:CONTENT_SERVICE_URL$/mp-content/idx.html?m=^CHT^&pId=$PAT_PERSONID$&eId=$VIS_ENCNTRID$&uId=$USR_PERSONID$&pCd=$USR_PositionCd$&ppr=$PAT_PPRCode$&app=^$APP_AppName$^&vId=^ADVINTEROP^`

#### What is this Report Name here
Breaking down this parameter we are putting an HTML URL tag into the TOC so it can pick it up in PowerChart and display the MPages ViewPoint with the data associated with the current patient.

#### Content Path
The `$DM_INFO:CONTENT_SERVICE_URL$` is the domain url and mpages-content path
* 64dev example
	* `http://ip85lodr27a.ip.devcerner.net:8080/mpage-content/64dev.ip.devcerner.net`
* You can get this by doing a query in the related domain's database
	* `select * from dm_info d where d.info_domain = "INS" and d.info_name = "CONTENT_SERVICE_URL"`

It is followed by `/mp-content/idx.html` to get the main page for mpage content. Everything after the `?` is information entered to get the right mpage component from the mpage content.

>`m=^CHT^` is related/abbreviated from *Chart* which we can see in __Prefmaint__ (check if right)

#### Patient and User Data
`&pId=$PAT_PERSONID$&eId=$VIS_ENCNTRID$&uId=$USR_PERSONID$&pCd=$USR_PositionCd$&ppr=$PAT_PPRCode$` has all the information relating to the patient let's break it down.
* Each `&` seperates a each patient data value in the URL
* Words surrounded between two `$` are variables gotten from the domain's database
* `pId=$PAT_PERSONID$` is the id associated with the patient
	* i.e. Charles Semoham is 18023313
* `eId=$VIS_ENCNTRID$` is the encounter id associated with the patient
	* i.e. 14840804 for Charles Semoham BW Clinic encounter
* `uId=$USR_PERSONID$` this is the id of the millenium user accessing the patient
	* i.e. 3077940 for junituser_admin
	* (check if right)
* `pCd=$USR_PositionCd$` this is the prefmaint position of the millenium user
	* 441 or DBA
	* (check if fully right)
* `ppr=$PAT_PPRCode$` this gets the patient's code set
	* i.e. 1115 for Charles Semoham from core code builder
	* (check if fully correct)

#### Application and MPages ViewPoint name
The last part of the URL is `&app=^$APP_AppName$^&vId=^ADVINTEROP^`

* Due to CCL we have to use `^` in order to denote a string in replacement of single quotes for some dumb reason.
* `app=^$APP_AppName$^` is the name of the powerchart application
	* i.e. powerchart.exe
* `vId=^ADVINTEROP^` is related to the ViewPoint name in Bedrock


Request URL from F12: http://ip85lodr27a.ip.devcerner.net:8080/mpage-content/64dev.ip.devcerner.net/mp-content/idx.html?m=^CHT^&pId=18023313.00&eId=14840804.00&uId=3077940.00&pCd=441.00&ppr=1115.00&app=^powerchart.exe^&vId=^ADVINTEROP^
   
Data used:

Charles Semoham
PowerChart
junituser_admin
DBA
Code Level 1115
ADVINTEROP

