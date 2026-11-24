# Exhaustive Search

## Approach
The exhaustive search technique is used to explore the entire solution space. This is done by recursively exploring a discrete solution space. 

Because a given solution space must be discrete, we use a accumulator to keep track where we are in the space. While this algorithm can be used in cyclic graph solution spaces, we will be looking at it in only the case of tree graph solution spaces. 

Here is a example public / private pair method:
```java
public static void someExhaustiveSearch(){
someExhaustiveSearch(someInitialAccumulator);	
}

private static void someExhaustiveSearch(Accumulator someAccumulator) {
	if (condition == true) {
		print(someAccumulator);
	}

	else {
		for (choice : potentialChoices)  {
			if (excludeCondition == true) {
				someExhaustiveSearch(someAccumulator + choice);
			}
		
		}
	
	} 
```
To help understand what the code does, let us look at a specific example of the above code. Let's say we want to print all permutations of the set {0,1,2}. We can make a decision tree graph that shows the recursive logic of the program:
```tikz 
\begin{document}
\begin{tikzpicture}
  [level distance=8mm,level/.style={sibling distance=20mm/#1}]
  \coordinate
    child foreach \x in {0,1,2}
      {child foreach \y in {0,1}
        {child foreach \z in {0}}};
\end{tikzpicture}
\end{document}
```
This is the graph of all the solutions that are program will print. It is easy to see why we use an accumulator here. Our condition for ending the recursion is a string of length 3 and our exclusionCondition is if the string already contains the number we are looping over. In general, when doing exhaustive search this will be general structure of the public / private method. An important thing to note is if we replaced the print statement with a return statement, the exhaustive search would only return one solution. This solution would be the leftmost solution in the tree because we are iterating up. 