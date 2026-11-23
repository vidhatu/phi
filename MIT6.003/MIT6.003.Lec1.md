# Signals and Systems 

Two types of homework to succeed in this course
- problem sets with unambiguous solutions
- engineering design problems with ambiguous solutions but a part of the problem is to make an argument for the solution (use python)

## The 6.003 Abstraction
A system is a bijective function which takes an input signal to an output signal. 

### Example: the mass spring system

Input: Position of the rod.
	Characterize the input to waveform and convert to a signal 

Output: Displacement of the mass
	Result is also a waveform due because of the input

You choose an input and output of interest. 

## Example: Tanks

$$ r_{0}(t) \to r_{1}(t) \to r_{{2}}(t)$$
0,1,2 all describe different tanks and the flow rate of water inside them. They are all related to each other through some physical laws, but we can abstract away these relationships by thinking purely in terms of inputs and outputs. We hide the unnecessary details in the "box". 

```tikz
\usepackage{tikz}
\usepackage{graphicx}
\begin{document}
\begin{tikzpicture}
 \path (0,0) node {$r_0(t)$} 
	-- ++(4,0) node[draw] {tank system} 
	-- ++(4,0) node {$r_2(t)$};
\draw[->] (0.5,0) -- ++(2,0);
\draw[->] (5.25, 0) -- ++(2,0);
 \end{tikzpicture}
 
\end{document}
```


## Why do we do this?
- This approach is widely applicable across a multitude of disciplines.
- Lets us use the tool of abstraction to focus on the information and characteristics relevant to the problem. We can clearly see the flow of information. 
- This approach lets us combine multiple characterizations because there is always one input to one output. For example, in very complex systems we are able them down to chains of signals and systems.
## What are signals
- Mathematical functions
	- independent variable = time
	- dependent variable = any dimensions
	- Doesn't have to a one dimensional function
## Discrete Time (DT) vs Continuous Time (CT) Signals
 - Physical signals are often in continuous time
 - Computational systems generally operate on signals that are functions of discrete time
 - As engineers we need to convert between these two time domains
 - Sampling: converting CT to DT
 - Reconstruction: converting DT to CT

## Mapping
When we map a signal:
$$f(t) = f(t_{1})$$
We can validate the resulting effect on the function output by choosing a couple points on the domain and verifying their outputs. 