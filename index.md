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
Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
