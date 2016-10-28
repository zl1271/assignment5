1. Describe the changes you made to make the game work with Python 3
   I changed line 37 of "adventure.py", from `line = raw_input('> ')` to `line = input('> ')`, because `raw_input` in Python 2 was replaced by `input`.
   The source for this: http://stackoverflow.com/questions/954834/how-do-i-use-raw-input-in-python-3

2. Describe three main techniques that the author used to structure the program.

   - Modular Programming: the game was separated into different modules ("adventure.py", "play.py", "data.py", ect.), each deals with a different problem. For example, "adventure.py" reads input and prints output, while other tasks are done by other modules.
   - Classes: in the file "model.py", different classes were used to organize the codes that are relevant to different parts of the game. For example, the "Room" class (line 38) was used to organized the location, the "Word" class (line 82) was used to organize the commands.
   - Functions: a lot of functions were defined in each of the modules. These functions helped to make the logic of the program clear.

3. Has the author used meaningful names? Give some examples of meaningful names used and what you think they mean. Give some examples of where the author has not used meaningful names. 

   - Meaningful names:
     - In "model.py", the "Room" class, line 46 to 54, the variable names are very meaningful and intuitive: "trying_to_catch_bird" is about if the player is trying to catch the bird, "trying_to_deal_with_snake" is about if the player is trying to deal with the snake, etc.
   - Not very meaningful names:
     - In "data.py", line 74 and 75, there are four variables "m", "n", "mh", "mm", which I don't see obvious meanings.

4. Do the functions used in the code do one thing? Give some examples of functions that only do one thing. Give some examples of functions that do more than one thing.

   - Functions that do one thing:
     - In "model.py", line 118 - 143, each of these functions does one thing (e.g., "destroy" does "self.hide").
   - Functions that do more than one thing:
     - In "adventure.py", the function "loop" (line 19) seems to be doing more than one thing: it parses the description (line 20-25), and loops the game (line 27-40).

5. Do any of the functions cause side effects? If so, which ones?

   Yes.

6. Can you find any repeated code that could be made into a function?

   No.

7. Does the program use exception handling? Can you find any input that causes the program to terminate abnormally? Hint: run the program from the terminal prompt. The invalid input may not be normal text.

   The program has lots of exception handlings.

   After I killed the bird, and input "w", the program terminated, but this only happened once. By chceking the error messages I can't see anything causing this. 

8. Do any of the classes have responsibility over more than one piece of functionality. If so, which ones?

   It looks like the class "Game" in "game.py" does all kinds of things. While all of them are about the game but maybe they can be divided into smaller responsibilities.

9. Are all the classes cohesive? List any that aren’t.

   The class "Game" in "game.py" may not be very cohesive.

10. Describe the author’s approach to commenting the code. Provide examples of good and bad comments that have been used in the code.

   - Good comments:
     - In "adventure.py", line 15, while the code is not clear about what it does, the comment provided good explanation.


   - Bad comments: 
     - In "data.py", line 218, the line of code is being commented out.

11. Provide an example of where vertical formatting has been used to make the code clearer. 

   In "adventure.py", there is an empty line (line 10) after all the importing stuff (line 3-9), followed by line 11 which sets the baud rate, followed by another empty line (12). This clearly shows that setting the baud rate is a separate concept from the importing.

12. Run the tests provided with the program. Do they pass or fail? Do you consider the tests meet the F.I.R.S.T. criteria? Provide details of why they do or do not meet the criteria. 

   After copying everything from /tests, the command `python -m unittest discover` returned the result: Ran 28 tests in 10.618s; OK. So they all pass.

   F.I.R.S.T:

   - Fast: they are fast, all done in about 10 seconds
   - Independent: by looking into the test codes, the 28 tests seemed to be independent, they can be ran individually.
   - Repeatable: I only have one environment to test, but I tested a few times and the results are the same.
   - Self-validating: they are all pass or fail.
   - Timely: obviously I tested long after the code has been developed. But presumably the programmer could have tested the code during development using these tests.

   ​