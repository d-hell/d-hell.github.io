# An Introduction to Neural Networks

Introduction:

This is a walkthrough of a simple neural network written in Python. While this doesn't seem like the AI you're used to seeing with the rising popularity of Large Language Models (LLM,) the fundamental concepts driving this program are remarkably similar. This is because all AI uses algorithms to process data, recognize patterns, and make decisions based on said patterns. In this article, I will be showing how this neural network finds a pattern that fits its data and trains itself over time to improve its prediction accuracy. For a more granualar approach to how LLMs specifically operate, I recommend this article LINK on The Pragmatic Engineer.

I will provide code snippets throughout this article- you can access the full source code in this GitHub repo. LINK

What a Neural Network Does:

This neural network attempts to recognize a pattern in the inputs it is given that maps to the outputs. This data can be found at the start of the module:

```python
inputs = np.array([[0, 1, 0],
                   [0, 1, 1],
                   [0, 0, 0],
                   [1, 0, 0],
                   [1, 1, 1],
                   [1, 0, 1]])
```

```python
outputs = np.array([[0], [0], [0], [1], [1], [1]])
```

This simply means that for each of the bracketed sets given in the input section, we expect to receive the corresponding output from the next list. A good way to visualize this is to put the output values into an "expected values" column:

```terminal
Given Value      Expected Value
[0, 1, 0]    ->        [0]
[0, 1, 1]    ->        [0]
[0, 0, 0]    ->        [0]
[1, 0, 0]    ->        [1]
[1, 1, 1]    ->        [1]
[1, 0, 1]    ->        [1]
```

So what is the pattern the neural network is trying to learn? If you haven't figured it out yet, here it is:

    - If the sum of the three input values is greater than or equal to 2, the output is 1.
    - If the sum is less than 2, the output is 0.


```
 Work in progress
```