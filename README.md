# Suicide_Prevention_Research_Team
Python projects used for the Suicide Prevention Research Team at Louisiana State University 

The goal of this organization is to reduce suicide rates by enhancing the lives of youth and emerging adults. We achieve this through a combination of research, clinical services, and community engagement. Our research spans both basic research—examining the development and maintenance of suicidal thoughts—to applied research, testing brief interventions aimed at reducing suicide risk.

My role was to lead the Replication of the **Geospatial Identification of Elevated Suicide Risk (GIESR) project**.

Project Context:

- The Geospatial Identification of Elevated Suicide Risk (GIESR) method aims to improve our understanding of suicide risk prevalence at a census-tract level and identify different factors contributing to suicidal ideation.
- For this project, we applied the GIESR method using new screening data from the Texas Children’s Hospital Emergency Center to determine whether suicidal behavior in youth is normally distributed across the Houston Metropolitan area. Identifying neighborhoods at elevated risk for suicide-related behaviors allows for targeted intervention efforts.
- The primary goal of this project was to integrate and standardize data from multiple sources, creating a comprehensive dataset that included key risk factors. This dataset was then analyzed to determine its relationship with suicide ideation rates at the census-tract level.

Challenges & Methodology:
- One of the main challenges was receiving raw datasets containing patient addresses and converting them into census tract data.
- We automated this process using Census Geocoder, a Python-based tool that translates addresses into census tract identifiers.
- The Python script in this repository automates this workflow, significantly improving efficiency.
- Key data sources used in this study included:
  - Houston Police Records
  - Houston State of Health Data
  - Suicide Ideation Rates (independent variable)
- After data processing, an in-depth statistical analysis was conducted in SPSS to identify key predictors of high suicide ideation rates at the census-tract level.
- Using the GIESR model with screening data from Texas Children’s Hospital, we computed the rate of positive suicide screens across 1,528 census tracts in Harris County.
- Results showed that suicide ideation rates ranged from 3% to 48% (Mean = 21.36, SD = 8.56), forming an approximately normal distribution (Skew = 0.56, Kurtosis = 0.25).
- These findings are significant because they allow for statistical analysis of suicidal behaviors at a new social-ecological level, enabling more precise public health interventions.


**Automated Census Geocoding for Suicide Prevention Research (Python Script)**

Project Overview:

This project automates the interaction with the Census Geocoder API to process participant address data efficiently. It was developed for the Suicide Prevention Research Team at Louisiana State University to replace a manual process that would have taken weeks with an overnight, unsupervised script.

The program takes a CSV file containing 249,975 participant records from Texas Children's Hospital, including ID, address, city, state, and zip code. Since the Census Geocoder can only process batches of 9,999 at a time, this script automatically splits the data into batches, submits them sequentially, and handles errors to prevent data loss and unnecessary restarts.

The output file includes the address, census tract, state code, county code, and block number. The program processes the data in a structured manner, ensuring accuracy and efficiency while mitigating API crashes.


Dataset Information:

- Original dataset (input):
- ID
- Address
- City
- State
- Zip Code

Processed dataset (output):
- Address
- Census Tract Code
- State Code
- County Code
- Block Number


Files in the Repository:

- SPR.py – Python script for processing data
- data.txt – Description of the dataset
- requirements.txt – List of required Python libraries


Statistical Findings:
- Using only census tracts with at least 25 surveys (309 tracts total), the data followed a normal distribution:
  - Range: 3% to 48% (45%)
  - Mean: 21.36
  - SD: 8.56
  - Skew: 0.56
  - Kurtosis: 0.25
- A stricter analysis using minimum 50 surveys per tract (63 tracts total) also showed a normal distribution:
  - Range: 10% to 33% (23%)
  - Mean: 20.39
  - SD: 5.26
  - Skew: 0.58
  - Kurtosis: -0.11


Installation & Setup:

To run the program, follow these steps:

Clone the repository:
- git clone https://github.com/ameliatodd2002/DS-Portfolio.git
- cd Project1_Suicide_Prevention_Research
- Install dependencies:
- pip install -r requirements.txt
- Open and run the script (SPR.py).


Conclusion:

- The normal distribution of suicidal behavior across Houston's census tracts enables statistical modeling at a social-ecological level, helping identify high-risk areas.
- This enables us to pinpoint census tracts with higher or lower rates of suicidal behavior.
- Understanding the suicidal behavior distribution can inform the development and targeting of intervention strategies, and it provides a basis for public health planning and resource allocation.
