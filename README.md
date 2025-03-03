# NARwhaL
Number-Analyzing Reinforcement Learning model
# Background
This is probably a very efficient reinforcement learning algorithm for its intended use cases (mostly number analyzing for finance-related stuff). I had no access to a computer while making this so I had to compute it myself, which led to me having to derive a lot of strategies that are very fast.
# Process
Sorry if this doesn't make a lot of sense, I'm not great at explaining things. You can look at the Python code as it's probably pretty readable.
- It starts by finding the distance from the input features to the training data features
- Using those values the two closest datapoints from the input point
- (This next part was the hardest to come up with)
- Using function composition, find equations you can use to represent a line between the two points
- Basically: x = input, y = f(x), z = g(y), a = h(z), etc. This is the efficient part.
- You also have to find the value for the independent variable in terms of the dependent variable (e.g. x = (y-b)/m)
- Now input each of the values of the input point into all those equations
- You should have multiple generated points
- Now compute the distance from those points to your original input features
- Choose the closest one. That's your pre-output
- If the estimated reward for that pre-output isn't as high as the two datapoint,
- Average the pre-ouput with the output from the higher datapoint from the original two
- Finally, you have to multiply it by the experimentation factor
- Experimentation factor: (1+((randint(-int(100-avg_reward)/2), int((100-avg_reward)/2)))/1000))
- And you have your value! Calculate the reward after it comes in and add that to the training stuff
