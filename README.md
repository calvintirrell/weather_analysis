# Weather Analysis
Weather data analysis using csv files provided by FiveThiryEight

My first code cell starts off very normally as most projects might for data analytics and visualizations - importing the necessary packages to work with data.

The second code cell is an interesting one.
My initial process for loading all the data was to simply manually write out the code to create a dataframe from a csv file but for all 10 files. Not very efficient.
The code in the second cell is a modified and trimmed down version of a previous Python script I had made and does everything needed in a more programmatic way.
Each line of code in the second cell has a comment above it that explains what the line of code does or is used for in the process of creating a single large dataframe.

The third cell uses 'display()' to see that the code in the second cell successfully created a single large dataframe of all the different csv files of city data.
The fourth cell makes use of '.replace' to change all the previously used city abbreviations in the dataframe to become the full city names.

The fifth cell shows the high level overview of column names and data types as well as the fact that some data is missing.
The sixth cell shows how I found the rows that contain the missing data (represented by 'NaN') and the seventh cell shows how to get rid of the rows missing data.

The eighth cell shows the statistics on the columns with numerical data. The ninth cell shows how I converted the 'date' column to be of 'datetime' data type (used later).
The first visual shows the cities along the x-axis, while the y-axis shows the values from the 'record_min_temp' column. 
The box plot is essentially a visual for the statistics shown by the the use of '.describe()' on the weather_df dataframe which is why I found this visual to be useful.

The next visualization is a count plot and it shows the count (y-axis) of each of the unique temperate values from the 'record_min_temp' (x-axis) column.
Given that this data is for the record minimum temperature - it would be surprising to see the warmest 'cold temperature' was 70 but Phoenix, Houston and L.A. are usually warm.
On the opposite end, I was shocked to see -27 as the coldest value given I have never experienced or heard of such cold temperatures in the U.S.

Using '.value_counts()' combined with '.head()' I'm able to see the five most common temperatures from the 'record_min_temp' column.
It's not particualarly surprsing to see the top five most common temperatures are also the tallest bars on the count plot visualization.
The count plot has many unique values to show. This method shows the data a bit more effectively at a detailed level but the count plot is good for an overview of all the data.

It wouldn't be right to keep using the 'record_min_temp' column and not take a look at the actual lowest temperature.
So using '.groupby()', '.min()', '.head()' we can see the rows of data for the five coldest temperatures, the year those minimum temperatures occurred and what cities as well.
# Only Chicago and Indianapolis are the cities for these five coldest temperatures, with Chicago having three of the five. I will not be visiting either city in the winter.

Lastly, the final three code cells are needed to create the final visualization for this project. I wanted to try something I've never done before and I'm glad it worked out.
Along with the previously imported packages for working with the data, there is one more we need for this visual - 'pandas_alive'.
Next we use '.pivot()' on the weather_df dataframe and specify the index, column(s) and values and then we show what the result of the pivot is on our weather_df dataframe.

The final code cell is where the magic happens for making the final visual. Please read the comments in the last code cell as they have useful information regarding either making your own version of this visual or why I commented out the code in this cell (hint: the code takes a while to run and create the final visual).

Since the final visualization is a GIF file, it won't show up within the Jupyter Notebook along with all the code, comments and other visualizations.
I wanted to create this visual because I think it brings in a sense of time to normally static visuals and helps to really understand the change in data values from the column record minimum temperature. [To see my version of the final visual GIF file please click this link.](https://imgur.com/a/WDdmPEX)
