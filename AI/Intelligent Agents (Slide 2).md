![[2 Intelligent agents.pdf]]

# Agents

An agent is anything that can perceive its **Environment** through **sensors** and acting upon its environment through **actuators** 

![[Pasted image 20250129094338.png]]

---
# Percept & Percept sequence

## Percept
A **percept** refers to the raw input or sensory data that an AI agent receives from its environment at a given moment. This can come from various sources, such as cameras, microphones, sensors, or any other input mechanisms.

## Percept sequence
A **percept sequence** is the complete history of all percepts an agent has received so far. It plays a crucial role in decision-making, as intelligent agents use past percepts along with the current percept to determine their next action.


- The agents choice of action can depend on the entire percept sequence till date
- Thus,  to describe an agent it is necessary to specify the agent’s choice of action for every possible percept sequence

---
# Agent Functions & Agents Program

## Agent Function
 - The **agent function** is a **mathematical** mapping from a **percept sequence** (everything the agent has perceived so far) to an **action**.
 - Represented as:
$$
	f: P* ->A
$$
		where 
		- **P**** is a is the set of all possible percept sequences.
		- A is the set of possible actions.
- Essentially, it defines **how an agent should behave** given its history of percepts.

## **Agents program**

- The **agent program** is the actual **implementation** of the agent function.
- It is **concrete** (coded in some programming language) and runs on the agent’s **hardware/software architecture**.
- The **agent function** is theoretical, whereas the **agent program** is what actually executes in real time.
🔹 **Example:**
- The agent function of a chatbot decides **how** it should respond to user input.
- The agent program is the **Python code** that runs NLP models to generate a response.

