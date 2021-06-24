# kickstarter-analysis
Kickstarter excel analysis

## About Kickstater Analysis
The data was retirieved from Kickstarter. Kickstarter is a service where organizations 
can post projects to look for funding. Not all projects are successful. Excel was used 
to find trends within the past 4,000 projects.

## Analysis

#Excel Sheet Description

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
    Deep Green - The project is **live**.  
    Light Green - The project is **successful**. The project met or exceeded its fundraising goal.  
    Yellow - The project was **canceled**.  
    Red - The project **failed**.  
    
The percent funded column was formatted using three-color scale.  
    0% - Red  
    100% - Green  
    200% - Blue  
    
## Tab 2: Pivot_CategoryState
## Tab 3: Pivot_SubcatState
## Tab 4: Pivot_Date
## Tab 5: Goal
## Tab 6: Statistical Analysis
