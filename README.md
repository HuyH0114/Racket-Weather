

##Authors
Jason Downing 
Huy Huynh
JT Shepple

##Overview
Our general idea for the project is to mimic a 10-day weather forcast where it displays two type of visualizations, one of the visualiazation is showing highs and lows with an image of the condition. The other is a line graph plotting the highs lows, and average temperature of a certain city. The project is split into several parts, first was to retrieve real data into a JSON file and the second part was to create two different visualizations from the retrieved data.

##Screenshot
This was our inital concept and visualization of what we wanted to mimic
<p align="center">
	<img src="https://github.com/oplS16projects/Racket-Weather/blob/master/Example.png">
<p>

This is what we actually have outputted 
<p align="center">
	<img src="https://github.com/HuyH0114/Racket-Weather/blob/master/Racket_Weather_Output_Diagram.PNG">
<p>


##Concepts Demonstrated
Identify the OPL concepts demonstrated in your project. Be brief. A simple list and example is sufficient. 
* **Data abstraction** is used to provide access to the elements of the RSS feed.
* The objects in the OpenGL world are represented with **recursive data structures.**
* **Symbolic language processing techniques** are used in the parser.
* 
 **Basic Recursion** was used to grab the min and max of values from the JSON file

##External Technology and Libraries
Briefly describe the existing technology you utilized, and how you used it. Provide a link to that technology(ies).

##Favorite Scheme Expressions
####Mark (a team member)
Each team member should identify a favorite expression or procedure, written by them, and explain what it does. Why is it your favorite? What OPL philosophy does it embody?
Remember code looks something like this:
```scheme
(map (lambda (x) (foldr compose functions)) data)
```
####Huy Huynh 
This is basically using the plot library and the plot procedure. What is interesting about this was that this plot is actually 
just a list and it uses a mixture of the "lines" procedure and the "points" procedure. Having the plot as a list allowed me to 
overlap the "lines" and "points" procedure into one display or graph. Each of the these procedure takes in two seperate lists where it
has the x and y coordinates needed to plot the diagram. From there the "plot", "lines" and "points" procedure had specific traits that I was able to change such as the label name, color , the x and y labels, the dimenstions of the graph, and its title. This was my favorite because I found it interesting that the procedures in the plot library were not only procedures but also their own objects within those procedures, which were those specific traits that I was able to change. The code itself looks simple but it was interesting to see that there were so much background work that was done. For example for changing the title I was able to use another procedure called string-append and pass it a list and a string I wanted to append. I was able to do all of this inside the "plot" procedure's specific object that it has. 
```scheme
      (plot (list (lines (map vector  city-x-coord list_max)
                           #:color 'red
                           #:label "High"
                           )
                    (points (map vector  city-x-coord  list_max)
                            #:color 'red
                            ))
              #:x-label "Days"
              #:y-label "Temperature in Fahrenheit"
              #:width 1250
              #:height 300
              #:title (string-append name-of-city " 10-Day Forecast Graph"))
```

##Additional Remarks
Anything else you want to say in your report. Can rename or remove this section.

#How to Download and Run
You may want to link to your latest release for easy downloading by people (such as Mark).

Include what file to run, what to do with that file, how to interact with the app when its running, etc. 
