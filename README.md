# Plotting maps of Covid 19

Work in progress, please mind the dust.

![US Map, raw](us-deaths-small.png)

## About the map style:
* Short form: They're heat maps.  
* Medium form: They're smoothed plots of their specific data sets.
* Long form: They're not what I'd call heat maps, rather they are answering a specific question, and most typical uses of this method yield heat maps.
In the context of an 'active covid cases plot', think of maps as answering the question of "Where are the people who should be aware of or concerned about people in the public being infectious?"
This question is subtly different from "Where are people sick?".  If you look close enough at the county level details you may be able to spot where the two give different answers, but for a basic, broad-picture view, the answers to the two questions are the close enough
that the differences arn't important.  If it's painting an area in red where there arn't infected people, the people in that area are probably concerned about, or directly impacted by the nearest sick populations.

## How to read the maps:
Unless otherwise noted, brighter colors = higher counts, and the scale used behind the scenes is a variation of the log scale.

Holes in the maps?  Sort of?  The data set has county-level detail.  The counties in the western US are large enough and sometimes just oddly shaped enough they're causing the coast-detection logic I'm using to see "ocean".  It's on the 'Must fix' list.  This plot style was developed to deal 
with huge data sets for which normal plotting yielded the "noise" of "too much information".  Having a 'too few data points' is a bit novel for me.

Maps in their respective folders will have respective READMEs, consult them for notes on using the maps.

## Todo list:
* Fix holes in the map.  Just having a high res mask of the US using the equirectangular projection would be great, but I may need to just directly mark those regions as "In Bounds".
* Automate all the things.  I'm lazy, I'd like programs to build and update the maps for me.  That's fine, I'm good at automating things, but like all tasks, automation takes effort, and effort needs time.
* More maps - the point of this project isn't to show the bad, but it had to start somewhere.  More maps is where this project will hit its primary goals.

## Suggestions
I'm open to suggestions, just open issues with them.  If they include reasonable solutions, there's a better chance 
of them being implemented.

## Data Source
https://github.com/datasets/covid-19

## License

These images are licensed under the Open Data Commons [Public Domain and Dedication License][pddl].

[pddl]: https://www.opendatacommons.org/licenses/pddl/1-0/

## Older work with the same plot style 
http://www.torrenal.com/Census/ - Some of the content here no longer works - YMMV

http://www.torrenal.com/Travian/

