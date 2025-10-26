# Blood Glucose Data Visualization
For diabetics who use continuous glucose monitors (CGMs), the time spent in the ideal blood glucose range helps lower A1C over time and reduce risk of complications like heart/kidney disease. This program takes in the input of a particular time range, compares it to a CSV containing blood glucose readings from a DexCom CGM, and produces graphical visualizations of cgm data sorted into ranges from low - high. It also compares the generated histogram to a histogram containing the "ideal" amount of CGM data that should fall into each range so users can see long terms trends in their health and rectify detrimental habits.

[histogram_visual]: https://drive.google.com/file/d/1I8FzdrM946Jfa_vobex0oX-zJj06d-TB/view?usp=sharing
[glucose_ranges]: https://diabetesjournals.org/clinical/article/38/5/439/32320/Time-in-Range-How-to-Measure-It-How-to-Report-It
This program was inspired by a [publication][glucose_ranges] by the American Diabetes Association that lists "ideal" blood glucose ranges. The ranges listed are what the program uses to sort data.
Program output example: [graph][histogram_visual]

# How to run the Jupyter notebook as a Webapp
- Using the Voila application, we can display the jupyter notebook in as a webapp.
- After installing Voila, cd~ to the correct directory in the terminal (we can assume the directory is called `cgm` in this case) 
- Run python3 -m venv .venv
- From the ~/cgm directory activate the virtual enironment by executing 'source .venv/bin/activate'
- execute the following on the bash prompt: pip install voila, pip install --force-reinstall jupyter_client, pip install ipykernel, pip install pandas numpy ipywidgets matplotlib

# How the program was made
**Tech Used:** Python, Seaborn, numpy, pandas, pyplot

**Python Usage:**
Python, along with numpy and pandas, are used as the primary ways to extract data from the csv file. By organizing the csv in data frames, the program systematically narrows down the large csv into solely the timestamp and CGM readings. Since this program was created to explore different glucose visualization methods, python code allows for easy reorganization of the data to access different columns to plot.

The grouper function was also used, which allows the python timeseries data to be sorted in a single cluster. From this, the csv data is stored in bins labelled as the inputted blood glucose ranges. The ranges (sourced from the article) are groupings that convey how desirable that particular data point is for a CGM user. Ideal data points should be within the target range of 70 to 180. 

**Graph visualization:**
Seaborn and Matplot are used to generate different types of graphical visualizations. The program takes in the user input of ranges and then can format them into the set graph of either histogram or line chart. 

The line chart was used initially to see all the CGM data present, allowing the user to easily identify potential outliers and events that could prompt a user to consider why that data would be outside the target range. Seaborn provides the line visualization, while pyplot sets up the graph labeling and title.

<img width="2484" height="1098" alt="image" src="https://github.com/user-attachments/assets/af077a1d-06c5-4675-a531-dcc83d5b8b76" />

The histogram chart is generated based on the inputted timeseries, and allows the user to see the percentage of their csv data that fits into each CGM sugar range. Then, another histogram is generated that shows the ideal percentages of CGM data that should be in each range. 

Shown is the histogram with example csv data next to the "ideal" histogram:

<img width="2610" height="1096" alt="image" src="https://github.com/user-attachments/assets/88b66819-f174-4d80-930c-7fd9c74eb47d" />
<img width="2460" height="886" alt="image" src="https://github.com/user-attachments/assets/4837e006-da9f-4393-96c9-0c12c330bb51" />

These graphs next to each other allow for more visual comparison, so users can lower day-to-day stress based on singular fluctuations, and instead focus on the larger trends in their data.

# Growth and Improvement
This project helped me learn how to parse through large, information-rich datasets using python and customize how I wanted the data to be represented. In the future, adding sliders to the program to allow it to change the timeseries points and therefore the graphs in real time would help uses visualize their data more efficiently. 








 
