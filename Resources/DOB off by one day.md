clipboard summary off by one day previous day 

8/30 expected, 8/29 given

possible timezone issue

convert db dt to w/timezone

local timezone should not apply to birthdate as it should be absolute

./PatientBirthDateRetriever.java

in mill-interop-dao

getFormattedDateOfBirth

https://wiki.cerner.com/display/public/reference/Understand+Birth+Date+and+Time+Values


Notes from Turnover to Christian:

6/3/22

-   [https://jira2.cerner.com/browse/PIE-12607](https://jira2.cerner.com/browse/PIE-12607 "https://jira2.cerner.com/browse/pie-12607")
-   BIRTH_DT_TM BIRTH_TZ: 29-AUG-2020 23:00:00.00
-   BIRTH_DT_TM BIRTH_TZ: 126

  

When retrieving the DOB – include the time zone and translate the date to it’s corrected date…

But when displaying it shouldn’t apply the any additional time zone logic (local timezone)

  

  

  

 [https://github.cerner.com/Powerchart-Info-Exchange-Dev/mill-interop-adapter-ped/blob/c411b23a1cedaef6c17c99601c6a3f5b2887af94/src/main/java/com/cerner/interop/adapter/ped/internal/util/PatientRetriever.java#L180](https://github.cerner.com/Powerchart-Info-Exchange-Dev/mill-interop-adapter-ped/blob/c411b23a1cedaef6c17c99601c6a3f5b2887af94/src/main/java/com/cerner/interop/adapter/ped/internal/util/PatientRetriever.java#L180 "https://github.cerner.com/powerchart-info-exchange-dev/mill-interop-adapter-ped/blob/c411b23a1cedaef6c17c99601c6a3f5b2887af94/src/main/java/com/cerner/interop/adapter/ped/internal/util/patientretriever.java#l180")

  

[https://wiki.cerner.com/display/public/reference/Understand+Birth+Date+and+Time+Values](https://wiki.cerner.com/display/public/reference/Understand+Birth+Date+and+Time+Values "https://wiki.cerner.com/display/public/reference/understand+birth+date+and+time+values")