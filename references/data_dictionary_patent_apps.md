# Data dictionary: Patent applications

## Source

PATSTAT August 2018 Edition

## Provenance

The raw data has been obtained from the European Patent Office's PATSTAT database

## Last update

Raw data last collected on: 

## Enrichment

None

## Known issues

TBA

|name|type|observations|
|----|----|----|
|Unnamed: 0|<class 'numpy.int64'>|   |
|appln_abstract|<class 'float'>| Abstract of the application  |
|appln_abstract_lg|<class 'float'>| Language of the abstract |
|appln_auth|<class 'float'>|  Application authority for the patent (eg USPTO, EPO, IPO) |
|appln_filing_date|<class 'float'>|  Application date for the patent |
|appln_filing_year|<class 'numpy.float64'>|  Application year for the patent |
|appln_id|<class 'numpy.float64'>| Unique identifier  |
|appln_kind|<class 'float'>| Kind of application - 'A' means patent  |
|appln_nr|<class 'float'>|  Application number from the authority were the patent was filed |
|appln_nr_epodoc|<class 'float'>|  Application number in epodoc format |
|appln_nr_original|<class 'float'>| Application number in original format  |
|applt_seq_nr|<class 'numpy.float64'>|  0 = not applicant, 1 to n = applicant|
|doc_std_name|<class 'str'>|  Standardised name of applicant |
|doc_std_name_id|<class 'numpy.float64'>|  Standardised id for the name |
|docdb_family_id|<class 'numpy.float64'>|  id for the simple family ('invention') |
|docdb_family_size|<class 'numpy.float64'>|  number of docs in the simple family  |
|earliest_filing_date|<class 'float'>|  Earliest filing (includes priorities) |
|earliest_filing_id|<class 'numpy.float64'>|  Id for the earliest filing |
|earliest_filing_year|<class 'numpy.float64'>|  Earliest filing year |
|earliest_pat_publn_id|<class 'numpy.float64'>| Id for earliest publication  |
|earliest_publn_date|<class 'float'>| Earliest publication date (not the same as application)!  |
|earliest_publn_year|<class 'numpy.float64'>|  Earliest publication year |
|granted|<class 'float'>| If the application has been granted  |
|han_harmonized|<class 'numpy.float64'>|  level of harmonization eg with the ORBIS database |
|han_id|<class 'numpy.float64'>|  id after harmonization |
|han_name|<class 'str'>| Harmonized name  |
|inpadoc_family_id|<class 'numpy.float64'>| more complex type of family (captures 'priority networks')  |
|int_phase|<class 'float'>|  Is the application in the international phase? |
|internat_appln_id|<class 'numpy.float64'>| PCT international application  |
|invt_seq_nr|<class 'numpy.float64'>| 1 to n = inventor, 0 = non inventor|
|ipc|<class 'float'>| IPC subclass  |
|ipc_maingroup_symbol|<class 'float'>| IPC subclass or main group  |
|ipr_type|<class 'float'>|  Type of IPR - could be a patent of invention or utility model |
|nace2_code|<class 'float'>|  Industrial classification of the patent |
|nace2_descr|<class 'float'>|  Industrial classification (description) |
|nace2_weight|<class 'numpy.float64'>|  Weight of the map between patent and sector (it's a dummy) |
|nat_phase|<class 'float'>|  If the pplication is in the national phase of the patent cooperation treaty |
|nb_applicants|<class 'numpy.float64'>| Number of applicants  |
|nb_citing_docdb_fam|<class 'numpy.float64'>|  Number of patents citing at least one in this family |
|nb_inventors|<class 'numpy.float64'>|  Number of inventors |
|not_with_ipc|<class 'float'>| Patent code co-occurrence  |
|nuts|<class 'str'>| NUTS region  |
|nuts_label|<class 'float'>|  NUTS label |
|nuts_level|<class 'numpy.float64'>|  NUTS level |
|person_address|<class 'str'>| person address  |
|person_ctry_code|<class 'str'>|  person country (should be GB) |
|person_id|<class 'numpy.float64'>| Name of applicant or inventor (?)  |
|person_name|<class 'str'>| person name  |
|person_name_orig_lg|<class 'str'>|  ? or is this ID? |
|psn_id|<class 'numpy.float64'>| Person id  |
|psn_level|<class 'numpy.float64'>|  Flag for name harmonisation |
|psn_name|<class 'str'>|  Same as psn name |
|psn_sector|<class 'str'>|  Type of organisation (individual, company etc) |
|receiving_office|<class 'float'>|  Office where an international application was filed |
|reg_phase|<class 'float'>|  Is the patent in the regional phase? |
|techn_field|<class 'float'>|  Technology field |
|techn_field_nr|<class 'numpy.float64'>| Technology field number / id  |
|techn_sector|<class 'float'>|  Technology sector |
|unless_with_ipc|<class 'float'>|   |
|weight|<class 'numpy.float64'>|  Weight of an association between application and industry |