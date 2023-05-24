---
title: "West Virginia Hospitals"
excerpt: Here is map showing hospital locations compared to race, median household income, and population density. Data was retreived from West Virginia GIS technical Center, and the U.S. Census.  <br/><img src='/images/WVhospitals.jpg'>
collection: portfolio
---
<br/><img src='/images/WVhospitals.jpg'>

Introduction
======
Access to quality healthcare in the United States is a big issue to many people as many disparities in healthcare access exist due to race or poverty status. The ability to access medical care during an emergency is incredibly important to address when examining healthcare disparities as the amount of time it takes to get to a hospital can be the difference between life or death. Areas in which medical care is hard to find are known as medical, or care deserts, and are often found in rural or low income areas. This project aims to highlight these disparities by showing the relationship between hospital locations and the population statistics such as race, median household income, and population density. 
I chose West Virginia to model disparity in access to hospitals because the state is notorious for having some of the worst healthcare in the country. Because care deserts are common, I believed population density to have the greatest impact on where the hospitals are located. A hospital point shapefile was downloaded from the West Virginia GIS Technical center. Information on the West Virginia population was taken from the United States Census using Tidy Census in Rstudio. Median household income, total population, and race percentage information for each county was plotted using ggplot. The plots were then downloaded as a shapefile using st_write, and manipulated in QGIS. Population density was found by using geometry statistics in QGIS for the total population shapefile, then adding a field to calculate the total population divided by the area in square miles. 
	
Methods 
======
The first map I created in Rstudio was the median household income. I used get_acs to find information on the counties and plotted them using ggplot. The second map I created was percentage race. I created a map showing the percentage of people identifying asian, black, hispanic, native and white in 2020 using tidy census. This was then plotted using tm_shape. However I only included the white percentage in the final layout because I believed this would have the greatest impact on hospital locations. <br/><img src='/images/wvrace.jpg'> 

Finally I created a map showing the total population per county using get_acs and ggplot.  
I saved the previous shapefiles and brought them into QGIS where I manipulated the data to better show the results. I took the shapefile for total population and found the area by creating a new field in the attribute table then using geometry area. This found the area of each county in square miles. I then created a new field where I used previous fields to find the population density by dividing the total population by the area in square miles. 

Analysis 
======
After plotting all the information, I found that population density had the greatest effect on hospital locations. Median household income had little effect, as many counties were in the 40,000-50,000 range, and in general the ones that had higher or lower income did not have a different number of hospitals. Race percentage also had little effect, as many counties with a high percentage of white people (95-100) had no hospitals, and the counties with lower percentage of white people such as Kanawha had multiple hospital locations. As hypothesized previously, population density had the greatest impact on hospital locations. Several of the lowest populated counties had no hospitals at all, while several of the highest populated counties had up to five hospitals. 

Conclusion
======
While each of these factors plays a significant role in healthcare access, our findings suggest that population density has the greatest influence on the number of hospitals.  This may be because hospitals require a large number of workers, and it is not feasible to have a hospital in a location where they cannot adequately staff it.  High population densities also put a strain on healthcare resources, meaning they are needed more frequently in these areas as opposed to areas with low population. By acknowledging the importance of population density in healthcare access, we can work towards creating a healthcare system that is responsive, inclusive, and equitable towards communities with low populations that often get overlooked.

