# cartpole_REINFORCE_with_tune


I used the cartpole environment to strengthen my knowledge about policy based methods, specifically policy gradient.

The idea behind policy-based methods is that the agent directly learns the policy by approximation without having to use a value function. It presents a probability distribution over actions. Policy based methods trump over value based methods by learning a stochasitic policy where the agent explores the state space without taking the same trajectory(a sequence of what happened i.e state,reward,action over a single episode). It doesnt require to store action value pairs and its able to peform in high-dimensional and continous spaces,autonomus driving as a example. Some disadvantages are that it takes longe to train and it will return a high variance.


For the cartpole env, I used policy gradient, a sub class of policy-based methods. The main idea behind policy gradient is that we search directly for optimal policy by peforming gradient ascent on the peformance of the objective function. The objective function helps in updating the policy by returning the peformance of the agent given a tragectory and outputs the cumulative reward. 

I used the the policy gradien theorem specifically to reforumlate the objective function into a differentable function that does not involve the differentiation of the state distribution. 
the function went from: J(theta) = 
