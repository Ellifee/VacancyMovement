# VacancyMovement
The code generates a monte Carlo simulation on vacancy movements in a CIS cristal in C++ within a project in the AIT photovoltaik group.

The simulation starts always with implementing the grid and filling the grid with atoms grid::fillgrid(). 
This happens after a random choice, but restricted by the pattern: 
Cu and In have four Se neighbors and Se has accordingly two Cu and two In neighbors. 
Afterwards the grid is randomly filled with an adjustable amount of vacancies hole::fillholes(), which then make steps. 
One step for one vacancy is made by hole::holestep(). 
This function works in the way, that it chooses randomly a nn from the four nn of the concerning vacancy, 
the transition probability is calculated and with a random generator chosen
if this step will be taken or not according to the probability. 
In the case it does not take this position, a similar query is performed for the other remaining three nn 
otherwise the step is terminated. In this procedure possible boundaries as nn are included.
One cluster step in the context of more vacancies means that all vacancies make a step after each other till a new step starts. 

The amount of steps in a run was normally chosen to be 1000.
Within the basic setups, there is the possibility to apply several testing tools on the simulation,
