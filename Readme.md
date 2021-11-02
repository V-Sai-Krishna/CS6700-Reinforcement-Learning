# CS6700 Reinforcement Learning
## RL- Grid world
Consider a 10 × 10 gridworld as shown in Figure

![alt text](https://github.com/V-Sai-Krishna/CS6700-Reinforcement-Learning/blob/main/rlgrid.png?raw=true)

State space: Gridworld has 100 distinct states. There is a special absorbing state called ”Goal”. There are other special non-absorbing states called ”sub-goals” that are scattered around the gridworld. All other states are referred to as ”normal” states.

Actions: In each non-terminal state, you can take 4 actions A = {North, East, South, West}, which moves you one cell in the corresponding direction.

Transition model: The model may be stochastic, i.e. for an action a ∈ {North, East, South, West}, the agent moves in the corresponding direction of a with probability of less than 1 and greater than 0 for the other directions. For instance, if you choose ”North” the agent will move one place northward with probability 0.8, while in the other directions it may move with probability 0.2/3. However, transitions that take you off the grid will not result in any change. There are no transitions available from the ”Goal” state.

Rewards: You will receive a reward of −1 for all transitions except the transition to the ”sub- goal” or ”Goal” state. Any transition to the ”Goal” state gives you a reward of +100. Any transition to one of the ”sub-goal” states gives you a reward in the range [+5, +25]. However, this reward can only be received once from each ”sub-goal” state after which it resets into a ”normal” state, i.e. transitioning into it again won’t give you any special reward apart from the −1 transition cost. Also, the number of ”sub-goal” sates lie in the range [4, 8].

Implement the following:

Find optimal values using ANY value iteration algorithm. Note that a faster converging algorithm would be awarded higher marks**. Initialize the value grid J0(s) = 0 and policy grid π0(s) = North, ∀s. Let the discount factor γ = 0.99. (Mention sources/papers if any.) (4 marks)

**Marking scheme: Let us say your algorithm A calculates a value grid JA and the optimal value grid (viz. pre-calculated) is J∗. Then a tolerance δ is calculated as

ε = max |JA(s) − J∗(s)|. s∈S

If this ε < 1e−3, then it is said that your algorithm has converged and the time taken for such a convergence tA is stored. There will be two cut-offs, i.e. a ”faster” time tf and a ”slower” time ts such that tf < ts. If tA < tf, you will be awarded the full 4 marks, else if tA > ts, you'll will be awared 0 marks. If tf < tA <ts, the marks will be linearly interpolated.

Note that δ will not be checked on evaluation for each iteration and only on the final values. Hence, an appropriate stopping criteria would be required. Also the time tA for your algorithm will be calculated on AIcrowd’s server on a specific hardware to ensure fair results. Code may be checked for any malpracties and appropriate actions will be taken under the discretion of the course instructor.

Find the optimal policy and values for each state using policy iteration algorithm. Start with J0(s) = 0  and  π0(s) = North, ∀s. Let the discount factor γ = 0.99. (1.5 marks)

Find the optimal policies for the default grid (in the figure) by now setting γ = 0.999 and for 3 different integer values of the transition reward, i.e. { -1, -5, -10 }. Show the variations in the optimal path visually, starting from the "Start" state for each of these 3 values. (1.5 marks)

