### [Home](index.html)

### [Code](https://github.com/balta-z-r/lunar-lander)

# Lunar Lander:

I recreated the Lunar Lander game found at http://moonlander.seb.ly/, however, without horizontal movement and a straight surface.
I also made a Genetic Algorithm to produce a rocket with a sequence that will allow it to land on the surface at a relatively low speed.

## How I approached the project:

I decided to do this project in Python using the Pygame library for graphics.
I created my initial batch of Rockets (I made a rocket class) with each having random sequences. These sequences where
arrays with a length of 60,000.
Each element in the sequence represented what the rocket was going to do at that milisecod, with True meaning that the
rocket would boost and False meaning it wouldn't boost.
So the sequence gave the Rocket instrunctions on how to move for a duration of a minute.
Other properties of the Rocket class were altitude and fuel, with the fuel being depleted everytime the rocket boosted.
I would test 100 rockets each session together and after the test was done, I got the top 10 best performing rockets
(meaning when they landed they had the least speed)
I then used the sequences of these 10 rockets to create 90 new ones (I grabbed two rockets from this batch of 10 at random,
then I randomly divided their sequences into two parts and combined the first part of the sequence of the first rocket and
added it to the second part of the sequence of the second rocket).
The remaining 10 rockets I grabbed directly from the previous generation.
Lastly, I took a rocket from the new generation and mutated it by generating an array of noise (values from 0 to 1 at random)
with the same length as the sequence of a rocket and added that noise to the sequence.

```python
# MUTATION
noise = np.random.rand(sequence_size)
for i, n in enumerate(noise):
    if n < 0.5:
        specimina[99].sequence[i] = False
    elif n > 0.90:
        specimina[99].sequence[i] = True
```

I also colored each rocket differently depending on their generation and whether or not they've been mutated or not, with
all Rockets from the same generation sharing the same color and all the mutated rockets being orange.

## Reflection on the challenges I faced:

The hardest part about this project was itiating the random sequences in a truly 'random' way. To make sure it was really
random, I set the probability of getting a True or a False in a sequence for each element random, so it allowed for the
creation of random sequences with a lot of False values and those with a lot of True values.

```python
def generate_sequence(size):
    p_false = np.random.random()
    return np.random.choice(a=[False, True], size=size, p=[p_false, 1 - p_false])
```