🔹 **Example:**
[[2 Intelligent agents.pdf#page=6|2 Intelligent agents, p.6 an example from slides (vacuume cleaner world)]]

---
# **Rationality in AI Agents**

A **rational agent** is one that **always selects the action expected to maximize its performance**, based on the information available.

At any given time, what is considered **rational** depends on four factors:

1. **Performance Measure** → Defines what counts as success.
2. **Prior Knowledge** → What the agent already knows about the environment.
3. **Available Actions** → The set of actions the agent can take.
4. **Percept Sequence** → The sequence of all percepts received so far.

💡 **Key Idea:**  
A rational agent **doesn’t blindly follow rules** but instead makes **decisions that maximize success**, given its knowledge and percepts.
### **Specifying the Task Environment – PEAS Framework**

Before designing an AI agent, we need to **fully specify** its task environment using **PEAS**:

|**Component**|**Description**|**Example (Self-Driving Car)**|
|---|---|---|
|**P** - **Performance Measure**|Defines success criteria|Safety, fuel efficiency, reaching destination on time|
|**E** - **Environment**|The world the agent operates in|Roads, traffic, weather conditions|
|**A** - **Actuators**|The agent’s means of interacting with the environment|Steering wheel, brakes, accelerator|
|**S** - **Sensors**|The agent’s means of perceiving the environment|Cameras, LiDAR, GPS, speedometer|

🔹 **Example – PEAS for a Chatbot**


A **task environment** is the setting in which an AI **agent operates** to achieve a specific goal.

- **Task** → The goal the agent is trying to achieve.
- **Environment** → The part of the real world or a computational system where the agent exists.

For example, a **self-driving car** operates in a **real-world traffic environment**, while a **chess AI** operates in a **virtual chessboard environment**.


## **Types of Task Environments**

AI environments can be classified based on different characteristics:
[[#➡️ **Fully Observable Vs Partially Observable**|➡️ Fully Observable Vs Partially Observable]]
➡️ **Deterministic vs. Stochastic Environments
➡️ **Episodic vs. Sequential Task Environments**
[[#**Dynamic and Static**]]]
### ➡️  **Fully Observable Vs Partially Observable**

![[Pasted image 20250129105710.png]]

#### **1. Fully Observable Environment**

 **Definition**:

- An environment is **fully observable** if an agent’s sensors provide **complete and accurate** information about the environment’s state at all times.
- The agent **does not need to maintain an internal memory** since all necessary information is available in real-time.

 **Characteristics**:

- **No hidden information** → The agent can see the entire state of the environment.
- **Easier to design AI for** → No need for prediction or memory-based reasoning.

 **Examples**:


1. Partially Observable Environment

Definition:

- An environment is partially observable if an agent’s sensors provide limited, noisy, or incomplete information about the current state.
- The agent must use memory or make predictions to compensate for missing information.

Characteristics:

- Some information is hidden → The agent does not have full knowledge of the environment.
- Requires state estimation → The agent may use previous Percept and internal models to infer missing details.

 Examples:



➡️  Deterministic vs. Stochastic Environments

The nature of an environment can either be deterministic or stochastic, based on whether the outcome of an action is predictable or not.

2. Deterministic Environment

Definition:

- An environment is deterministic if the next state is completely determined by the current state and the agent’s action.
- There is no randomness involved, so an agent can fully predict the consequences of its actions.
 Characteristics:

- No uncertainty → The same action always produces the same result.
- Easier to design AI for → Agents can use simple logic and planning.
 Examples:


3. Stochastic Environment

 Definition:

- An environment is stochastic if the next state is not entirely predictable due to random factors or hidden variables.
- The same action may lead to different results depending on chance or unknown influences.

 Characteristics:

- Involves uncertainty → The agent cannot always predict the outcome of an action.
- Requires probabilistic reasoning → AI needs models like Markov Decision Processes (MDPs) to handle uncertainty.

 Examples:


🔹 If an environment is deterministic except for the actions of other agents, it is called strategic         (e.g., Chess or Poker).  
🔹 In chess, the rules are fixed, but the opponent’s moves introduce unpredictability.  
🔹 In poker, randomness exists due to both opponent behavior and card shuffling.





➡️  Episodic vs. Sequential Task Environments

In task environments, the nature of the agent's experience determines how decisions are made, and these can be categorized into episodic and sequential environments.

4. Episodic Task Environment
 Definition:  
    In episodic environments, the agent’s experience is divided into atomic episodes. Each episode is independent, meaning the current action only depends on the current episode and not on past episodes.
 Action Dependence:  
    The agent only needs to focus on the current state (episode), and past episodes have no effect on future decisions.
    
 Examples:
    
 Classification tasks (e.g., identifying defective bottles)
    - Vacuum cleaner agent: Each cleaning task is independent (one room is cleaned without considering the previous one).
    
Illustration:
    
    P1 → A1
    P2 → A2
    P3 → A3
    P4 → A4
    P5 → A5    
Here, each bottle (P1, P2, etc.) is independently checked for defects (A1, A2, etc.).
    



5. Sequential Task Environment

- Definition:  
    In sequential environments, the agent’s decisions are dependent on previous actions. Each decision can affect future decisions, meaning that the current action has long-term consequences.
    
- Action Dependence:  
    The agent needs to consider future consequences while deciding its next action, as the decision could influence future actions and outcomes.
    
- Examples:
    
    - Chess: One move (e.g., moving a pawn) affects the entire game and the strategy for the next move.
    - Taxi driving agent: The agent’s current route affects its future decisions (such as taking a shortcut or avoiding traffic).
- Characteristics:    
    - Complexity: More complex because the agent must plan and think ahead.
    - Long-term Impact: Actions must be chosen wisely, keeping the entire sequence of future actions in mind.



Dynamic and Static 

Static Environments
- Definition: The environment remains unchanged while the agent is deliberating.
- Examples:
  - Crossword Puzzle: No external changes affect the puzzle as the agent solves it.
- Characteristics:
  - Easier to manage because the agent does not need to continuously observe the environment.
Dynamic Environments


#### **2. Partially Observable Environment**

**Definition**:

- An environment is **partially observable** if an agent’s sensors provide **limited, noisy, or incomplete** information about the current state.
- The agent must **use memory** or **make predictions** to compensate for missing information.

**Characteristics**:

- **Some information is hidden** → The agent does not have full knowledge of the environment.
- **Requires state estimation** → The agent may use previous [[#Percept]] and internal models to infer missing details.

 **Examples**:

| **Scenario**         | **Why Partially Observable?**                                                                       |
| -------------------- | --------------------------------------------------------------------------------------------------- |
| **Self-Driving Car** | The car can detect nearby objects, but cannot see **around corners** or predict **hidden hazards**. |
| **Vacuum Cleaner**   | It may not know **where dust is** unless it has covered the entire room.                            |


----


### ➡️  **Deterministic vs. Stochastic Environments**

The nature of an environment can either be **deterministic** or **stochastic**, based on whether the outcome of an action is predictable or not.

#### **1. Deterministic Environment**

**Definition**:

- An environment is **deterministic** if the **next state** is **completely determined** by the **current state and the agent’s action**.
- There is **no randomness** involved, so an agent can **fully predict** the consequences of its actions.
 **Characteristics**:

- **No uncertainty** → The same action always produces the same result.
- **Easier to design AI for** → Agents can use simple logic and planning.

 **Examples**:

| **Scenario**                 | **Why Deterministic?**                                                     |
| ---------------------------- | -------------------------------------------------------------------------- |
| **Chess Game**               | The board state changes **exactly** as per the rules, with no randomness.  |
| **Mathematical Computation** | Given the same input, the function will **always** return the same result. |
| **Pathfinding on a Grid**    | If there are no dynamic obstacles, movement is **fully predictable**.      |


#### **2. Stochastic Environment**

 **Definition**:

- An environment is **stochastic** if the next state is **not entirely predictable** due to **random factors** or **hidden variables**.
- The same action may lead to **different results** depending on **chance** or **unknown influences**.

 **Characteristics**:

- **Involves uncertainty** → The agent cannot always predict the outcome of an action.
- **Requires probabilistic reasoning** → AI needs models like **Markov Decision Processes (MDPs)** to handle uncertainty.

 **Examples**:

|**Scenario**|**Why Stochastic?**|
|---|---|
|**Self-Driving Car**|Traffic behavior is unpredictable, accidents can happen randomly.|
|**Taxi Driving**|A taxi driver can’t predict **exactly** how traffic will change.|
|**Interactive English Tutor**|A student’s response **varies** based on their understanding, making outcomes uncertain.|

 **Special Case: Strategic Environments**

🔹 If an environment is **deterministic except for the actions of other agents**, it is called **strategic**         (e.g., Chess or Poker).  
🔹 In **chess**, the rules are fixed, but the **opponent’s moves** introduce unpredictability.  
🔹 In **poker**, randomness exists due to both **opponent behavior** and **card shuffling**.



----


### ➡️  **Episodic vs. Sequential Task Environments**

In **task environments**, the nature of the agent's experience determines how decisions are made, and these can be categorized into **episodic** and **sequential** environments.

#### **1. Episodic Task Environment**

 **Definition**:  
    In **episodic** environments, the agent’s experience is divided into **atomic episodes**. Each episode is **independent**, meaning the current **action** only depends on the current **episode** and not on past episodes.
 **Action Dependence**:  
    The agent only needs to focus on the **current state** (episode), and past episodes have no effect on future decisions.
    
 **Examples**:
    
 **Classification tasks** (e.g., identifying defective bottles)
    - **Vacuum cleaner agent**: Each cleaning task is independent (one room is cleaned without considering the previous one).
    
**Illustration**:
    ```
    P1 → A1
    P2 → A2
    P3 → A3
    P4 → A4
    P5 → A5
    ```
Here, each bottle (P1, P2, etc.) is independently checked for defects (A1, A2, etc.).
    


---

#### **2. Sequential Task Environment**

- **Definition**:  
    In **sequential** environments, the agent’s decisions are dependent on previous actions. **Each decision can affect future decisions**, meaning that the current action has **long-term consequences**.
    
- **Action Dependence**:  
    The agent needs to consider **future consequences** while deciding its next action, as the decision could influence future actions and outcomes.
    
- **Examples**:
    
    - **Chess**: One move (e.g., moving a pawn) affects the entire game and the strategy for the next move.
    - **Taxi driving agent**: The agent’s current route affects its future decisions (such as taking a shortcut or avoiding traffic).
- **Characteristics**:
    
    - **Complexity**: More complex because the agent must plan and think ahead.
    - **Long-term Impact**: Actions must be chosen wisely, keeping the entire sequence of future actions in mind.


---

# **Dynamic and Static** 

### Static Environments
- **Definition**: The environment remains unchanged while the agent is deliberating.
- **Examples**:
  - **Crossword Puzzle**: No external changes affect the puzzle as the agent solves it.
- **Characteristics**:
  - Easier to manage because the agent does not need to continuously observe the environment.
### Dynamic Environments
- **Definition**: The environment can change while the agent is making decisions.
- **Examples**:
  - **Taxi Driving**: Other vehicles are moving while the driving algorithm decides the next action.
- **Characteristics**:
  - More challenging as the agent needs to constantly monitor and respond to changes.

### Semi-Dynamic Environments
- **Definition**: The environment itself doesn’t change with time, but the agent’s performance score may degrade over time.
- **Examples**:
  - **Chess**: The state of the game does not change with time, but if the agent takes too long to make a move, its performance (or perceived performance) may suffer.
- **Characteristics**:
  - Requires the agent to manage time effectively to avoid degradation in performance.

