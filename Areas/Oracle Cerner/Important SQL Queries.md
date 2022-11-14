# Important SQL Queries
### Get all tables that contain certain column name
`select table_name from all_tab_columns where column_name like '%<COLUMN_NAME>%'`

### Get patient information (need to know Patient ID)
`select * from person where person_id = <PERSON_ID>`

### Get appointment information
`select * from sch_appt where person_id = <PERSON_ID>`

### Get encounter information
`select * from encounter where person_id = <PERSON_ID>`

### Get Staged Clipboard Data
`select * from ext_data_info where encntr_id = <ENCNTR_ID> and data_source_name = '%<DATA_SOURCE_NAME>%'`

### Get appt_location_cd value
`select person_id, appt_location_cd from sch_appt where sch_appt_id = <SCH_APPT_ID>`

### Update appt_location_cd value
##### Charles Semoham
```
update into sch_appt  
set appt_location_cd = <20573082 || 0>
where sch_appt_id = 50702964.00 go
commit go
```
##### Madeleine McClain
```
update into sch_appt  
set appt_location_cd = <20573082 || 0>
where sch_appt_id = 50702650.00 go
commit go
```