### [Home](index.html)

# Flocking: 
In this project, I created a computer program to model coordinated animal motion such as bird flocks and fish schools. The basic flocking
model consists of three simple steering behaviors which describe how an individual boid maneuvers based on the positions and velocities
its nearby flockmates:
*   Separation: steer to avoid crowding local flockmates
*   Alignment: steer towards the average heading of local flockmates
*   Cohesion: steer to move toward the average position of local flockmates
Each boid has direct access to the whole scene's geometric description, but flocking requires that it reacts only to flockmates within a 
certain small neighborhood around itself. The neighborhood is characterized by a distance (measured from the center of the boid) and an 
angle, measured from the boid's direction of flight. Flockmates outside this local neighborhood are ignored. The neighborhood could be 
considered a model of limited perception (as by fish in murky water) but it is probably more correct to think of it as defining the region 
in which flockmates influence a boids steering. The boids also have a certain steer to avoid obstacles.

## How I approached the project: 
I decided to do this project using pyGame since it was an easy way to implement graphics into it. For the boids, I drew an isosceles
triangle that has its tallest vertex pointing towards the direction the boid is facing. I used an array to store all the boids and another
array to store all the obstacles. I made a class for the boids with four seperate steer functions that alter the direction the boid is facing
All four steers are ran constantly, creating a flocking behaviour.
 
## Reflection on the challenges I faced: 
One the major challenges I faced was implementing the steer for obstacle avoidance. For this, I reused the method I ussed during the
Braitenberg project where there were two sensors and both sides of the boid and whichever sensor was closest to the obstacle, the boid would
steer towards the opposite directions the sensor is at.
![Photo 2](braitenberg-work2.PNG "Work")
