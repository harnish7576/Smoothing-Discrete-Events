# Smoothing-Discrete-Events_Pandas
As a part of the curriculum, course CSCI-720 - Big Data Analytics

## Problem Statement

You will read in data that happens at discrete, specific times. The time is measured in hours. The data starts at 12:01 AM to 1:00 AM on a Sunday early in the morning. The data then each hour of a 10-week semester.

1. Generate a histogram of the data, quantized to the nearest day. ( The quantization size is the width of a bin in a histogram bin. For days, there are 24 hours in a day, so use the sum of 24 data records per bin )

2. Parzen Density Estimation:<br />
Using the number of events that happened for each day of the semester (you just computed that so that you could plot it), you will do Density Estimation.

First you want to normalize the histogram you created before. To normalize the histogram, you divide all of the values by the total number. This gives us an estimate of the probability of an event happening on any given day.

Then, you will smooth those values using a Gaussian filter with the following kernel:<br />
Gaussian Coefficients: [ 0.06 0.12 0.20 0.24 0.20 0.12 0.06 ]

For each day, you estimate the number of events as the number in your normalized histogram on each day, 
plus 0.06 * the fraction of events that happened three days before,<br />
plus 0.12 * the fraction of events that happened two days before,<br />
plus 0.20 * the fraction of events that happened one day before,<br />
plus 0.24 * the fraction of events that happened on that day,<br />
plus 0.20 * the fraction of events that happened the following day,<br /> 
plus 0.12 * the fraction of events that happened two days later,<br />
plus 0.06 * the fraction of events that happened three days later.

Use zeros for the days that are outside of the data range.<br />
This gives an estimate of how many events will happen on any day, smoothed out. It avoids random noise in the data.

Graph your results in a continuous graph.

3. Generate a histogram that shows the most common day of the week for events to happen.

4. Generate a histogram that shows the most common week of the semester for events to happen.

## Results
![results](Results.pdf)







