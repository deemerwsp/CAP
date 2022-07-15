### Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data](#Data)
- [Data Dictionary](#Data-Dictionary)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

### Problem Statement

What are the factors that determine the time it takes to locate and rescue victims in need of rescuing, both in the wilderness and other non-wilderness environments. How can different factors of Search and Rescue efforts indicate the total timeframe of a SAR mission and how can civilians understand these SAR processes and factors in order to give themselves the best chance of receiving aid in the event of their recuiring rescue. 


### Executive Summary

Search and Rescue is a public service that has become increasingly necessary contingent with the increasing number of US civilians enjoying the beautiful national parks and wilderness in our country. There are inherent risks when persons endeavor any adventure into the outdoors, and these SAR missions are the safety net that mitigate those risks and ultimately save lives. As the number of civilians venturing out into these risk proned environments increases, the necessity of these professional SAR teams increases in correlation. 

For the most part, these SAR teams are not governmentally funded and are comprised of non-paid volunteers. Members of these SAR teams are highly skilled and predominantly philanthropic. The frequency of incidents requiring SAR missions increase annually. These SAR teams are becoming overwhelmed and financially unsubstainable. Certain states with higher frequencies of necessary SAR missions understand the importance of this public service and consequently have allocated public funds towards these non-profit organizations resulting in higher success rates and reduced times for SAR mission completion. 

This data analysis and subsequent machine learning models reveal the quintessential factors that either improve or impair the success of a SAR mission. These analyses are meant to aid SAR teams/organizations in their efforts to achieve mission success, educate individuals on SAR processes and how they can improve their chances of being located/rescued, and conclusively show how certain states with higher frequency of SAR missions and success rates benefit from state goverment financial/legislative support. 

---

### Data
- [original_dataset](https://experience.arcgis.com/experience/5a9928653c6c45ca94ae29c8ce90cf91/page/Open-Data/)
This data was collected from the [Mountain Rescue Association](https://mra.org)

### Data Dictionary

|Feature|Description|
|--:|:--|
|**time_bin**|**Target:**  0-11 hours, 11-32 hours, 32 hours-7 days|
|**number_volunteers**|Number of volunteers (continuous variable) involved in SAR mission|
|**number_subjects**|Number of subjects involved in SAR mission (limited to up to 10 subjects)|
|**area_type**|**Type of area:** wilderness, urban_rural, unknown, water, interface (urban/rural/wilderness)|
|**total_aircrafts**|Number of different types of aircrafts involved: helicopter, fixed-wing, UAV|
|**children**|OHE feature where children (1-15 years old) involved|
|**seniors**|OHE feature where seniors (65+) involved|
|**mental**|OHE feature where any subject has a mental factor or rating other than normal|
|**winter**|OHE feature for incidents occuring in winter months or snow conditions|
|**daylight**|OHE feature where mission initiated in daylight hours (7am - 8pm)|
|**state**|Dummified feature for each state out of 19 states|


---

### Conclusions and Recommendations

The Logistic Regression model offers more human interpretabillity and thus is the recommended model to incorporate into production. This model is 58% accurate in predicting the target class, 23% more than the baseline model of 35% probability in predicting the majority class. 

Evidently the number of types of aircrafts used in a SAR mission does indicate the target time to completion of a SAR mission. Most likely these missions were achieved in a lesser time than those without any aircrafts involved. We can summize through background knowledge that the inclusion of any aircraft does reduce the time it takes to complete a SAR mission. In terms of machine learning models, if any aircraft type was involved, a longer timeframe is indicated as most missions are not instantiated with a call for any aircraft. When an aircraft is needed after initial efforts, the time frame has most likely passed 11 hours. 

If a SAR team or organization intended to use a machine learning model to predict the time it will take to complete a SAR mission, I would recommend incorporating the random forest model as it is more accurate compared to the logistic regression model. 
