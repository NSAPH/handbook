# MCBS

## MCBS Prior To 2015

The available MCBS data prior 2015 is not optimal for data analysis. No data exists for 2014 because the questionnaires were not administered. However, a new baseline panel was still selected.

## MCBS 2015

### Changes in 2015
This marks the first use of the Survey and Cost Supplement files. Previously, these were called the Access to Care and Cost and Use files, respectively. The survey files can be standalone, or the Cost Supplement files can be considered, but in order to access important demographic information, the survey files are necessary. The beneficiaries the Cost Supplement are a subset of the Survey beneficiaries. In general, each participant will have data for four years in the Survey file and for three years in the Cost Supplement file. In 2015, ghosts were no longer used to give an extra year's worth of information in the Cost files. 

According to the Methodology documentation: "Beginning in 2015, beneficiaries who became eligible for Medicare Part A or B and enrolled anytime during the sampling year were eligible to be sampled as part of the annual MCBS panel. Prior to 2015, only beneficiaries who became eligible on or before January 1 of the sampling year were eligible to be sampled." 


#### Data Collection Timeline Changes
2015's questionnaire timeline was unique due to the transition between questionnaire types.  According to the Methodology documentation: "the Fall 2014 round was conducted from September 2014 through March 2015; the Winter 2015 and Summer 2015 rounds were combined into a single, longer data collection period that was conducted from March 2015 through August 2015; and the Fall 2015 round was then conducted from August 2015 through early January 2016. Thus, the 2015 MCBS data releases reflect data collected from March 2015 through the first week in January 2016". 

Below shows an image that explains the timeline for a typical year compared to that of 2015. 
<img width="830" alt="Screen Shot 2022-06-20 at 9 51 58 AM" src="https://user-images.githubusercontent.com/89894104/174616716-8b5fa860-ad53-42de-b4ba-8f13fb9a149d.png">


#### Sampling Methods
In 2015, Hispanic beneficiaries living outside of Puerto Rico were intentionally oversampled. Additionally, beneficiaries under age 45 with disabilities and beneficiaries over age 85 were intentionally oversampled in order to better understand their medical needs.


### Data Location and Contents
The survey files contain information regarding various aspects of the beneficiaries' lives, including topics such as their housing, demographic information, income, and health status. Prior to 2015, these files were labeled "RIC-X" for the various topics, but now they are labeled with titles that reflect their contents, e.g. "Health Status and Functioning (HFQ)". The questions about nicotine and alcohol are included within the nicoalco.csv file under the Survey folder (`/n/dominici_nsaph_l3/data/mcbs/2015/survey_file/data/csv/nicoalco.csv` within FASSE). In order to match these patients with their demographic information, use the demo.csv file with variable BASEID.

In order to learn what each variable represents in these files, please reference the Codebooks folder. For example, to access the code book for the nicotine and alcohol survey, you can navigate to `/n/dominici_nsaph_l3/data/mcbs/2015/survey_file/codebooks/nicoalco_2015.txt` in FASSE to get the codebook. Some variables include the number of drinks per day, if the beneficiary currently smokes, if they ever smoked, etc. The demographic file codebook contains information such as DOB, sex, race, income, state, county, and zipcode. 

#### Data Tree

To access MCBS data, please open FASSE and navigate to `/n/dominici_nsaph_l3/data/mcbs/2015/`. Below, you can see a data tree reflecting the folder structure of the `2015` folder:

``` 
|-- cost_supplement
|   |-- codebooks
|   |-- data
|   |   |-- csv
|   |   |-- formats
|   |   `-- sas
|   `-- documentation
`-- survey_file
    |-- codebooks
    |-- data
    |   |-- csv
    |   |-- formats
    |   |-- research_claims
    |   |   |-- csv
    |   |   `-- sas
    |   `-- sas
    |-- documentation
    `-- questionnaire
        `-- Showcards\ and\ Reference\ Cards
            |-- Community
            |   `-- Community\ Showcards\ HI2-HI6
            `-- Facility 
```


Above we can see the overall setup of the directories. Most of the files that will likely be used in data analysis are in `/survey_file/data/csv', and these data files are also stored in the SAS .sas7bdat format within the sas folder. The codebooks folder provides information for each variable included in the code, along with the survey logic (e.g. any skip patterns used in the survey), and what the different values signify in the data (the variable used for missing data, any data binning, etc.). The documentation folder contains more detailed information about how the data was collected and describes the contents of each survey at a high level. 

Much of the data of interest will be in the `survey_file/data/csv/` folder. Below we can see the files in this folder:

