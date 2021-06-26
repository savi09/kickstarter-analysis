# kickstarter-analysis
Kickstarter excel analysis

## About Kickstarter Analysis
The data was retrieved from Kickstarter. Kickstarter is a service where organizations can post projects to look for funding. Not all projects are successful. Excel was used to find trends within the past 4,000 projects.

## Analysis

### Results
Conclusion one: The main difference between Kickstarter's successful and unsuccessful campaign is the number of project backers. The median amount of backers for unsuccessful campaigns was four, while successful campaigns had sixty-two backers. Median is a better measurement of the data's central tendency because there are too many outliers that are skewing the distribution. Variability is greater in successful campaigns because they have different funding goals. Some campaigns need more backers to meet their goals, while others need less.

Conclusion two: Kickstarters' top 3 primary categories that met or exceeded their goal were music with 77.14% of projects, theatre projects with 60.23%, and film & video with 57.69%.

Conclusion three: Documentaries, hardware technology, and rock music subcategories received 100% success and had over 100 campaigns launched.

### Data Limitations
    Project goals use different currencies.
    Too many outliers that skew data.
    Cultural or personal preferences of backers might determine which projects they are willing to fund.
    
### Next Steps
    CompCompare blurbs: Do blurbs from successful campaigns have anything in common? What about for unsuccessful campaigns?
    Compare by currencies: Compare success rates by the currency or equate the goals. This could resolve issues with outliers.
    Compare by country: Compare success rates by country. There are systematic differences across countries. This will shed light on some trends that might be worth noting.
# Excel Sheet Description

## Tab 1: StarterBook
Tab one is the data retrieved from Kickstarter. The data included the following columns:
Project ID (id), Project Name (name), A short blurb about the project (blurb), project fundraising goal (goal), amount funded (pledged), the state of the project (state), the country the project is located in (country), the currency of the fundraising goal (currency), the project deadline (deadline), the date the projected was created on Kickstarter (launched_at), staff pick (staff_pick), the number of people who pledged to the project (backers_count), spotlight, and the category and subcategory of the project (Category and Sub-Category)

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
    
The percent funded column was formatted using a three-color scale.  
    0% - Red  
    100% - Green  
    200% - Blue  
    
## Tab 2: Pivot_CategoryState
Tab two includes a stacked column pivot chart to view the state (live, successful, canceled, or failed) of campaigns based on their primary category. This chart can be filtered by campaign country location to better understand the trend based on campaigns' location.

## Tab 3: Pivot_SubcatState
Tab three includes a stacked column pivot chart to view the state of campaigns based on their secondary category. This chart can be filtered by campaign country location and primary category to better understand this trend based on campaigns' location and/or category.

## Tab 4: Pivot_Date
Tab four includes a line graph pivot chart to visualize the relationship between the number of successful, failing, or canceled campaigns and the date the campaign launched its project on Kickstarter. This chart can be filtered by the campaigns' primary category and year launched.

## Tab 5: Goal
Tab five includes a table with the number and percentages of campaigns that are successful, failed, or canceled divided goal range. A line chart is included to visualize the relationship between goal range and the chance of being successful, failing, or canceled.

## Tab 6: Statistical Analysis
Tab six includes data extracted from the initial data tab, a summary table of backers, and a box plot. Campaign state (outcome) and the number of backers (backers_count) were extracted into this tab. The summary table includes the mean, median, minimum, maximum, variance, and standard deviation of the count of campaign backers. The box plot visualizes the number of outliers.
