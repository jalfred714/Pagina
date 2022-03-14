---
title: Notes Data visualization
author: Juan Pacheco
date: '2022-03-13'
slug: data viz
categories:
  - Data visualization
tags:
  - Principles
  - design
  - Design thinking
---

# **Effective data visualizations**

![Untitled](DATA%20VIZ%20babc9/Untitled.png)

## **Begin with your story**

Start off by evaluating the type of data you have and go through a series of questions to determine the best visual source:

- **Does your data have only one numeric variable?** If you have data that has one, continuous, numerical variable, then a histogram or density plot are the best methods of plotting your categorical data. Depending on your type of data, a bar chart can even be appropriate in this case.
- **Are there multiple datasets?** For cases dealing with more than one set of data, consider a line or pie chart for accurate representation of your data. A line chart will connect multiple data sets over a single, continuous line, showing how numbers have changed over time. A pie chart is good for dividing a whole into multiple categories or parts.
- **Are you measuring changes over time?** 
A line chart is usually adequate for plotting trends over time. However, when the changes are larger, a bar chart is the better option.
- **Do relationships between the data need to be shown?** 
When you have two variables for one set of data, it is important to point out how one affects the other. Variables that pair well together are best plotted on a scatter plot. However, if there are too many data points, the relationship between variables can be obscured so a heat map can be a better representation in that case./

