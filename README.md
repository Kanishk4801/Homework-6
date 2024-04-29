# Extra Credit Homework: Connecting charts and enhancing interactivity
The purpose of this homework is to enhance your skills in linking different visualizations in D3 and adding interactivity with them. By the end of the assignment you will be able to:

 - Manipulate the DOM for data visualization, including creating SVG elements, binding data, and applying scales and axes
 - Add interactivity to your D3 visualizations, such as tooltips and event handlers for mouse events
 - Link data across multiple visualizations, allowing interactions in one visualization to update another

The completed interface for the assignment is shown in the below image:

![final_interface](https://github.com/Kanishk4801/Homework-6/assets/83276964/d2a6a0ce-fc7f-4c46-a9a3-725940a72061)

# Overview
In the given starter code for this assignment, you will see two panels (or boxes), the left panel is for creating a horizontal bar chart of National Parks located in the USA, which will visualize their area (in Acres). The parks will be differentiated (by color) for each state. For example - All parks located in California will be green, those located in Texas will be yellow and so on.

Clicking on a bar for a specific National Park, will in turn create a pie chart based on that park's data on classification of species. The dropdown provided will be populated with 4 options. And the pie chart will divide the species of that park based on the category chosen in the dropdown. Each slice in the pie chart will be based on its percentage of the total value, and will have a different color.

# Data Description 
The dataset we are going to use is "Biodiversity in National Parks: a database of animal and plant species identified in individual national parks" located [here](https://www.kaggle.com/datasets/nationalparkservice/park-biodiversity). This dataset contains two csv files, "parks.csv" and "species.csv". The first csv file will be used to draw the bar chart and the second will be used to create the pie chart. 
For your assignment, you may choose any 20 parks out of the available parks in the dataset. For these parks, create the pie chart classifying species on 4 parameters:

  - Category (Mammal, FIsh, Amphibian, etc)
  - Abundance (Rare, Abundant, Common, etc)
  - Nativeness (Native, Not native, etc)
  - Occurence (Present, Not Present, Not confirmed, etc)

Make sure to include all these 4 parameters in your dropdown to let the user select the pie chart classifier


## To complete the assignment

- Clone this code template to your local machine.
- Start a local server and open the `index.html` page.
- Modify the given code according to the instructions below to achieve the requested interface.
- Commit and push the code back to this repository to submit it.

## Step 0: Starting code

When you first run the page, you should see the empty interface. Add your name and email to the top. It's up to you if you want to write your JavaScript code in a separate JS file, or in the main `index.html` file.

## Step 1: Displaying the bar chart

The first step, is to display a horizontal bar chart plotting areas (in acres) of any 20 national parks given in dataset.

-  Load and preprocess the `parks.csv` data, ensuring park areas are parsed as numerical values for accurate representation.
- Define an SVG canvas in HTML, setting appropriate dimensions and margins to accommodate the bar chart elements and axes.
- Use D3.js to create linear and band scales for the axes, and render each park as a colored rectangle based on its state.
- Implement interactivity with tooltips for detailed data display on hover, and configure click events to link the bar chart with other visual components like the pie chart.
- Choose a categorical d3 color scale for this chart by picking a color scale from [https://github.com/d3/d3-scale-chromatic](https://github.com/d3/d3-scale-chromatic) or creating your own manual one.

![Bar Chart](https://github.com/Kanishk4801/Homework-6/assets/83276964/5b099017-16cf-4229-a7c2-728723c5652d)

## Step 2: Displaying the pie chart

When the user clicks on a bar in the bar chart, draw a Pie chart in the bottom right panel. Your design should look similar to what is in the screenshots. Slices should be sized based on the counts of each species in that category selected in the dropdown.


- Load `species.csv` and filter data based on the selected park and classification from the dropdown to dynamically update the pie chart.
- Calculate pie data from the filtered list using D3's pie layout to show species distribution based on the selected classification.
- Create a color scale with unique colors for each pie slice to visually differentiate between species categories.
- Add a title to your pie chart, with the name of the park whose bar has been clicked on by the user

![Pie Chart](https://github.com/Kanishk4801/Homework-6/assets/83276964/0d5c0413-1715-4f37-a245-fcf1b06640b2)

## Step 3: Add a hover tooltip and legend to the two charts

Finally, add a tooltip to the two charts. When the user hovers over a bar in the bar chart, display the name of the National Park, the state its located in, and its area . When a user hovers over a slice in the Sankey diagram, show an appropriate tooltip to display the count of species in that slice, with the percentage of the chart that slice covers.

The tooltip should be styled similar to the GIF (e.g., white background, black rounded border) and smoothly follow the user's mouse as it moves along the rectangle, and disappear when it's no longer over the rectangle. You'll want to use mouse events to control this functionality (`mouseover`, `mousemove`, `mouseout`).

| 🔍 **Hint:** There are multiple ways to implement tooltips. One option is defining a div that's hidden unless you are hovering over a bar; when that happens, you populate the div with the necessary info, change its display to visible, and move it to the appropriate position on the so it follows the mouse's x/y position on the page. See  this page which for an example: [https://bl.ocks.org/d3noob/97e51c5be17291f79a27705cef827da2](https://bl.ocks.org/d3noob/97e51c5be17291f79a27705cef827da2).

| 🔍 **Hint:** When you mouse over a rectangle, you want to select the currently hovered data point. Inside your `mouseover`/`mousemove`/`mouseout` functions, you can have two parameters like so: `.on('mouseover', function(d, i) { ...})`. Use the Dev Tools to see what the `d` and `i` objects are, and what properties they contain, as a way to figure out how to reference the data item that is currently part of the event (i.e., that corresponds to the rectangle).

Furthermore, add a legend to the two charts, that states clearly what color is assigned to what group. Surround the legend with a black box with rounded edges.
!- 🔍 Since the pie chart will keep updating as the user changes the dropdown, make sure that the legend updates with it as well!


## Extra Credit

You can receive up to two extra credit points for this assignment. (depending on quality  of implementation).

 - Implement linked highlighting between the bar chart and pie chart. For example, when a bar in the bar chart is hovered over, highlight that bar. For example, you could make the border a little thicker and change its stroke color to an easily visible highlight color to do this. Likewise, when a user hovers over a slice in the pie chart, highlight that slice in a similar manner.

- For the legend, when the user hovers over a square, highlight all bars that corresponds to that square.

![Extra Credit](https://github.com/Kanishk4801/Homework-6/assets/83276964/f416fd05-6ccb-4a4d-98b3-3c9e2718e229)

## Grading

This assignment is worth 10 points.

- Step 0 is worth 1 point
- Step 1 is worth 3 points
- Step 2 is worth 3 points
- Step 3 is worth 3 points
- The Extra Credit is worth up to 2 bonus points


