### [Home](index.html)

### [Code](https://github.com/balta-z-r/hexagon-game-react)

# Bridge Pattern:

In this project, I made a bridge pattern of my previous project called Hexagon Game. Instead of only having one mode, I created two more
unique modes to play the game in with the same logic behind all three.

- Flat Mode, the hexagons have a flat top
- Pointy Mode, the hexagons have a pointy top
- 3D Mode, instead of hexagons, there are cubes
  Not only did the visuals change, but also the controls.
  In the 3D mode, I made the player move using his camera, and you can move the camera around using keyboard keys.

## How I approached the project:

I decided to do this project in React since it was a good way to organize all my code and seperate my various types. I also implemented P5
into my code to have the graphics for the game and for the UI I used bootstrap. React comes with a bunch of other npm libraries such as
babel which allows me to use JSX. All these libraries allowed for the creation of my project to be a lot more organized and have the logic
and the three implementations be in their own unique files.

## Reflection on the challenges I faced:

The hardest challenge I faced was getting the camera in P5 to be able to move for the 3D mode. Due to errors with the library, I had to
subtract the coordinates of the player to the coordinates of the cube since I was unable to set the coordinates of the camera to anything
other than (0,0,0). I also implemented a way for the player to be able to change the FOV by scrolling to allow the player to see more of
their environment. For moving the camera around, I had coordinates of to the cube the player was looking at, had the P5 camera point to
those coordinates.

```js
p.camera(
  0,
  0,
  zModifier,
  direction.x * size,
  direction.y * size,
  direction.z * size + Math.floor(zModifier),
  0,
  1,
  0
);
```
