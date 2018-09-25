### [Home](index.html)

# Gridworld: 
In this project, we were made to create a virtual world made out of a grid

## How I approached the project: 
I decided to do this project in Javascript, more specifically using the p5.js library since it was a simple way to integrate graphics. 
 
## Reflection on the challenges I faced: 
The biggest challenge I faced was creating a randomize function that randomized the map in a way the exit was always accessible from any point in the map. I ended up creating several rules for a square in the map to be possibly filled. If the square didn't meet these rules, it would be empty. If it the rules did apply to square, it would've a 50/50 chance of being filled. The rules were:
* The squares surroundings up to two blocks away are empty
* The square is only adjacent to one block
* The square cannot be within a two block radius from the exit
