---
layout: archive
title: "About My Research"
permalink: /research/
author_profile: true
redirect_from:
  - /research/
---

{% include base_path %}


<h2>What is ARC?</h2>

![Illustration of ARC](/images/ARC_representation.png){: .align-right width="150px"}
[Abstraction and Reasoning Corpus (ARC)](https://arxiv.org/abs/1911.01547) is a benchmark dataset invented by [François Chollet](https://en.wikipedia.org/wiki/Fran%C3%A7ois_Chollet), to test the intelligence of artificial systems. Each task has averagely 2 - 5 example pairs and a test input. The solvers are to guess the rule that satisfies all the example pairs and apply test input to get the correct answer. Here, the picture on the right is an example ARC task. What grid would be in the "?" according to the rules found within the example pairs?

This task is simple. However, there are various types of tasks and it is not easy for a machine to solve it. It is known that human beings can solve it around 85% of the time, while machines can only solve it around 42%, according to the [ARC-AGI Leaderboard](https://arcprize.org/leaderboard#arc-agi-pub).

Here is one additional note for you if you are interested in solving ARC tasks. Please visit [o2arc.com](https://o2arc.com/). This is a web application created by our lab, where you can see and solve other ARC tasks. You can also create your own tasks!


<h2>System-1 and System-2 Thinking</h2>

Have you ever heard of System-1 and System-2 thinking? 

They are two different ways of thinking. System-1 is fast and subconscious, while System-2 is slow and conscious. Due to the characteristics of the two systems, System-1 thinking produces more intuitive fast responses, while System-2 thinking produces more rational and logical responses. Neither is better or worse, they are just different. The point is humans are able to switch between them flexibly!

Currently, most of the AI systems provide pleasing performance on System-1 thinking. They are good at solving tasks that does not require logical processing. The limitation of current AI systems is well-known with the <b>black box issue</b> of the inference process, and <b>lack of explainability</b>. Moreover, considering LLMs as an AI system, they suffer from <b>hallucination</b>. We can see these issues when they are asked to solve tasks that require logical processing.

ARC is a task that requires System-2 thinking. By setting a short-term goal to solve ARC tasks, I am dedicated to develop a new type of AI systems that are able to do System-2 thinking. I am expecting so-called "a new module" to be plugged into the current AI systems and enable them to do System-2 thinking or further plays a role of left/right brain.

<br>
<hr>
<br>

<h1>Research Motivation</h1>

To achieve the goal of System-2 thinking by solving ARC, I first pondered on how human beings solve ARC tasks. Not only in shallow and intuitive level, but also in deep and logical level by repeatedly asking "WHY" questions to my solution. Eventually, the problem solving process has divided into stages and it became the motivation of my research direction and the background of [Abductive Symbolic Solver on Abstraction and Reasoning Corpus](https://ceur-ws.org/Vol-3819/paper1.pdf).

<h2>Steps of Human Solving ARC</h2>

I defined 6 steps of human solving ARC tasks.

1. Observation
2. Pattern, Change, Difference Recognition
3. Rule Formulation + Adjustment
4. Repeat 

5. Observation (Test)
6. Application

The above process can be described in words as follows: We observe a single grid in the ARC task, then we recognize the patterns. Using the information, we formulate a rule. Then the process repeats until we observe all the grids provided in the example pairs. During the repetition, we may adjust the rule. Finally, we observe the test input and apply the rule appropriately to get the correct answer.

After formulating these steps, I focused on the knowledges we gain during the process and how we synthesize them to conclude the rule. Even though only a few example pairs are provided, humans can formulate the rule that satisfies all the example pairs. This brought me to the idea of abductive reasoning.


<h2>Abductive Reasoning</h2>

Abductive reasoning is a reasoning method to find the most plausible explanation within a limited number of observations. It is similar to inductive reasoning that draws general conclusions from specific instances. However, the difference is that abductive reasoning is under the constraint of limited observations while inductive reasoning is based on a large amount of observations that is enough to generalize a conclusion.

Within tasks that requires object selection, the abductive reasoning process can gain information of object's property and relation which can be used as a constraint to find the most plausible object. Here, the accumulation of the property and relation information is done by so-called symbolic back-propagation.

By preserving the semantic meaning of the knowledges and applying abductive reasoning, this symbolic system appeared to narrow down the conditions for selecting the object in the test input. This architecture achieved a knowledge accumulation within the small number of examples which is the key to solve the task.


<br>
<hr>
<br>

<h1>Research Interests</h1>

Above work is the inital idea of my research, so it may look raw. However, I believe the approach is reasonable and I am dedicated to develop it into a more robust system. The following contents are the research interests that I am currently focusing on and getting ready to be developed.

<details>
<summary><font size="+1"><b>Human Perception and Cognitive Science</b></font></summary>
<div markdown="1">

From the raw data, deciding what to focus and extracting additional information is done by human and we do not even notice it. Currently, the material for the ARC solution is defined by researchers with Domain Specific Languages (DSLs) that is considered specific and not flexible. Depending on how we define the DSL, the coverage of the solution varies. Therefore, I expect preparing the fundamental sources for the DSL starting from the human perception and cognition would be a reasonable direction for system-2 reasoning.

</div>
</details>

<br>
<details>
<summary><font size="+1"><b>Knowledge Representation</b></font></summary>
<div markdown="1">

Until now, in the field of artificial intelligence, information is embedded in the massive size vector and the values get altered and mixed when computation is done. During this process, I think the information is not preserved. Human really likes to classify things and this is why I am approaching with symbolic ways. Not only that, I think each semantic symbols forms a structure and this structure is what we call knowledge. Thus, I am expective that the representation of knowledge may be the key to conquer the system-2 reasoning.

</div>
</details>

<br>
<details>
<summary><font size="+1"><b>Human-like Planning and Decision-Making</b></font></summary>
<div markdown="1">

In solving ARC tasks, we need to make a series of decisions. I was thinking about how humans make decisions. Saying conclusion first, I think humans make decisions based on what they have observed. Suppose, a grid size of 10x10 has changed to 3x3 in the pair. Based on the observations of two different sized grids, humans decide to apply DSL that changes/defines the grid size. Thinking more with examples, it would be too specific however, it is possible to be generalized. I am expecting to find the relationship between the observation and the decision to establish a human-like decision making module.

</div>
</details>


<br>
<details>
<summary><font size="+1"><b>Program Synthesis</b></font></summary>
<div markdown="1">

Solution of ARC tasks is a program. Although most of the research bases on the condition of sequential program. However, I think the human thinking process is not always sequential, rather it is more like a tree/graph sturcutre. Creating a non-sequential program synthesizer would be a reasonable direction to solve ARC tasks.

</div>
</details>