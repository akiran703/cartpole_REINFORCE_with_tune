# cartpole_REINFORCE_with_tune


I used the cartpole environment to strengthen my knowledge about policy based methods, specifically policy gradient.

The idea behind policy-based methods is that the agent directly learns the policy by approximation without having to use a value function. It presents a probability distribution over actions. Policy based methods trump over value based methods by learning a stochasitic policy where the agent explores the state space without taking the same trajectory(a sequence of what happened i.e state,reward,action over a single episode). It doesnt require to store action value pairs and its able to peform in high-dimensional and continous spaces,autonomus driving as a example. Some disadvantages are that it takes longe to train and it will return a high variance.


For the cartpole env, policy gradient was used, and its a sub class of policy-based methods. The main idea behind policy gradient is that we search directly for optimal policy by peforming gradient ascent on the peformance of the objective function. The policy is modeled with a parameterized function respect to theta,pi of theta(a|s).The objective function(reward function) helps in updating the policy by returning the peformance of the agent given a tragectory and outputs the cumulative reward. The objective function can be written as J(theta) = summation(d^pi(s) * summation(pi of theta(a|s) * Q^pi(s,a)

d^pi(s) is the stationary distribution of markov chain for pi of theta 
Q^pi(s,a) is the value of state and action pair when we follow a policy



The gradient, gradient of theta * J(theta), is hard to compute because it depends on both the action selection, determined by the policy, and the stationary distrubtions of states following the target selection behaviors, indirectly caused by the policy. Most environments are unknown and it becomes difficult to estimate the effect on a state distrubtion given a policy update. Using the the policy gradient theorem, we can reforumlate the objective function into a differentable function that does not involve the differentiation of the state distribution. 
the function went from: Gradient theta * J(theta) ->   E of pi[ Q^pi(s,a) *  Gradient theta  * ln pi of theta(at|st)] 


The specific policy gradient algo that was used is REINFORCE. REINFORCE or monte carlo policy gradient uses episodes to update the policy parameter. The expectation of sample gradient is equal to the actual gradient. 

Steps of REINFORCE

1) initalize policy parameter
2) Generate a episode based on the policy, S0,A0,r0......St,At,rt
3) for t = 1 to T:
   1) calculate the policy
   2) update the policy parameters: theta = theta + alpha * (Gradient theta * J(theta))







