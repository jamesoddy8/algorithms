## Introduction to algorithms

An algorithm is a set of instructions for accomplishing a task.

Binary search

Suppose you are searching for a person in the phone book. Their name starts with *K*. You could start at the beginning and keep flipping the pages until you get to the K's. But you're more likely to start at a page in the middle, because you know the K's are going to be near the middle of the book. 

Or suppose you're searching for a word in a dictionary, and it starts with O. Again, you'll start near the middle. 

Now suppose you log on to Facebook. When you do, Facebook has to verify that you have an account on the site. So, it needs to search for your username in its database. Suppose your username is karlmageddon. Facebook could start from the A's and search for you name - but it makes more sense for it to begin somewhere in the middle. 

This is a search problem. And all these cases use the same algorithm to solve the problem: *binary search*. 

Binary search is an algorithm; its input is a sorted list of elements. If an element you're looking for is in that list, binary search returns the position where it's located. Otherwise, binary search returns ```null```. 

Here's an example of how binary search works. I'm thinking of a number between 1 and 100. 
You have to try and guess my number in the fewest tries possible. With every guess, I'll tell you if your guess is too low, too high, or correct. 

Suppose you start guessing like 1, 2, 3, 4 ... This is a simple (stupid) search as with each guess you are eliminating only one number. 

A better technique would be to start with 50. This number is too low, but half of the numbers have subsequently been eliminated. Now you know that 1 to 50 are all too low. 

Nest guess would be in the middle again, so 75. This is too high, but again the number of remaining numbers has been cut down by half. Next is 63, halfway between the two again. 

The next number would be 57 which just so happens to be correct. 

This is binary search. Half of the numbers of any (ordered) sequence are removed every time. 

Whatever number I'm thinking of, you can guess in a maximum of 7 guesses!

Suppose you're looking for a word in the dictionary. The dictionary has 240,000 words. *In the worst case*, how many steps do you think each search will take?

Simple search could take 240,000 steps if the word you were looking for is the very last one in the book. With every step of binary search, you cut the number of words in half until you're left with only one word. 

240k -> 120k -> 60k -> 30k -> 15k -> 7.5k -> 3.75k -> 1875 -> 938 -> 469 -> 235 -> 118 -> 59 -> 30 -> 15 -> 8 -> 4 -> 2 -> 1

18 STEPS in total

So binary search will take 18 steps - a big difference! In general, for any list of *n*, binary search will take log2 *n* steps to run in the worst case, whereas simple search will take *n* steps. 

## Logarithms 

You may not remember what logarithms are, but you probably know what exponentials are. log10 100 is like asking, "How many 10s do we multiply together to get 100? The answer is 2: 10x10. So log10 100 = 2. Logs are the flip of exponentials. 
|Exponentials|Logs|
|---|---|
|10^2 = 100|log10 100 = 2|
|10^3 = 1000|log10 1000 = 3|
|2^3 = 8|log2 8 = 3|
|2^4 = 16|log2 16 = 4|
|2^5 = 32|log2 32 = 5|

When running time in Big O notation, log always means log2. When you search for an element using simple search, in the worst case you might have to look at every single element. So for a list of 8 numbers, you'd have to check 8 numbers at most. For binary search, you have to check log n elements in the worst case. For a list of elements, log 8 == 3, because 2^3 == 8. So for a list of 8 numbers you would haev to check 3 numbers at most. For a list of 1024 elements, log 1024 = 10, because 2^10 == 1024. So for a list of 1024 numbers, you'd have to check 10 numbers at most. 

Binary search only works when your list is in sorted order. For example, the names in a phone book are sorted in alphabetical order, so you can use binary search to look for a name. 

The ```binary_search``` function takes a sorted array and an item. If the item is in the array, the function returns its position. You'll keep track of what part of the array you have to search through. At the beginning, this is the entire array: 