```
|-- accesscr.csv
|-- admnutls.csv
|-- agreescl.csv
|-- assist.csv
|-- cenwgts.csv
|-- chrncdfl.csv
|-- chrncond.csv
|-- demo.csv
|-- evrwgts.csv
|-- facasmnt.csv
|-- facchar.csv
|-- falls.csv
|-- foodins.csv
|-- genhlth.csv
|-- hhchar.csv
|-- hisumry.csv
|-- hitline.csv
|-- incasset.csv
|-- interv.csv
|-- lng3wgts.csv
|-- lng4wgts.csv
|-- maplanqx.csv
|-- mcreplnq.csv
|-- mds3.csv
|-- nagidis.csv
|-- nicoalco.csv
|-- oasis.csv
|-- pmuse.csv
|-- pntact.csv
|-- prevcare.csv
|-- rxpartd.csv
|-- satwcare.csv
|-- uscppic.csv
`-- vishear.csv
```
The survey data as well as the weight variables are included. Notice that for continuously enrolled weights, you should use `cenwgts.csv`, for ever enrolled weights you should use `evrwgts.csv`, and for longitudinal weights, use `lng3wgts.csv` and `lng4wgts.csv`. `lng2wgts.csv` does not exist for 2015 because surveys were not released for 2014. 

#### Data Dictionary for Nicotine and Alcohol Survey 2015
Since the nicotine and alcohol survey is of particular interest, below is a data dictionary with several variable names of potential interest and a corresponding description. To access this file, please navigate to `/n/dominici_nsaph_l3/data/mcbs/2015/survey_file/data/csv/nicoalco.csv`. The dictionary below is based upon the codebook for nicotine and alcohol; for additional variables and their information, please reference the codebook located in `/n/dominici_nsaph_l3/data/mcbs/2015/survey_file/codebooks/nicoalco_2015.txt`.

| Variable Name      | Description | Values |
| ----------- | ----------- | ---- |
| BASEID       |    Beneficiary's unique ID number, linkable to other MCBS and Medicare files     |   |
|  EVERSMOK   |      If the beneficiary has ever smoked cigarettes/cigars/tobacco    |  D= Don't know <br> R=Refused <br> 1=Yes <br> 2= No |
| SMOKNOW | If the beneficiary currently smokes; only asked if the said they ever smoked | . = Inapplicable/Missing <br> R = Refused <br> 1=Yes <br> 2=No |
| DIDSMOKE| Number of years the beneficiary did smoke; only asked if the beneficiary has ever smoked but is not a current smoker | D=Don't know <br> .=Inapplicable/Missing <br> R=Refused <br> 1-95=Number of years the beneficiary smoked <br> 96=Less than one year of smoking|
| DRINKDAY | Beneficiary's number of days per month drinking alcohol | D=Don't know <br> .=Inapplicable/Missing <br> R=Refused <br> 0=None <br> 1-31=Number of days drinking per month|
| DRINKSPD | Beneficiary's number of drinks per day; only asked if the beneficiary drinks at least one day per month | D=Don't know <br> .=Inapplicable/Missing <br> R=Refused <br> 1-16+=Number of drinks consumed per day |

Please note that some of the variables have a high number of inapplicable values denoted ., included SMOKNOW, DIDSMOKE, and DRINKSPD because of their inclusion criteria; you needed to denote that you previously drank/smoked to be included in the question. You can write a script to fill in 0 as a value for some of the inapplicable beneficiaries. For example, you can fill in the number of drinks per day as 0 for people who drink 0 days per month with something similar to the following R script:

```
for (ben in 1:nrow(nicoalco_data_2015)){
  if(nicoalco_data_2015[ben,]$DRINKDAY == 0){
    nicoalco_data_2015[ben,]$DRINKSPD <- 0
  }
}
```



# MCBS 2016

MCBS in 2016 is similar to that of 2015. The files are organized in the same way as those in 2015 (please reference the data tree above). However, some of the files included in the survey are different. Please reference the list below to see the different file names. Note that in 2016, there are longitudinal weights for 1 and 3 years prior (`lng2wgts.csv` and `lng4wgts.csv`, respectively), but not for 2 years as there were no surveys in 2014.
```
|-- accesscr.csv
|-- admnutls.csv
|-- assist.csv
|-- cenwgts.csv
|-- chrncdfl.csv
|-- chrncond.csv
|-- demo.csv
|-- dental.csv
|-- diabetes.csv
|-- evrwgts.csv
|-- facasmnt.csv
|-- facchar.csv
|-- falls.csv
|-- foodins.csv
|-- genhlth.csv
|-- hhchar.csv
|-- hisumry.csv
|-- hitline.csv
|-- incasset.csv
|-- interv.csv
|-- lng2wgts.csv
|-- lng4wgts.csv
|-- maplanqx.csv
|-- mcreplnq.csv
|-- mds3.csv
|-- menthlth.csv
|-- mobility.csv
|-- nagidis.csv
|-- nicoalco.csv
|-- oasis.csv
|-- pmuse.csv
|-- pntact.csv
|-- prevcare.csv
|-- restmln.csv
|-- rxpartd.csv
|-- satwcare.csv
|-- uscare.csv
`-- vishear.csv

```

For more information on what these surveys contain, please consult the documentation located in the documentation folder which describes the surveys at a higher level, as well as the codebooks in the codebooks folder which explain each variable and what the different values represent.




