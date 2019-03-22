# Search_Autocomplete_System

# Project: Design Search Autocomplete System


## Background for our problem

   Autocomplete system was created in 2004 by a guy named Kevin Gibbs, a Stanford grad and a former IBM engineer. When he worked for google,  he created it on a Google shuttle bus. He was interested in URL completion, and he wanted to make users to navigate on web more efficiently, then he spent time working on a URL predictor, and create a tool which is called Google suggest.  As a user typed a URL into a browser, this tool will analyze Google’s enormous web content, and autocomplete the options that will be possibly remained.

## Motivation for our problem 
   Autocomplete system makes life more convenient in many ways.  For searching engine, like Google, users can navigate on website much more efficiently with helps of autocomplete system.  It also applies for input tools.  When you text to someone say “Hello”, probably you just need to type “H”, and word “Hello” will already appear on the screen.  Also, when you log in to some websites, such as Amazon, you can allow browsers to save your account and passwords.  In this case, when you just type a few characters of your account name, the system will automatically fill the remaining. 

## Problem description/Introduction
Autocomplete system is common when we are using search engine for example like google and bing. While we are using google, when we type down key word "i", then website will show some related key words lead by “i” such as "instagram", "indeed", "in n out" and some other words that you might want to look for. The order of these words are typically based on how frequent users searched them. So our want to design an autocomplete system, which returns the  top 3 hottest historical sentences that have the prefix the same as user’s input. 

There will be two functions:

__1.	AutocompleteSystem( a list of strings, a list of ints)__

The AutocompleteSystem function is used to build a database which stores the historical search data.    
The first parameter is a list of string which represents previously typed sentences.    
The second parameter is a list of integers which represents how many times these sentences has been typed.   

__2.	input( a character )__

The parameter of input function is the next character typed by user. The character can only be lower-case letters (‘a’ to ‘z’), blank space (‘ ’) or the special character (‘#’). The previously user input will be recorded . When user add one more character to the sentence, the output will be updated.

__Output of input function__    
input functions returns the top 3 hottest historical sentences that have the prefix the same as user’s input.


### Example:
__Operation: AutocompleteSystem(["i love you", "instagram","ironman",  "i think", "indeed", "in n out","in"], [5,4,4,3,3,2,2])__

In the database:      
“i love you” : 5 times    
"instagram" : 4 times    
"ironman" : 4 times    
"i think" : 3 times    
“indeed” : 3 times    
“in n out” : 2 times    
“in” : 2 times    
Now, the user begins another search    

__Operation: Input(‘i’)__    
__Output: [“i love you”, “instagram”, “ironman”]__

“i love you”, “instagram”, “ironman” are the three hottest sentences with prefix ‘i’

__Operation: Input(‘n’)__    
__Output: ["instagram", "indeed", "in"]__

User add one more character ‘n’
“instagram”, “indeed”, “in n out” are the  three hottest sentences with prefix ‘in’

__Operation: Input(‘ ’)__    
__Output: [“in n out”]__   

“in n out” is the only sentence with prefix “in ”

__Operation: Input(‘a’)__    
__Output: []__

There is no sentence starting with “in  a“

__Operation: Input(‘#’)__    
__Output: []__

The user finishes the search. The sentence “in  a” will be stored into database. The next input will be considered as a new search.
