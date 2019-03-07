### [Home](index.html)
### [Code](https://github.com/mrprokoala/guessing-game)

# Guessing Game: 
For this project, we made a game based of our previous knowledge of nodes. We made a binary tree made up of nodes pointing to other nodes. During the game, you're asked a yes or no question and based on your response you're redirected to another question that leads from the original question. My topic of the game was games in general so for example like video games and board games.

## How I approached the project: 
I used JavaScript again to do my app, however, unlike my previous projects, I didn't use p5.js, instead I used React to help build my app. Using React, I was able to use a live database, and for that I used Google's firebase which was free. I stored the starting node in my database as an object and updated it whenever a player added a game the app was not able to guess.

## Reflection on the challenges I faced: 
I face many challenges, my first one was using a database or some sort of data saving mechanism within an app with client and a server side to it. I started trying to do it with a combination of HTML and Node.js, however, ended up using React due to it's easiness to use.I also started using a file to save my binary tree, however, ended up using Google's firebase to save my binary tree. To access firebase within React, I used the axios library.
```js
registeringNewNode = () => {
    const newNode = {
      data: `Is your game a ${this.state.difference}?`,
      left: { ...this.state.currentNode },
      right: {
        data: this.state.newGame
      }
    };
    console.log(
      "https://binary-tree-list.firebaseio.com/tree" +
        this.state.updatedURLString +
        ".json"
    );
    axios
      .put(
        "https://binary-tree-list.firebaseio.com/tree" +
          this.state.updatedURLString +
          ".json",
        newNode
      )
      .then(response => {
        console.log("added succ", response);
      })
      .catch(e => {
        console.log("error", e);
      });
  };
```
