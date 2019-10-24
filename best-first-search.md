### [Home](index.html)

### [Code](https://balta-z-r.github.io/best-first-search)

# Best First Search:

In this project, I created a way to find the best path from one point to another. I used three types of searches that operated differently.

- Uniform Cost Search

This type of search finds the path by opening the node that cost the least to open, without regard of the node's location in comparison to the goal. This made it so this search even though it opened more paths than other searches, it would always find the best path.

- Greedy Search

This type of search finds the path by opening the node that is the closest to the goal, which it found by using a heuristic cost. Because this heuristic cost was sometimes not representative of the actual cost, it was possible to get the wrong answer, however, it found answers without needing to open as many nodes as UCS.

- A\* (A Star) Search

This last type of search is a mix of both UCS and Greedy. It calculates the cost by adding up the past cost to the heuristic cost (distance from the node to the goal) and opens the one with the least cost. This makes it so it opens less nodes than UCS and also tends to get the correct path more often that greedy.

## How I approached the project:

I decided to do this project in Javascript, more specifically using the p5.js library since it was a simple way to integrate graphics.
I chose to several functions:

- "Add" Adds a point on the screen with a specific name (data)
- "Link" Links two points with a specified cost
- "Remove" Removes a point

I added buttons for the three searches and had the path found show in the screen.

I also added a template for the Romanian map and an alphabet without links.

To link up two nodes, I added two new properties every new link, 'node#' and 'cost#' to the node.

For example, if I had a point called 'A' with no links and I wanted it to link to a point called 'B' which already had three links, the new properties added to A would be node1 and cost1, node1 would be a reference to point B and cost1 would be the cost to point B. For point B, the properties that would be added would be node4 and cost 4 since the properties node1, node2, and node3 (same for cost) are already being used by other links. The property node4 in point B would contain a reference to point A and cost4 would contain the cost of point B to A (same as the cost to point A to B).

## Reflection on the challenges I faced:

The hardest challenge came at the end when I tried to implement an 8-puzzle solver however wasn't able to. The logic was there however it went on an infinite loop which I was not able to fix in time.

Another difficult part of this project was getting the total cost of the node. To do this, I made it so everytime a node got opened, two new properties would be added to it, one was father and the other one was fatherCost. Father would just be a referenced to the node that preceded the node and fatherCost was just the cost between the node that preceded it and the actual node. This helped get the total cost of a node by looping through all of a node's fatherCost and addding them all up.

Getting the cost of a node by adding up its fatherCosts:

```js
getCost = node => {
  let cost = 0;
  while (node.fatherCost) {
    cost += node.fatherCost;
    node = node.father;
  }
  return cost;
};
```

Adding the properties father and fatherCost to nodes (q is the original node, node is the name of the property that references the node):

```js
let newNode = { ...q[node] };
newNode.father = q;
newNode.fatherCost = q["cost" + node.substring(4)];
queue.push(newNode);
```
