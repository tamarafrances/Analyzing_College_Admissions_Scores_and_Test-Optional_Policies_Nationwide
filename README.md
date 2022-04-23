# Project 1
# Standardized Test Analysis: Analyzing Test Scores and Test-Optional Policies across the U.S.

# Tamara Frances
<br>


### Objective

Presented with a list of SAT and ACT test related datasets, my goal was to identify and investigate potential trends and relationships with the provided data and outside data sources in order to address a problem statement of our choosing.
<br>
<br>


### Problem Statement

Test-optional college admissions policies greatly expanded in 2020 and 2021 due to the COVID-19 pandemic. This change further complicated the already complex and time-intensive college application process for students and their families.

This project aims to increase transparency in the college application process by exploring the following:
* the current landscape of test-optional policies among colleges and universities across the U.S
* whether there is a relationship between SAT and ACT scores and college acceptance rates
* whether there are trends among SAT and ACT scores and a variety of intended college majors.<br><br>



### Description of the data<br>
#### Sources
**2019 Total Group SAT Suite Assessments Annual Report** ([source](https://reports.collegeboard.org/pdf/2019-total-group-sat-suite-assessments-annual-report.pdf))

This data set describes the mean SAT reading/writing scores and the mean SAT math scores by intended college major in 2019. It also outlines the amount of test takers per intended college major, along with the percentage of students who indicated each major out of the total test takers. There are 38 different intended college major groups outlined in this data set.

<br>

**SAT and ACT Policies and Score Ranges for Popular Colleges and Universities** ([source](https://www.compassprep.com/college-profiles/))

This data set describes the test-optional policies, policy years, policy details, number of applicants, acceptance rates, and SAT and ACT score ranges for over 400 colleges and universities across the U.S. The data is ordered by acceptance rate.

<br>

#### Data Dictionary
<br>
2019 Total Group SAT Suite Assessments Annual Report
<br><br>

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**intended_college_major**|*object*|College Board SAT Suite 2019|Student self-selected intended college majors, 38 total| 
|**num_sat_takers**|*object*|College Board SAT Suite 2019|Number of test takers by intended college major|
|**percent_of_majors**|*float*|College Board SAT Suite 2019|Percent (%) of test takers with intended college major out of total test takers|
|**total_score**|*int*|College Board SAT Suite 2019|Mean total SAT score (out of 1600)|
|**mean_sat_reading_writing**|*int*|College Board SAT Suite 2019|Mean reading and writing SAT score (out of 800)|
|**mean_sat_math**|*int*|College Board SAT Suite 2019|Mean math SAT score (out of 800)|

<br>SAT and ACT Policies and Score Ranges for Popular Colleges and Universities<br>

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**school**|*object*|Compass Education Group|College or university name| 
|**are_tests_optional**|*object*|Compass Education Group|Yes or No statement regarding presence of test-optional policies at the school|
|**last_class_year**|*object*|Compass Education Group|The last application year the test-optional policy will be in place|
|**policy_details**|*object*|Compass Education Group|Details of the test optional policy|
|**num_of_applicants**|*int64*|Compass Education Group|Number of applicants to the school|
|**acceptance_rate**|*float64*|Compass Education Group|Percent (%) of students accepted among those who applied|
|**sat_total_middle_range**|*object*|Compass Education Group|Range of 25th and 75th percentile SAT scores accepted by the school|
|**act_total_middle_range**|*object*|Compass Education Group|Range of 25th and 75th percentile ACT scores accepted by the school|
|**sat_25th_percentile**|*float64*|Compass Education Group|25th percentile of school's accepted SAT scores|
|**sat_75th_percentile**|*float64*|Compass Education Group|75th percentile of school's accepted SAT scores|
|**act_25th_percentile**|*float64*|Compass Education Group|25th percentile of school's accepted ACT scores|
|**act_75th_percentile**|*float64*|Compass Education Group|75th percentile of school's accepted SAT scores|
<br><br><br>

### Methods and Findings

**Finding 1: Almost half of schools have test-optional policies that end after 2021**
* By counting the categorical variables in the last_class_year feature using countplot(), the data showed that  47% of schools with test-optional policies plan on letting it lapse after the 2021 application period.
* Almost 10% of schools have policies that are scheduled to lapse between 2022 and 2025.
* Almost 40% of schools have permanent test-optional policies.


**Finding 2: As college acceptance rates increase, accepted SAT and ACT scores decrease**
* In the SAT and ACT policies dataset, SAT and ACT test score percentiles were presented as an object data type.
* I isolated the 25th and 75th percentiles for each test type by iterating through the total_middle_range columns, splitting the data, and reassigning them to columns signifying their score percentiles.
* By creating scatter plots for the newly created 25th and 75th percentile columns for both the SAT and ACT, along with creating a correlation matrix, it became clear that there was a strong negative correlation between school acceptance rate and accepted test scores. The higher the acceptance rate, the lower the accepted test scores.
* I created two-group horizontal lollipop plots as well in order to drill down on the test score ranges further. This visualization provides a clearer understanding of the exact accepted test score ranges by school in comparison to others.

**Finding 3: Students intending to pursue science-related majors tend to have higher total mean SAT scores**
* I was interested in understanding if there were any trends among intended college majors and mean total SAT scores. To dig into this further, I sorted the majors by their total mean score and visualized the data on a horizontal lollipop chart.
* Four of the top five mean scores belonged to science-based majors (e.g. math and statistics, physical sciences, and computer and information sciences).

<br>

### Conclusions

* Testing is important - over half of schools will not have a test-optional policy for the 2022 application cycle. Again, this is based on data from 2021 and this may have changed. Even with test-optional policies, some students may benefit from submitting their test scores.

* There is a relationship between test scores and school selectivity. The more selective the school, the higher the accepted SAT and ACT scores.

* There are trends among intended field of study and test scores. Students intending to pursue science-related majors should aim for even higher SAT scores to remain competitive. This is especially important for students applying to schools that have selective science or engineering programs or tracks that incoming students apply to on top of general admission.
<br>

### Next Steps

* I would be interested in looking at variables other than college selectivity to see if there are relationships between other aspect(s) of the college and test scores (i.e. size, cost, public vs. private, region).


* Regarding the mean SAT scores by college major, if I were to further iterate on this analysis, I would be interested in seeing if the trend of students intending to pursue science-related majors having higher test scores holds true for the separate reading/writing and math sections of the SAT.

<br>

### Sources
#### Background Information
* Dance, Amber. “Has the Pandemic Put an End to the SAT and ACT?” Smithsonian Magazine, 15 July 2021, www.smithsonianmag.com/innovation/has-pandemic-put-end-to-sat-act-180978167/. Accessed 2 Apr. 2022.
* SAT Suite of Assessments Annual Report. The College Board, 2019.
* Sawyer, Art. “SAT and ACT Policies and Score Ranges for Popular Colleges and Universities.” Compass Education Group, 6 Oct. 2020, www.compassprep.com/college-profiles/. 
* “What SAT Score Is Required for Engineering Majors?” Www.techpoweredmath.com, 24 July 2018, www.techpoweredmath.com/what-sat-score-required-engineering/. Accessed 3 Apr. 2022.


#### Code
* Holtz, Yan. “Lollipop Chart.” The Python Graph Gallery, www.python-graph-gallery.com/lollipop-plot/. Accessed 2 Apr. 2022.
* “Lollipop Plot with 2 Groups.” The Python Graph Gallery, www.python-graph-gallery.com/184-lollipop-plot-with-2-groups. Accessed 2 Apr. 2022.
* “Python - Dictionary Comprehension to Apply a Function to DataFrame Columns.” Stack Overflow, 7 Mar. 2019, www.stackoverflow.com/a/55048684. Accessed 1 Apr. 2022.

#### Images
* Works Cited “ACT & SAT Preparation.” Katherine Miller Education, www.katherinemillereducation.com/act-and-sat-preparation/. Accessed 3 Apr. 2022.
* Wikipedia Contributors. “SAT.” Wikipedia, Wikimedia Foundation, 16 Sept. 2019, www.en.wikipedia.org/wiki/SAT.
