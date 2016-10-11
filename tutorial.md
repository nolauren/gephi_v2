## Gephi

### Install with PC
Follow the instructions on the [Gephi Install page.](http://gephi.github.io/users/install/)

### Install with MAC

Download [Gephi](http://gephi.github.io/). 

Open the .dmg file. Drag Gephi into Applications. Launch Gephi.

### Data

Go to [Google Spreadsheets](https://docs.google.com/spreadsheets/d/1zDkN6uR4ODW14jUg5kvPxZ_2gbVqEtS6ZmsRcZ948c8/edit?usp=sharing)
to see our data. The data was taken from
the [Getty Union List of Artist Names.](http://www.getty.edu/research/tools/vocabularies/ulan/) 
Let's take a look. Describe the data. Is it clean? messy? smart? tidy?

Now, download the sheets `nodes` and `edges` as csv files (File > Download as > Comma-seperated value)
to your desktop/

### Import data

Open up Gephi and go to the Data Laboratory. 
File > Import Spreadsheet, and choose `edge.csv`
on your computer. Make sure you selection Edges Table as the table type. Do you see any problems
with doing this?

In order to import, Gephi requires the data to be structured with certain labels. The edge list
needs columns labeled "Source" and "Target". So, rename the column headers either directly in the
Google docs or locally on your machine.

Back in Gephi, go to Data Table > Import Spreadsheet. Choose your `edges.csv`. It should now
import as an edge list. By default, the data will be imported as directed. If we want the data
to be undirected, add "Type" and use "Undirected". 

Go to Data Table > Edges. We see our data. Now, go to Data Table > Nodes. Now, click on Overview
on the top bar. What do you see?

### Labels

To make our graph more readable, we can add labels to the points in the graph. Go back to the
data laboratory and click on "Copy Data to other column" and selection "Last Name". Copy this
value to "Label". Click back on overiew, and select the capital "T" on the bottom toolbar. You
can play around with the bottom toolbar to make the graph more readable. Take a minute to do
so!

### Layout
You can choose an algorithm to help construct a better layout for the graph. Let's take a look at two:

```
Layout -> Fruchterman Reingold -> Run -> Stop
```

It is based on graph drawing. The idea is that the edges want to stay together but the nodes want to
move apart. It is comes out of physics and mimicks the movement of charged particles.  We can also
try:

```
Layout -> Forced Atlas2 -> Run -> Stop
```

Designed for Gephi and popular for visualizations in DH.

The first time you select a layout, options will appear. Some adjustments you might consider are
Gravity, Prevent Overlap and Scaling. To return to this screen, go to Data Laboratory -> Layout
Select the layout you want to adjust and the options screen will appear. Take a moment to play
around with these options.

### Statistics

Modularity is an algorithm designed to help identify groups or communities in a network (i.e.
community detection). We can run it using:

```
Statistics -> Modularity -> Run
```

You'll see a single pop up that doesn't mean much out context. To visualize the algorithm over
selection:

```
Appearance -> Nodes -> Attribute -> Modularity Class
```

Now we have groups of cases (you may need to turn off the labels in order to see them). Now,
let's say I want to know which cases are the most important. We visualize this using the
degree of a node:

```
Appearance -> Nodes -> Attribute -> Degree
```

You can change this to "In-Degree" and "Out-Degree"; notice how it changes the visualization.

Finally, we can have Gephi calculate the centrality of each node. 

```
Appearance -> Nodes -> Attribute -> Eigenvector Centrality
```

### Outliers

Finally, let's consider the case where our data has some outliers that we are not particularly
interested in. This is extra important if you have a lot of data. We might consider removing
certain nodes.

```
Window -> Filters -> Library (double click) -> Topology -> Degree Range
```

A slider will appear. Adjust accordingly.  Select "Filter" to apply. Now, try it with the Ego
Network:

```
Window -> Filters -> Library (double click) -> Topology -> Ego Network
```

This allows us to see the local neighborhood of a given node. Type in `500018666` to select
the neighborhood of Georgia O'Keefe. You can modify the visualization by choosing how many
degrees of seperation to include, and whether you want to add Georgia O'Keefe directly to
the graphic.

#Related Readings

Cordell, Ryan, “Uncovering Reprinting Networks in Nineteenth-Century American Periodicals.” Am Lit Hist (Fall 2015) 27 (3): 417–445. [Viral Texts Project at Northeastern] (http://viraltexts.org/) and [Networks of Viral Texts](http://networks.viraltexts.org/)

Edward Arriaga, Fernando Caparini and Juan Luis Suarez, [“Modeling Afro-Latin American Artistic Representations in Topic Maps: Cuba’s Prominence in Latin American Discourse.”](http://www.digitalhumanities.org/dhq/vol/7/1/000145/000145.html).

Meeks, Elijah and Scott Weingart. [An Introduction to Networks Analysis and Representatin.] (http://emeeks.github.io/networks/)

Moretti, Franco. [Network Theory, Plot Analysis.](https://litlab.stanford.edu/LiteraryLabPamphlet2.pdf)

Weingart, Scott. [“Topic Modeling and Network Analysis.”](http://www.scottbot.net/HIAL/?p=221) The scottbot irregular.

Weingart, Scott. [“Contextualizing networks with maps.”](http://www.scottbot.net/HIAL/?p=1942) The scottbot irregular.
