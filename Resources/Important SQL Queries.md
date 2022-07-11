# Important SQL Queries
#### Get all tables that contain certain column name
`select table_name from all_tab_columns where column_name like '%<COLUMN_NAME>%'`

#### Get patient information (need to know Patient ID)
`select * from person where person_id = <PERSON_ID>`

#### Get appointment information
`select * from sch_appt where person_id = <PERSON_ID>`

#### Get encounter information
`select * from encounter where person_id = <PERSON_ID>`

#### Get Staged Clipboard Data
`select * from ext_data_info where encntr_id = <ENCNTR_ID> and data_source_name = '%<DATA_SOURCE_NAME>%'`