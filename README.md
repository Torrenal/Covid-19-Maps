# Plotting maps of Covid 19

Work in progress, please mind the dust.

![US Map, Total Cases](us-cases-small.png)
![US Map, Total Deaths](us-deaths-small.png)  ![US Map, New Deaths](us-new-deaths7-small.png) ![US Map, Doubling Rates](us-doubling-rates-small.png)

## About the map style:
* Short form: They're (mostly) heat maps.  
* Medium form: They're smoothed plots of their specific data sets.
* Long form: The plots are each answering a specific question.  Most typical uses of those tools produce heat maps - for example, if I wanted a proper map of "what kind of iris flower is this?", I'd take the classic iris data set, plot it using this, and then use the colored areas as guides for identifying which flower I had.  "Well, that heigh/width is clearly in the red region, it's setosa.  By rendering thigns as regions rather than points, this declutters the plot, it removes the noise as it were to let you see the signal.  The  naieve coast-finding logic this is using to plot the edges of the US is an application of the same process, and that doesn't present as a heat map.  Using similar logic is the doubling-rates plot.

## How to read the maps:
Notes on how to read the maps are with each plot, basic: Black = no nearby cases, and then typically from dark to light aas counts go up.  The plots working on # of deaths use a variation of the log scale so as not to lose the shape of the data due simply to the scale of the nubmers involved, be they large or small.

Maps in their respective folders will have respective READMEs, consult them for notes on using the maps.

## Defects
Broken borders - The data set has county-level detail, and I don't have a mask of the country's borders to use.  I'm using a naive algorithm to feel out those borders, but it's neither precision nor perfect.  It's doing good work, but a replacement is needed.  Until that happens, if you have your own borders you want to provide, you can strip out the mask I'm using and apply your own.  Details for that are in the README with the maps.

## Todo list:
* Fix holes in the map.  Just having a high res mask of the US using the equirectangular projection would be great, but I may need to just directly mark all the respective regions as "In Bounds" and "Out of Bounds".
* Automate all the things.  I'm lazy, I'd like programs to build and update the maps for me.  That's fine, I'm good at automating things, but like all tasks, automation takes effort, and effort needs time.
* More maps - I've got the maps I wanted to make, but that doesn't mean there arn't other, more useful maps  to make.

## Suggestions
I'm open to suggestions, just open issues with them.  If they include reasonable solutions and add true value, there's a better chance of them being implemented.  That said, time is limited, and I have ultimate goals picked out for this project, I may well turn down ideas if they need a lot of effort and don't bring me towards my goals.

## Data Source
https://github.com/datasets/covid-19

## License

Like their data source, these images are licensed under the Open Data Commons [Public Domain and Dedication License][pddl].

[pddl]: https://www.opendatacommons.org/licenses/pddl/1-0/

Basically, as public domain data went into making these, I consider them public domain.  Mentions, while nice, arn't necessary.
The tools that make them however are my private creations and are not being put in the public domain at this time.

## Older work with the same plot style 
http://www.torrenal.com/Census/ - Some of the content here no longer works - YMMV

http://www.torrenal.com/Travian/

