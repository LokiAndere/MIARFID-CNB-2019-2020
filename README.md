# MIARFID-CNB-2019-2020
**CNB project**
**Denis Yura**

*Simple Splicing System*
We did a system with two letters “a” and ”b”. 
A = { a. b }; B = { b }; r = ( b,  1, b, 1 ) 
I = { … } is provided by user. 
Additionally we used a function to check if a list is a subset of another list. 
Everything else we wrote in class “simpleSS”. It does everything automatically. Converts big register to lower register so the class is not sensitive to that. Deletes words from initial strings if they are outside mentioned rules. Give you some information about mistakes and some instructions. 
To solve a task of simple splicing the idea of Parikh projection was used. So for example the initial word “abbaabbbaabbabaa” is converted to “a1b2a2b3a2b2a1b1a2”. And then stored as: 
Beginning = [ 1 ] stating that there is only one option to begin generated word with “a” 
Middle = [ 1, 2 ] because there are only two uniqu emaximum firm subwords “a”, “aa” 
Ending = [ 2 ] because there is only one possibility to end the word 
B list = [ 1, 2, 3] from this we obtain information whether we can duplicate “b” 
The first three can be empty. The B must contain something. Otherwise the word is excluded from initial words. Beginning and end can have more then one value if we have several initial words. 
This example gives us regular expression 
ab( b + ab + aab )*aa 

*Program usage*
One have to create a list of initial words: 
initial = ['aaBBbbaa','abbAa', 'bbaa'] 
It has to be not empty list of strings. 
Send in as an input to a class entity: 
ourClass = simpleSS(initial) 
If needed we can see some inner structure information: 
ourClass.printInfo() 
Then we check the words, whether they can be generated from initial sequence: 
ourClass.checkWord('aBA') 
And get some informative or not answer, it depends on initial list and a word asked. 
The program is built generally. It means it can be widened to more letters. The Parikh projection approach stays the same. 
