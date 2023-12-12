# nyc-public-school-dashboard
Dashboard visualizing data from NYC public schools using R and Tableau


For our project, we have designed three distinct school dashboards: District Level, School Level, and Socioeconomic Analysis. Our data collection involved sourcing diverse datasets from NYC Open Data, encompassing information such as school districts' overall grades, attendance records, graduation and dropout rates, as well as comprehensive demographic data. 

In the case of individual schools, we went beyond the basic metrics and sought out data that included overall "ratings" for schools on a standardized scale. This approach enables a direct and meaningful comparison between different schools, offering a more comprehensive view of their performance and characteristics.

Upon cleaning our data to align with our project requirements, we seamlessly integrated individual datasets by using district numbers for district-level information and school names for school-related data. Additionally, we incorporated information on after-school programs to enhance the practical utility of the dashboard. To provide a spatial context, we acquired geometrical data for individual districts and school location points. 

Leveraging this data, we extracted longitudes and latitudes, allowing us to precisely map and visualize the geographical distribution of districts and school locations in our dashboard. This integration of diverse datasets and geographical information enriches the depth and accuracy of our analytical platform.

In our district dashboard, we first distinguished each individual district with a unique color on a map to provide a visual representation of their geographical distribution. Subsequently, we organized various sheets to present diverse forms of data, ranging from the overall enrollment of males and females to attendance rates and demographic breakdowns for each grade within the districts. 

To effectively communicate this information, we employed a variety of visualization tools, including regular text tables, bar graphs, and line graphs. One notable feature is a table designed with a spectrum of hues, reflecting the percentage distribution of a specific grade within each district. 

This color-coded representation offers an intuitive and quick understanding of the grade distribution across districts. By employing these different visualization techniques, our district dashboard aims to provide a comprehensive and accessible overview of key educational metrics for each district.

![image](https://github.com/jubuyer/nyc-public-school-dashboard/assets/66185881/58345d07-f4c5-48e2-8b34-50a28f6d80a9)

For our school level dashboard, we utilized the location data of individual schools and created a filter that only lets one school be displayed at once, but the user can select any of them whenever they so wish to. On that same map, we created another Marks layer that included the after school programs, but they’re filtered if they’re a certain “radius” distance away (in miles), from the currently selected school. The way we implemented the was to use the DISTANCE() function in Tableau, where it accepts parameters in the form of 
 `DISTANCE(MAKEPOINT(latitude, longitude), MAKEPOINT(latitude, longitude), ‘unit’)`

Which returns the distance between the two points in space. We utilized each after school program’s individual latitude and longitude, and the currently selected school’s, to get the distance between the two locations. Once we got that, we used a Radius parameter that the user can freely change between 1 and 10 to view any programs near their school, should they want their child to do extracurriculars. The data we used included their addresses and phone numbers, which parents can keep note of to call them to find out if their child might be interested in being there.

In our final dashboard, we emphasized the pivotal role of socioeconomic factors in shaping educational outcomes. To illustrate this, we crafted a heat map that visually captures the intersection of poverty indices and racial demographics across diverse school zones. Recognizing the significance of school enrollment in shaping the representative population within specific poverty indices, we meticulously incorporated enrollment data into the density representation of each school on the heat map. This integration reveals distinct hot zones, enabling users to draw precise and informed conclusions.



Demographic information for each school is presented alongside the map, providing users with in-depth analytical capabilities for nuanced interpretations. Additionally, we incorporated a supplementary visualization detailing school graduation and dropout rates spanning from 2012 to 2018. To enhance user accessibility and address space constraints, we introduced functionality allowing users to filter data by both ZIP code and school, thereby facilitating access to school demographic information and graduation rates. The extensive filtering options offer users a comprehensive snapshot of the average student success rate, coupled with a breakdown of demographics and economic status in the area at a glance.

![image](https://github.com/jubuyer/nyc-public-school-dashboard/assets/66185881/73c3c9a7-8877-43c6-8c96-8d1571da7797)

