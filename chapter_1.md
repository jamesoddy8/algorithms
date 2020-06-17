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

So binary search will take 18 steps - a big difference! In general, for 