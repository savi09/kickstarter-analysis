# kickstarter-analysis
Kickstarter excel analysis

## About Kickstater Analysis
The data was retirieved from Kickstarter. Kickstarter is a service where organizations 
can post projects to look for funding. Not all projects are successful. Excel was used 
to find trends within the past 4,000 projects.

## Analysis

### Results
Conclusion one: 
    The main differnce between successful and unsuccessful campaign is the number of 
    project backers. The median amount of backers for unsuccessful campaigns was four, 
    while successful campaign had sixty-two backers. Median is a better measurement of
    the the data's central tendency, because there are too many outliers that are skewing 
    the distribution. Variability is greater in successful campaigns because they have 
    different funding goals. Some campaigns need more backers to meet their goals, while 
    others need less.
    
Conclsion two:
    The most successful categories

### Data Limitations
    Do not have equivalent currencies.
    Too many outliers.
    
### Next Steps
    Compare blurbs: Do blurbs from successful campaigns have anything in common? What 
     about for unsuccessful campaigns?
    

# Excel Sheet Description

## Tab 1: StarterBook
Tab one is the data retrieved from Kickstarter. The data included the following columns:  
Project ID (id), Project Name (name), A short blurb about the project (blurb), project 
fundraising goal (goal), amount funded (pledged), the state of the project (state), the 
country the project is located in (country), the currency of the fundraising goal 
(currency), the project deadline (dealine), the date the projected was created on 
Kickstarter (launched_at), staff pick (staff_pick), the number of people who made a 
pledge to the project (backers_count), spotlight, and the category and subcategory of the 
project (Category and Sub-Category)

### Added columns
  Percent Funded = pledged/goal  
  Average Donation = pledged/backers_count  
  Category = LEFT(N2,(FIND("/",N2,1)-1)) (Seperates Category and Sub-category column)  
  Sub-category = MID(N2,FIND("/",N2)+1,256) (Seperates Category and Sub-category column)  
  Date Created Conversion = (((J2/60)/60)/24)+DATE(1970,1,1) (Converts Unix timestamps/ launched_at)  
  Date Ended Conversion = (((I2/60)/60)/24)+DATE(1970,1,1) (Converts Unix timestamps/ deadline)  

The state column was formatted to make the state of the campaign visible.  
    Deep Green - The project is **successful**. The project met or exceeded its fundraising goal.
    Light Green - The project is **live**.   
    Yellow - The project was **canceled**.  
    Red - The project **failed**.  
    
The percent funded column was formatted using three-color scale.  
    0% - Red  
    100% - Green  
    200% - Blue  
    
## Tab 2: Pivot_CategoryState

Tab two includes a stakced column pivot chart to view the state (live, successful, canceled, 
or failed) of campaigns based on their primiary category. This chart can be filtered by 
campaign country location to better understand the trend based on campaigns' location.

## Tab 3: Pivot_SubcatState

Tab three includes a stakced column pivot chart to view the state of campaigns based on their 
secondary category. This chart can be filtered by campaign country location and primary 
category to better understand this trend based on campaigns' location and/or category.

## Tab 4: Pivot_Date

Tab four includes a line graph pivot chart to visualize the relationship 
between the number of successful, failing, or canceled campaigns and date
the campaign launched their project on Kickstarter. This chart can be filtered by campaigns' 
primary category and year launched.

## Tab 5: Goal

Tab five includes a table with the number and percentages of campaigns that are successful, 
failed, or canceled divided goal range. A line chart is included to visualize the relationship 
between goal range and chance of being successful, failing, or being canceled.

## Tab 6: Statistical Analysis

Tab six includes data extracted from the initial data tab, a summary table of backers and a
box plot. Campaign state (outcome) and the number of backers (backers_count) was extracted 
into this tab. The summary table includes the mean, median, minimum, maximum, variance, 
and standard deviation of the count of campaign backers. The box plot visualizes the number 
of outliers.
