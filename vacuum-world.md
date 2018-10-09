### [Home](index.html)
### [Code](https://mrprokoala.github.io/vacuum-world)

# Vacuum World: 
For this project, we made a simple app consisting of two cells being both either clean or dirty and a vacuum cleaner able to go from one 
cell to another and clean the cell. The vacuum cleaner had the task to clean both cells in as little steps as possible. It could only 
sense whether or not the cell it was in was clean or dirty.

## How I approached the project: 
I once again decided to use Javascript, more specifically the p5.js library to integrate graphics into my code in a simple manner. For the
vauum cleaner, I created a singleton using the const modifier in javascript which essentially makes a variable unchangable. In the case
objects, this means you can't alter the number of properties of the object or the name of its properties, but you can change the value of
the properties. In my project, I had three buttons:
*   "Next" button ran one step of the vauum cleaner
*   "Restart" button set the map and the vacuum cleaner's location back to it's original (both cells being dirty and the vacuum cleaner to
the right
*   "Randomize" button randomized the value of two cells, dirty or clean
Apart from this, I also added a slight animation to the project. When cleaning, the vacuum cleaner shakes randomly side to side and when
moving from one cell to another, it slides and changes direction to face where it's going.

## Reflection on the challenges I faced: 
The only challenge I really faced was getting the animations to work. For the shaking, I had to mess with angles and provide a limit for
how far the angles of rotation could go. I also had to add a timer so I worked with the p5.js function 'millis()' which provided the number
of milliseconds past since the application started. Using this, I was able to set the animations for only a short and constant period of
time.
```js
if (vacuum.shaking && time + 2000 > millis()) {
        push()
        tint(255, 255 * ((time + 2000 - millis()) / 2000))
        image(dirtImg, 10 + size * vacuum.position, 10, size, size)
        pop()
        push()
        rectMode(CENTER);
        translate(10 + size * vacuum.position + size / 2, 10 + size / 2)
        rotate(random(-45, 45))
        ellipse(0, 0, 10)
        image(vacuumImg, -size / 2, -size / 2, size, size)
        pop()

    } else if ((vacuum.moving === 'Right' || vacuum.moving === 'Left') && time + 2000 > millis()) {
        push()
        let change = -size * ((millis() - time) / 2000)
        translate(10 + size * vacuum.prevPos + size / 2, 10 + size / 2)
        vacuum.moving === 'Right' ? scale(-1.0, 1.0) : scale(1)
        image(vacuumImg, -size / 2 + change, -size / 2, size, size)
        pop()
    } else {
        time = millis()
        vacuum.shaking = false
        vacuum.moving = null
        image(vacuumImg, 10 + size * vacuum.position, 10, size, size)
    }
```
