# COS425-trafficlight
Starting code for traffic light assignment

In this project we will model the control logic of traffic signal using state machine and produce an implementation using SMC / python. 

Problem description
In this project we will model traffic signals at a single intersection of two, two-way, roads.  To regulate traffic in four directions we will need four coordinated signals.  For simplicity we will refer to these as: North, South, East, and West.  The basic version of each signal will have three lights – red, yellow, green.

Simulate the traffic light using a python GUI that looks something like:
Inline-style: 
![alt text](https://github.com/CovenantCS/COS425-trafficlight/blob/master/image001.png "Trafficlight image")

As a starting point use the trafficlight.py code in this repository.

We will work through several scenarios: American Basic, American Left Arrow, European Basic, and European Left Arrow.  Each will be defined in detail.  We will assume that the system will be driven from state to state purely by a timer.  The timer will provide an event every 5 seconds.  Therefore, each state will be a choice of which lights to put on for a 5 second interval. The traffic signal will run in an infinite loop, such that if it is in the last state defined and receives a timer event it will go to the first state defined.

For each of the scenarios create a working SCM project, including an sm file, python event / action file, python driver file.

Scenario Descriptions:
American Basic:  Red, Yellow, and Green light for each signal.  North and South display Red for 30 seconds, then Green for 25 seconds, and then Yellow for 5 seconds.  East and West display Red if North and South display Green or Yellow.

American Left Arrow:  The North and South signals have Red, Yellow, Green, Green left arrow, Yellow left arrow.  The East and West signals have only Red, Yellow, and Green lights.  The North light displays Green and Green arrow for 10 seconds, then Green and Yellow arrow for 5 seconds, then Green for 25 seconds, then Yellow for 5 seconds, then Red while the rest of the lights cycle.  South has the same intervals as the North, but note it must be Red while North has a Green arrow or Yellow arrow.  East and West have the same lights at the same time.  Their cycle is Green for 25 seconds, Yellow for 5 seconds, and Red the remainder. 

European Basic:  In Europe towards the end of the Red light the driver is warned of an impending change to Green by displaying a Yellow light at the same time that the Red is displayed.  Given four signals each with a Red, Yellow, and Green:  North and South display: Green for 25 seconds, then Yellow for 5 seconds, then Red for 25 seconds, and then Red AND Yellow for 5 seconds.  East and West have the same cycle offset so that if North and South are Green or Yellow then East and West are Red.

European Left Arrow:  This will be the same as the American Left arrow except:  5 seconds before a light goes from Red to Green, a Yellow is displayed with the Red.

You may wish to write up a chart showing the states before you start coding.

Turn in a zip file with a subdirectory for each scenario.  Place a copy of Smc.jar in the root directory.  Place a copy of statemap.py in each subdirectory, in addition to the sm and python files that you have written.  Turn in the zip file.
