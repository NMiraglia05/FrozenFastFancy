# FrozenFastFancy
A presentation created to analyze Good Mythical Morning's Frozen vs Fast vs Fancy series.

This project was created to demonstrate data organization and presentation skills. The way the data was gathered was watching episodes of Good Mythical Morning(GMM) and recording the relevant data in a spreadsheet. I intentionally organized the data in a denormalized format to show my ability to model and use a star schema. 

Each food was recorded in the Food Summary table, along with the episode, genre, dish name, the locations utilized for each price level, and the price of each level. 

Each episode was recorded, along with the episode number in GMM's series, the theme of the episode, the date the episode was posted, the days since the previous episode, the views, and the view difference between that episode and the previous episode.

Each genre was recorded, along with the sum price of each host's choices in that genre, and the % difference between their choices.

Each meal was recorded, including the episode it was served in, the sum price of both host's choices, and the % difference between their choices. 

Both the meal and genre summaries were calculated as pivot tables. While this effectively means they are not dimension tables(they're fact tables), part of my goal was to demonstrate usage of star schema, so I treated them as if they are dimension tables. 

The choices table is a calculated table. The way it is created is by bringing in the food summary table with the formula 'Food Summary'!B2:C149,"". The tier chosen by each host is recorded, and the price is recorded using the function =IFERROR((INDEX('Food Summary'!H2:K150,MATCH(C2:C150,'Food Summary'!C2:C150,0),MATCH(D2:D150,'Food Summary'!D1:G1,0))),""). 

The dashboard was built by pulling in data from the excel sheet. 

The summary page includes two pie charts, and 4 cards. Each host has a pie chart and two cards dedicated to them. The pie charts visualize how often each of the hosts pick a given tier. While I personally do not prefer pie charts, people generally prefer them, and they work in this scenario since they break down parts of a whole. The cards summarize total money spent by both host, and the average cost of their meals. The point of this page is to break down their general numbers and answer the 3 most common questions asked about the series- how often do they choose each option, what is the average of their meals, and how much has each host spent.

The price levels page is a bar chart breaking down the average price spent by each host per level. The reason I chose average is that the items presented on the show sometimes involve higher priced items(peanut butter sandwich vs full dish), necessitating an average. Doing this comparison allows comparison of each host's tastes in a given level. 

The meals page records percentage difference in each meal, and the total cost spent on each meal, both in column charts. Percentage differences are recorded on a standard column chart, as that's a better way to understand the difference between genres, and see the difference when Link has a higher preference than Rhett. And, by calculating based on percentages, the table is not effected by one meal having a higher base price than another. The sum of each meal price is recorded in a clustered column chart, which helps to show the difference in each host's choice per meal. This table does not use percentages to show the raw difference- yes it effectively measures the same thing as the other table, however it visualizes how substantial the difference is in some cases. Additionaly, it helps the audience understand the varying base price between different meals, and shows each host's most expensive meal.

The genres page records the percentage difference between the host's choices in each genre. This is relevant since each meal is confined to a specific episode, however some genres are used across multiple episodes. 

The meta analysis table is a combo chart, with a line showing the difference in views between each episode and a bar chart showing the difference in days between each episode. 

The powerpoint uses the visuals created in powerbi to illustrate the observations being made.
