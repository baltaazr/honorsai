### [Home](index.html)

### [Code](https://github.com/balta-z-r/double-half-moon)

# Double Half Moon:

In this project I created a double half moon using Python, specifically PyGame. I split the moon in half and colored the bottom part blue
and top part red based on a neuron.

## How I approached the project:

I stored the points first in an array with each point having a degree and a radius and then I processed them through a function to get the
X and Y coordinates of the points, and stored their supposed value, 1 for red and 0 for blue.

## Reflection on the challenges I faced:

The hardest part was getting the training to work. I included a parameter in the training called max_iter to check that the training method
doesn't go over a certain amount of epochs and I used recursive to have the function repeat itself.

```js
def train(self, trainingSet, max_iter, cur_iter=1):
      trainingSet = trainingSet.copy()
      error = 0
      for x in trainingSet:
          t = x[2]
          o = -1
          if self.activate(x):
              o = 1
          else:
              o = 0
          error += abs(t-o)
          x = x.copy()
          x.insert(0, -1)
          for i in range(0, len(self.w)):
              self.w[i] += self.learningRate*(t-o)*x[i]
      if(error == 0 or cur_iter >= max_iter):
          return
      else:
          self.train(trainingSet, max_iter, cur_iter+1)
```
