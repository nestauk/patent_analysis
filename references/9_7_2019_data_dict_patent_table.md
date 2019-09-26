# Data dictionary: Patent table

## Source

PATSTAT August 2018 Edition

## Provenance

The raw data has been obtained from the European Patent Office's PATSTAT database.
See [here](https://github.com/nestauk/patent_analysis/blob/eda/references/9_7_2019_patent_outputs_inventory.md) for an inventory of the sources we have merged to create this dataset, and [here](https://github.com/nestauk/patent_analysis/blob/eda/notebooks/02-jmg-patent_merge.ipynb) for the process.

It includes information about all patent applications that have an inventor or applicant based in the UK

## Last update

Data last updated on 9th July 2019

## Enrichment
* Enriched the data with Travel to Work Area codes and names after extracting postcodes
* Added 'AI' flags based on the patents identified as AI by the Intellectual Property Office in their global patent landscape.
  * See report [here](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/808891/AI-a-worldwide-overview-of-AI-patents.pdf)
  * Get AI patent ids [here](https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/808699/AI-raw-data.csv)

## Known issues

* Currently missing IPC codes
* Missing a significant number of addresses (although this might be an artifact of how the data has been extracted)
* Large number of duplicates in the organisation names

## Variables

For more information about the variables, check the PATSTAT data dictionary [here](https://github.com/nestauk/patent_analysis/blob/eda/references/patstat_data_dict.pdf)

|name|type|observations|
|----|----|----|
|appln_id|<class 'numpy.int64'>|  Id for a patent application |
|appln_nr|<class 'str'>|  Application number from the patenting authority|
|ipr_type|<class 'str'>|  Type of intellectual property - can be a patent of invention (PI), design patent (DP) or Utility Model (UM) |
|granted|<class 'str'>|  Whether the patent was granted ('Y') or not ('N') |
|appln_auth|<class 'str'>|  Code for the application authority eg. US for US patent office |
|appln_filing_year|<class 'numpy.int64'>|  Year when the application was filed |
|earliest_publn_year|<class 'numpy.int64'>|  Year when the application was published |
|docdb_family_id|<class 'numpy.int64'>|  ID of the 'family' the patent application belongs to (see below for a brief explanation of what this means) |
|inpadoc_family_id|<class 'numpy.int64'>| ID of the 'family' the patent belongs to according to a different definition  |
|nb_citing_docdb_fam|<class 'numpy.int64'>| Number of citations received by the family the patent belongs to |
|appl_psn_name|<class 'list'>|  List with names for all patent applicants |
|appl_psn_id|<class 'list'>|  Ids for all patents applicants |
|appl_psn_sector|<class 'list'>|  'sector' for patent applicants (is it a person, company etc) - missing in most cases |
|appl_person_address|<class 'list'>|  Addresses for applicants |
|appl_uk_postcode_long|<class 'list'>| Postcodes for applicants  |
|appl_ttwa|<class 'list'>| Travel To Work Area code for applicants  |
|appl_ttwa_name|<class 'list'>|  Travel to Work Area name for applicants |
|inv_psn_name|<class 'list'>|  As above but for inventors |
|inv_psn_id|<class 'list'>|  As above but for inventors |
|inv_psn_sector|<class 'list'>|  As above but for inventors |
|inv_uk_postcode_long|<class 'list'>|  As above but for inventors |
|inv_person_address|<class 'list'>|  As above but for inventors |
|inv_ttwa|<class 'list'>| As above but for inventors  |
|inv_ttwa_name|<class 'list'>|  As above but for inventors |
|appln_abstract_lg|<class 'str'>|  Language for the abstract (engliish in most cases) |
|appln_abstract|<class 'str'>|  Abstract for the application |
|tf_weight|<class 'list'>|  Weignts for technology fields that the patent relates to |
|tf_techn_field_nr|<class 'list'>|  Codes for the technology fields the patent relates to |
|tf_techn_field|<class 'list'>|  Names for the technology fields the patent relates to |
|raw_ids|<class 'str'>|  Concatenation of `appln_auth` and `appln_nr` used to match with IPO AI patents |
|is_ai_ipo|<class 'numpy.bool_'>|  Flag for wether the patent was identified as AI by IPO in their analysis |

## A brief note on patent families

Patents are generally filed in national jurisdictions such as the US patent office (USPTO), UK patent office (IPO), European Patent Office (EPO) etc.

This creates the risk of double counting the same patent being filed with different patent authorities. One way to manage this risk is by focusing the analysis on patent families.

Patent families are groups of patents sharing a 'priority' - that is, referring to the same first filing which serves to establish priority and gives the applicant a year within which all patents referring to the priority can ignore events after the piority was filed.

Most patent handbooks describe patent families as referring to the same 'invention'.

## TODO

* In cases where we have person (inventor or applicants) for a patent, but not their address, we could create an inferred TTWA based on the TTWA distribution of persons with the same name
* Create a version of the table where every row is a patent family. This will require aggregating org names / TTWAs etc over patent ids. 

