# New Deaths plots

![US Map, New Deaths](../../us-new-deaths7-small.png)

This plot represents the current rate of new deaths across the country.

These plots are of the format: Deaths in past N days / Population

## Notes
* There are some render artifacts where the data points in the source data cover what is almost excessive territory.  This is most noticible in central Nevada, although you can see some minor artifacts in the 2020-04-20 plot by the Colorado/Oklahoma border.  These are a sign that the data points would benefit from being subdivided - some of this is caused by very large counties, some of this is from a few high population counties being mixed mixed among mostly low population couties.  More fine grained data would counter this- the current data is County level.  Having zip-code or city level data would help.
* The source data has death counts that go "backwards".  ie: There were a grand total of 30 people killed to date as of last week, and as of today that total has gone down(?!?) to 14.  Either 16 people came back to life, or there's something off in the data.  Occurrences of people "returning-to-life" are filtered out of this plot.
* Theres a 'previous 7 days' plot and a 'previous 3 days' plot.  Some people are used to seeing things that sumarize 3-day periods, and 7 day periods don't have artifacts from including/excluding different days of the week from one plot to the next.
