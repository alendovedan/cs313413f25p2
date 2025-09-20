COMP 313/413 Project 2 Report Template

TestList.java and TestIterator.java

	TODO also try with a LinkedList - does it make any difference?

		Behaviorally there is no difference in how the iterator works. All test cases pass whether using ArrayList or LinkedList.

TestList.java

	testRemoveObject()

		list.remove(5); // what does this method do?

			Removes the element at index 5.

		list.remove(Integer.valueOf(5)); // what does this one do?

			Removes the first occurrence of value 5.

TestIterator.java

	testRemove()

		i.remove(); // what happens if you use list.remove(77)?

			throws ConcurrentModificationException error.

TestPerformance.java

	State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000)
	to get the running time in milliseconds and how the test running times were recorded.

	SIZE 10
								  5 tests
        testArrayListAddRemove:  394ms 406ms 405ms 404ms 395ms
        testLinkedListAddRemove: 46ms 43ms 42ms 39ms 42ms
		testArrayListAccess:     31ms 28ms 30ms 28ms 32ms
        testLinkedListAccess:    20ms 25ms 22ms 18ms 23ms

	SIZE 100
								  3 tests
        testArrayListAddRemove:  431ms 478ms 414ms
        testLinkedListAddRemove: 41ms 47ms 47ms
		testArrayListAccess:     27ms 30ms 30ms
        testLinkedListAccess:    42ms 43ms 41ms

	SIZE 1000
								  3 tests
        testArrayListAddRemove:  606ms 632ms 615ms
        testLinkedListAddRemove:  43ms 41ms 42ms
		testArrayListAccess:     30ms 29ms 31ms
        testLinkedListAccess:    518ms 502ms 506ms

	SIZE 10000
								  2 tests
        testArrayListAddRemove:  2941ms 3186ms
        testLinkedListAddRemove: 43ms 43ms
		testArrayListAccess:     31ms 32ms
        testLinkedListAccess:    5603ms 5772ms

	listAccess - which type of List is better to use, and why?

		From the results, ArrayList is consistently faster for access operations. For all sizes (10, 100, 1000, 10000), ArrayList access times remain around ~28–32 ms, while LinkedList access becomes drastically slower as the size grows (20–25 ms at SIZE 10 but over 5600 ms at SIZE 10000)

	listAddRemove - which type of List is better to use, and why?

		The data shows LinkedList performs much better than ArrayList for add/remove operations. For example, at SIZE 10000, LinkedList add/remove stays around 43 ms, while ArrayList takes nearly 3000 ms. LinkedList is the better choice for frequent add/remove operations, especially with large lists.