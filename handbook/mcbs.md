# MCBS

## Data catalog

```
/n/dominici_nsaph_l3/data

mcbs
├── 1999 
│   ├── TODO 
│   ├── TODO 
├── 2000 
│   ├── TODO
├── 2001 
│   ├── TODO
```

## MCBS 2011
## MCBS 2012
## MCBS 2013
## MCBS 2014
No data exists for this year because the questionnaires were not administered. However, a new baseline panel was still selected.

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
The survey files contain information regarding various aspects of the beneficiaries' lives, including topics such as their housing, demographic information, income, and health status. Prior to 2015, these files were labeled "RIC-X" for the various topics, but now they are labeled with titles that reflect their contents, e.g. "Health Status and Functioning (HFQ)". The questions about nicotine and alcohol are included within the nicoalco.csv file under the Survey folder (/n/dominici_nsaph_l3/data/mcbs/mcbs/2015/Survey File 2015/Data/CSV Files/nicoalco.csv/ within FASSE). In order to match these patients with their demographic information, use the demo.csv file with variable BASEID.

In order to learn what each variable represents in these files, please reference the Codebooks folder. For example, to access the code book for the nicotine and alcohol survey, you can navigate to /n/dominici_nsaph_l3/data/mcbs/mcbs/2015/Survey File 2015/Codebooks/nicoalco_2015.txt/ in FASSE to get the codebook. Some variables include the number of drinks per day, if the beneficiary currently smokes, if they ever smoked, etc. The demographic file codebook contains information such as DOB, sex, race, income, state, county, and zipcode. 

# MCBS 2016

