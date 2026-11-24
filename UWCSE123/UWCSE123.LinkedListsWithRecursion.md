# Linked Lists w/ Recursion

## Linked Lists Definition

They are either null or a Node w/ another linked list. This is a recursive definition and gives us a hint about how to recursively traverse linked lists. 

The guaranteed base case when using recursion will be when the reference reaches the end of the list or in other words when the node we are referencing is null. This doesn't mean there are not other base cases (such as invalid arguments), but it is helpful to keep in mind the guaranteed inclusion of a null reference. 

Furthermore, when using recursion on a list we need to move a pointer to traverse the list. We do this by creating a public-private method pair. The public method calls the private method and passes in a reference to our list (it can be the front or back depending on how the list is setup). 

## x = change(x)

The structure of our private method is goal-agnostic. 

```java
private ListNode privateMethod(ListNode curr)  {

	if (curr == null)
		return curr;
	
	else if (condition == true)
		return privateMethod(curr.next);
		
	else {
		curr.next = privateMethod(curr.next);
		return curr;
	}
}
```

In the example above, the method is removing a node from the list if it satisfies a certain condition. 

```java
private ListNode privateMethod(ListNode curr)  {

	if (curr == null)
		return curr;
	
	else if (condition == true)
		curr.data = randomData;
		curr.next = privateMethod(curr.next);
		return curr;
		
	else {
		curr.next = privateMethod(curr.next);
		return curr;
	}
}
```

In the example above, the method is modifying the data of a node if it satisfies a certain condition. 

The structure for the private method stayed the same even though we are doing completely different operations to the list. 

The structure is to stop the recursion at our base case, and recursively traverse the list by either making some change for certain conditions or doing nothing. Both of these are captured by x = change(x). Also notice that we are able to change the data of the current node to update the list because it was passed in as curr.next in the previous recursion. Using another method like iteration would not allow you to do this.