[From data to Viz | Find the graphic you need](https://www.data-to-viz.com/)

# **Principles of design**

![Untitled](DATA%20VIZ%20babc9/Untitled%201.png)

**1. Balance**

The design of a data visualization is balanced when the key visual elements, like color and shape, are distributed evenly. This doesn’t mean that you need complete symmetry, but your visualization shouldn’t have one side distracting from the other. If your data visualization is balanced, this could mean that the lines used to create the graphics are similar in length on both sides, or that the space between objects is equal. For example, **[this column chart](https://developers.google.com/chart/interactive/docs/gallery/columnchart)**
 (also shown below) is balanced; even though the columns are different heights and the chart isn’t symmetrical, the colors, width, and spacing of the columns keep this data visualization balanced. The colors provide sufficient contrast to each other so that you can pay attention to both the motivation level and the energy level displayed.

![Untitled](DATA%20VIZ%20babc9/Untitled%202.png)

**2. Emphasis:** Your data visualization should have a focal point, so that your audience knows where to concentrate. In other words, your visualizations should emphasize the most important data so that users recognize it first. Using color and value is one effective way to make this happen. By using contrasting colors, you can make certain that graphic elements—and the data shown in those elements—stand out.

For example, you will notice a heat map data visualization below from **[The Pudding’s “Where Slang Comes From"](https://pudding.cool/2017/02/new-slang/)** article. This heat map uses colors and value intensity to emphasize the states where search interest is highest. You can visually identify the increase in the search over time from low interest to high interest. This way, you are able to quickly grasp the key idea being presented without knowing the specific data values.

![Untitled](DATA%20VIZ%20babc9/Untitled%203.png)

**3. Movement:** Movement can refer to the path the viewer’s eye travels as they look at a data visualization, or literal movement created by animations. Movement in data visualization should mimic the way people usually read. You can use lines and colors to pull the viewer’s attention across the page.

For example, notice how the average line in **[this combo chart](https://developers.google.com/chart/interactive/docs/gallery/combochart)** (also shown below) draws your attention from left to right. Even though this example isn’t moving, it still uses the movement principle to guide viewers’ understanding of the data.

![Untitled](DATA%20VIZ%20babc9/Untitled%204.png)

**4. Pattern:** You can use similar shapes and colors to create patterns in your data visualization. This can be useful in a lot of different ways. For example, you can use patterns to highlight similarities between different data sets, or break up a pattern with a unique shape, color, or line to create more emphasis.

In the example below, the different colored categories of **[this stacked column chart](https://developers.google.com/chart/interactive/docs/gallery/barchart)** (also shown below) ****are a consistent pattern that makes it easier to compare book sales by genre in each column. Notice in the chart that the Fantasy & Sci Fi category (royal blue) is increasing over time even as the general category (green) is staying about the same.

![Untitled](DATA%20VIZ%20babc9/Untitled%205.png)

**5. Repetition:** Repeating chart types, shapes, or colors adds to the effectiveness of your visualization. Think about the book sales chart from the previous example: the repetition of the colors helps the audience understand that there are distinct sets of data. You may notice this repetition in all of the examples we have reviewed so far. Take some time to review each of the previous examples and notice the elements that are repeated to create a meaningful visual story.

**6. Proportion:** Proportion is another way that you can demonstrate the importance of certain data. Using various colors and sizes helps demonstrate that you are calling attention to a specific visual over others. If you make one chart in a dashboard larger than the others, then you are calling attention to it. It is important to make sure that each chart accurately reflects and visualizes the relationship among the values in it. In **[this dashboard](https://developers.google.com/chart/interactive/docs/gallery/controls)** (also shown below), the slice sizes and colors of the pie chart compared to the data in the table help make the number of donuts eaten by each person the focal point.

![Untitled](DATA%20VIZ%20babc9/Untitled%206.png)

These first six principles of design are key considerations that you can make while you are creating your data visualization. These next three principles are useful checks once your data visualization is finished. If you have applied the initial six principles thoughtfully, then you will probably recognize these next three principles within your visualizations already.

**7. Rhythm:** This refers to creating a sense of movement or flow in your visualization. Rhythm is closely tied to the movement principle. If your finished design doesn’t successfully create a flow, you might want to rearrange some of the elements to improve the rhythm.

**8. Variety:** Your visualizations should have some variety in the chart types, lines, shapes, colors, and values you use. Variety keeps the audience engaged. But it is good to find balance since too much variety can confuse people. The variety you include should make your dashboards and other visualizations feel interesting and unified.

**9. Unity:** The last principle is unity. This means that your final data visualization should be cohesive. If the visual is disjointed or not well organized, it will be confusing and overwhelming.

Being a data analyst means learning to think in a lot of different ways. These nine principles of design can help guide you as you create effective and interesting visualizations.

![Untitled](DATA%20VIZ%20babc9/Untitled%207.png)

# Design thinking for visualization improvement

Design thinking for data visualization involves five phases:

1. **Empathize:** Thinking about the emotions and needs of the target audience for the data visualization
2. **Define:** Figuring out exactly what your audience needs from the data
3. **Ideate:** Generating ideas for data visualization
4. **Prototype:** Putting visualizations together for testing and feedback
5. **Test:** Showing prototype visualizations to people before stakeholders see them

As interactive dashboards become more popular for data visualization, new importance has been placed on efficiency and user-friendliness. In this reading, you will learn how design thinking can improve an interactive dashboard. As a junior analyst, you wouldn’t be expected to create an interactive dashboard on your own, but you can use design thinking to suggest ways that developers can improve data visualizations and dashboards.

![Untitled](DATA%20VIZ%20babc9/Untitled%208.png)

### **Empathize**

First, empathize by putting yourself in the shoes of a customer who has a checking account with the bank.

- Do the colors and labels make sense in the visualization?
- How easy is it to set or change a budget?
- When you click on a spending category in the donut chart, are the transactions in the category displayed?

What is the main purpose of the data visualization? If you answered that it was to help customers stay within budget or to save money, you are right! Saving money was a top customer need for the dashboard.

### **Define**

Now, imagine that you are helping dashboard designers define other things that customers might want to achieve besides saving money.

What other data visualizations might be needed?

- Track income (in addition to spending)
- Track other spending that doesn’t neatly fit into the set categories (this is sometimes called **discretionary spending**)
- Pay off debt

Can you think of anything else?

### **Ideate**

Next, ideate additional features for the dashboard and share them with the software development team.

- What new data visualizations would help customers?
- Would you recommend bar charts or line charts in addition to the standard donut chart?
- Would you recommend allowing users to create their own (custom) categories?

Can you think of anything else?

### **Prototype**

Finally, developers can prototype the next version of the dashboard with new and improved data visualizations.

### **Test**

Developers can close the cycle by having you (and others) test the prototype before it is sent to stakeholders for review and approval.

## **Key takeaways**

This design thinking example showed how important it is to:

- Understand the needs of users
- Generate new ideas for data visualizations
- Make incremental improvements to data visualizations over time

You can refer to the following articles for more information about design thinking:

- [Three Critical Aspects of Design Thinking for Big Data Solutions](https://dataconomy.com/2019/05/three-critical-aspects-of-design-thinking-for-big-data-solutions/)
- [Data and Design Thinking: Why Use Data in the Design Process?](https://www.enginess.io/insights/data-and-design-thinking)

# Effective data stories

In data analytics, **data storytelling** is communicating the meaning of a dataset with visuals and a narrative that is customized for a particular audience. In data journalism, journalists engage their audience of readers by combining visualizations, narrative, and context into data-driven articles. It turns out that data analysts and data journalists have a lot in common! As a junior data analyst, you might learn a few things about effective storytelling from data journalism. Read further to explore the role and work of a data journalist in telling a good story.

**Note:** This reading refers to an article published in *The New Yorker*. Non-subscribers may access several free articles each month. If you already reached your monthly limit on free articles, bookmark the article and come back to this reading later.

## **Take a tour of a data-driven article**

[Ben Wellington](https://www.newyorker.com/contributors/ben-wellington), a contributing writer for *The New Yorker* and a professor at the Pratt Institute, used New York City’s [open data portal](https://nycopendata.socrata.com/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9?) to track down noise complaints from logged service requests. He analyzed the data to gain a more quantitative understanding of where the noise was coming from and which neighborhoods were the noisiest. Then, he presented his findings in the [Mapping New York's Noisiest Neighborhoods](https://www.newyorker.com/tech/annals-of-technology/mapping-new-york-noise-complaints) article.

First, click the link above to skim the article  and familiarize yourself with the data visualizations. Then, join the bus tour of the data! You will be directed to three visualizations (tour stops) to observe how each visualization helped strengthen the overall storytelling in the article.

### **Tour stop 1: setting context**

Earlier in the training, you learned how context is important to understand data. **Context** is the condition in which something exists or happens. Based on the categorization of noise complaints, the data journalist set the context in the article by defining what people considered to be noise.

In the article, review the [combo table and bar chart](https://media.newyorker.com/photos/590965cfebe912338a3758c4/master/w_1600%2Cc_limit/Wellington-noise-ComplaintCounts.jpg) that categorizes the noise complaints. Evaluate the visualization:

- **How does the visualization help set the context?**
The combo table and bar chart is effective in summarizing the noise categories as percentages of the logged complaints. This helps set the context by answering the question, “what is noise?” Notice that the data journalist created a combo table and bar chart instead of a pie chart. With 11 noise categories, a list with a bar chart showing relative proportions is an elegant representation. A pie chart with 11 slices would have been harder to read.
- **How does the visualization help clarify the data?**
If you add the percentages in the categories in the combo table and bar chart, the total is ninety-eight percent. There is a difference of two percent that can’t be accounted for in the visualization. So, rather than clarifying the data, the visualization actually causes a little confusion. One lesson is to always make sure that your percentages add up correctly. Sometimes rounding decimal places up or down causes percentages to be off so they don’t add up to 100%.
- **Do you notice a data visualization best practice?** 
You learned that a companion table in Tableau shows data in a different way in case some in your audience prefer tables. It appears that the data journalist had the same idea by using a combo table and bar chart.
**Note:** As a refresher, a companion table in Tableau is displayed right next to a visualization. A companion table displays the same data as the visualization, but in a table format. You may replay the [Getting Creative](https://www.coursera.org/learn/visualize-data/lecture/Eytgs/getting-creative) video which includes an example of a companion table.

### **Tour stop 2: analyzing variables**

After setting the context by identifying the noise categories, the data journalist describes his analysis of the noise data. One interesting analysis is the distribution of noise complaints versus the time of day.

In the article, review the [stacked area chart](https://media.newyorker.com/photos/590965cd1c7a8e33fb38d4ac/master/w_1600%2Cc_limit/Wellington-noise-ComplaintsHours.jpg) for the distribution of noise complaints by hour of the day. Evaluate the visualization:

- **How does the visualization perform against the five-second rule?**
Recall that the five-second rule states that you should understand what is being conveyed within the first five seconds of seeing a chart. We are guessing that this visualization performs quite well! The area charts for loud music and barking dogs help the audience understand that more of these types of noise complaints were made during late night and early morning hours (between 10:00 PM and 2:00 AM). Notice also that the color coding in the legend aligns with the colors in the chart. A chart legend normally has the largest category at the top, but the data journalist chose to order the legend so the largest category, “Loud music or party” appears at the bottom instead. How much time do you think this alignment saved readers?
- **How does the visualization help clarify the data?** 
Unlike the visualization from the previous tour stop, this visualization does a better job of clearly showing that all percentages add up to 100%.
- **Do you notice a data visualization best practice?** 
As a best practice, both the x-axis and y-axis should be labeled. But, the data journalist chose to include % or A.M. and P.M. with each tick on an axis. As a result, labeling the x-axis “Time of Day'' and the y-axis “Percentage of Noise Complaints” isn’t required. This demonstrates that a little creativity with labeling can help you achieve a cleaner chart.

### **Tour stop 3: drawing conclusions**

After describing how the data was analyzed, the data journalist shares which neighborhoods are the noisiest using a variety of visualizations: [combo table and bar chart](https://media.newyorker.com/photos/590965ceebe912338a3758c2/master/w_1600%2Cc_limit/Wellington-noise-ComplaintsNeighborhoods.jpg), [density map](https://media.newyorker.com/photos/590965cfc14b3c606c1067b0/master/w_1600%2Cc_limit/Wellington-noise-complete.jpg), and [neighborhood map](https://media.newyorker.com/photos/590965d0ebe912338a3758c8/master/w_1600%2Cc_limit/Wellington-noise-WilliamsburgDetail.jpg).

In the article, review the [neighborhood map](https://media.newyorker.com/photos/590965d0ebe912338a3758c8/master/w_1600%2Cc_limit/Wellington-noise-WilliamsburgDetail.jpg) for how close a noisy neighborhood is to a quiet neighborhood. Evaluate the visualization:

- **How does the visualization help make a point?**
The data journalist observed that one of the noisiest neighborhoods was right next to one of the quietest neighborhoods. The neighborhood map is effective in emphasizing this observation as a dark blue area versus a white area.
- **How does the visualization help clarify the data?** 
The visualization classifies the data by neighborhood and allows the audience to follow along when the journalist focuses specifically on the Williamsburg, East Williamsburg, and North Side/South Side neighborhoods.
- **Do you notice a data visualization best practice?** 
Each neighborhood is directly labeled so a legend isn’t necessary.

## **End of the tour: being inspired**

We hope you enjoyed your tour of a data journalist’s work! May this inspire your data storytelling to be as engaging as possible. For additional information about effective data storytelling, read these articles:

- [What is Data Storytelling?](https://www.nugit.co/what-is-data-storytelling/)
- [The Art of Storytelling in Analytics and Data Science | How to Create Data Stories?](https://www.analyticsvidhya.com/blog/2020/05/art-storytelling-analytics-data-science/)
- [Use Data and Analytics to Tell a Story](https://www.gartner.com/smarterwithgartner/use-data-and-analytics-to-tell-a-story/)
- [Tell a Meaningful Story With Data](https://www.thinkwithgoogle.com/marketing-resources/data-measurement/tell-meaningful-stories-with-data/)