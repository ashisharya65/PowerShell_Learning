# Functions in PowerShell

- Functions are the most lightweight form of PowerShell command.
- They exist in memory only for the duration of a session. When you exit the session the functions are gone.

## Function Syntax

        function <name> {<statement list>}
   
   
   <img width="425" alt="image" src="https://user-images.githubusercontent.com/56192979/170746766-1722f7bf-64c9-4c30-b9a2-ef84ee817c72.png">

* Here the statement list is also called **Script Block**. 


## Passing arguments using $args

- The ability to pass values into a function is called **parameterizing** the function. In most languages, this means modifying the function to declare the parameters to process.
- In PowerShell, you do not have to declare the parameters as there is a default argument array that contain all the values passed to the function.
- This default array is available in the variable $args.

  Example: 
  
        PS> function Hello {"Hello there $args, how are you?"}
        PS> Hello bob
        
        Output:
        -------
        Hello there bob, how are you?
  




