---
layout: default
---


# Game of Life: 
In this project, we were made to recreate Conway's Game of life in our own fashion. 
How the game works is there is a grid with squares that are either alive or dead. 
The alive cells are colored in gray and the dead cells are white. 
Live cells remain live and dead cells remain dead with the following exception: 
*   A dead cell with exactly three live neighbors becomes alive 
*   A live cell with one live neighbor or less becomes dead 
*   A live cell with more than three live neighbors become dead 
## How I approached the project: 
I decided to do this project in Javascript, more specifically using the p5.js library since it was a simple way to integrate graphics. 
I chose to make it so if you click on a square on the grid it changes if state (if click on a live cell, it becomes dead and vice versa). 
I also added some sliders to increase and decrease the size of the grid, along with some buttons to perform basic functions like: 
*   "Next" button ran one iteration of the game 
*   "Play/Stop" button toggled the running of the iterations continuously 
*   "Random" button Randomized the grid, making it 50/50 chance a square in the grid becomes dead or alive 
*   "Clear" button made all the cells dead (white)
 
## Reflection on the challenges I faced: 
One the major challenges I faced was making a deep copy (meaning everything is copied) of the array so I can perform an apply the rules to the grids all at once. 
The reason why this was difficult is because I couldn't use the normal way of creating a copy of an array since the arays in the arrays were still references. 
Therefore, I had to iterate through each of the arrays in the 2D array and copy each of them individually.
```js
newMap = map.map(function (arr) {
    return arr.slice();
  });
```