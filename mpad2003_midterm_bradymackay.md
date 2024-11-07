**Date:** 04/11/2024 <br>
**Course Code & Course Name:** MPAD2003A Introductory Data Storytelling (WKS)<br>
**Student's First Name & Last Name:** Brady Mackay<br> 
**Presented to:** Jean-Sébastien Marier<br>

# Midterm Project: Exploratory Data Analysis


## What is the dataset? <br>
The dataset is a collection of requests for services that require action by government workers. And I will be specifically taking a look at it's relationship between the date of the requestand it's description, and whether I can find real life for the flow-change <br>

Over the course of the month of august 2024 the City of Ottawa has recorded their requests from civilians through 311 Contact Centre, Client Service Centre, 311 Email, and Web-based Self- Service portal. It features information such as the Type of call, Where the report came from, and it's request ID. it also has over 28 000 entries making it quite the dificult set to piece through

* [The City of Ottawa's 2024 Service Requests](https://www.arcgis.com/home/item.html?id=65fe42e2502d442b8a774fd3d954cac5)
* [The Provided, Reduced Dataset of Only Data From August 2024](https://raw.githubusercontent.com/jsmarier/course-datasets/refs/heads/main/ottawa-311-service-requests-august-2024.csv)
* [My Own Document](https://docs.google.com/spreadsheets/d/18DKm0AUgxz66YUWfJEMt_JMu6t9Rvz7rFFsmHvPhXy0/edit?usp=sharing)

## Getting the Data Yourself

To start on your own journey of analyzing this data you'll need to download the data, to do that you'll follow the link above labeled "The Provided, Reduced Dataset of Only Data From August 2024" and if you're connected to the internet you'll find yourself on this screen:<br> <br>
![](<Screenshot 2024-11-05 105452.png>)
From there you'd want to rightclick to open the little selection menu and then locate "save as" and click that, and now you've officially downloaded the csv file!<br><br>
Now you'll open up a google sheet, name it apropiately and then fine your way to the "file" tab, and from there find the "import" button, once you click on that you'll have to upload the file and wait for it to finish.<br> <br> 
![](<Screenshot 2024-11-05 115907.png>)<br>
Now all there is to do is to set the import location to "Append to current sheet" and your separator type to comma and then just click the import button and your Table should look like this!<br> <br>
![alt text](<Screenshot 2024-11-05 170049.png>)<br><br>
### Observations 

Now that we both have the data we can make a couple observations about the content, taking a look at it couple things stand out; the sheer amount of rows, 28538 in the narrowed data to be exact that compared to the 11 columbs it's a huge amount of data to parse through. If you look closely at the dates after scrolling all the way to the bottom you can tell that it doesn't end in august, there is a single datapoint for September first. Other than that outliers though the data looks clean! 
<br><br> a couple things to note though, it's very telling that according to this that over 10% of service requests are still active 3 months later! And beyond that 1% of all requests are cancelled. There are 12 different types of requests, including ones that are non-valued but the only two that are like that are "Property Standards - Grass Long/Weeds." and when we're looking at specific addresses only 2% had more than one service call during the month of august and the place with the most is 99 Cobourg St, "MacDonalds Gardens Park" with 18 calls, because it seems to need a lot of maintenence and is a high traffic grafitti spot.  <br><br>
It makes you wonder, how many calls do they get a day if there are so many entries in just august? does anything specific happen to make the flow of calls increase? what makes a specific place more likely to make calls? I'd think it might be related to the daily events around the location, like a tree falling would get significantly more calls about it.

## 3. Understanding Deep Dive

### 3.1. Analysing Data Using the VIMO Method

Now, let's get into the thick of the data using the VIMO strategy!<br>
To start, we must identify if datapoints are valid, we look to see if any content is blank or missing or outside of the valid range. VIMO stands for: Valid, Invalid, Missing, Outlier, we will be mostly concentrating on the date the case was opened, and the description of the problem. <br>The Date Opened: as we talked about before, almost every single date is valid, none are written as something other than a date, and none are missing entirely, but there is a single outlier, the one date outside of August, a call on September first, clearly a mistake by whomever reduced this data. and now the description: again, most datapoints are valid, there are no clearly invalid descriptions, there are no outliers, but there is a strange pattern of missing data. it seems like after august 21 many calls under the type "water and the environment" were left descriptionless, it's very strange that it's only after a certain date, all "water and the environment" type calls got a description in the early days of the month, sadly, we can only speculate what occured

### 3.2. Spring Cleaning

Now to clean up these datapoints we identified as invalid with the VIMO method. the first strategy I employ is to create a filter on the descriptions tab and filter out all of the missing datapoints, though there weren't many there were still enough to mess with the data. Since there was only a single point that is outside of our date range, we'll employ the fool-proof method of manually seaching and deleting it, which for a small number of invalid datapoints is the most effective. I also removed the longitude and latitude columbs due to the fact that they effect very few datapoints. that last thing I did was use the =SPLIT command to remove the french part of the description columb as no other columb had that and it was just cluttering up the visual of the table

**Refrences**

![](<Screenshot 2024-11-06 185139.png>)
=SPLIT(D?, "|")

### 3.3. Exploratory Data Analysis (EDA)

Insert text here.

**This section should include a screen capture of your pivot table, like so:**

![](pivot-table-screen-capture.png)<br>
*Figure 2: This pivot table shows...*

**This section should also include a screen capture of your exploratory chart, like so:**

![](chart-screen-capture.png)<br>
*Figure 3: This exploratory chart shows...*

## 4. Potential Story

Insert text here.

## 5. Conclusion

Insert text here.

## 6. References

Include a list of your references here. Please follow [APA guidelines for references](https://apastyle.apa.org/style-grammar-guidelines/references). Hanging paragraphs aren't required though.

**Here's an example:**

Bounegru, L., & Gray, J. (Eds.). (2021). *The Data Journalism Handbook 2: Towards A Critical Data Practice*. Amsterdam University Press. [https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153](https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153)
