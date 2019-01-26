# Java-coding-style

# Purpose

# Process

# Style rules

## Variable naming conventions

### Prefer descriptive variable names instead of short variable names 
Describing the meaning of a variable in its name gives more context to its use in code. As rule of thumb, variables with a small scope (meaning, only referenced within several adjacent lines of code) may have shorter names, but variables with large scope should have descriptive names. In other words, constants used throughout a script should have longer and more descriptive names, but temporary variables that are only used on a few adjacent lines may have short names.

Some single letter variable names can be misleading in their visual similarity to numbers. For example, the lower-case “L” can appear similar to the number “1” in some fonts, just as the upper-case “O” can appear similar to the number “0”. Avoid the use of these letters as variable names in particular.

### Underscore prefix for member variables / fields
See the Oracle Java docs for the definition of a member variable (https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)

### Prefix "I" indicates an interface

### Prefix command names with subsystem name: "Subsystem_CommandName"

### Constants in all caps snake case, static and final

TODO: Define snake case

### Camel case variables and functions/methods starting with lower case

### Class names camelcase starting with capital

### Avoid the use of similar names between different variables
Do not use variable names that vary only by letter case, or addition of single character or ending “s”, or other slight variation that may be confusing for readers.

### Use the prefix “is” for logical or boolean variables
To indicate that a variable is of type logical or boolean, use the prefix “is”. The rest of the logical variable name should be phrased so that it approximately reads like an English statement when placed inside an if statement. Avoid using negated boolean naming using words like “not”, as the additional negative statement makes the meaning of the variable harder to understand. Other prefixes that suggest a boolean state like “are” or “has” may be used if they produce a more readable variable name.

## Formatting

### Indentation inside classes, functions, control blocks
 (2 spaces or 4? What is VS code default?)
Spaces or tabs?
Is there an auto format in VS Code?

### Use opening curly brackets on the same line as function or class definitions

### One statement per line 

### White space before and after operators 

### Line width limit 
(100 characters?)
Where is the current line width in VS Code?
Does VS Code have tools to help manage this?

## Comments

### Prefer to document code with style (naming/functions/etc) instead of comments
In most cases, using good naming style for variables and functions should provide context about the purpose and intention behind the code. Comments should only be considered after determining that other means do not provide sufficient context.

“Truth can only be found in one place: the code. Only the code can truly tell you what
it does. It is the only source of truly accurate information. Therefore, though comments are sometimes necessary, we will expend significant energy to minimize them.” 
–Robert C. Martin, “Clean Code”

Use comments only when naming doesn’t express full context

### Avoid commenting-out code
The context and purpose of commented-out code is often unclear for readers. Previous or alternative implementations should be managed with version control instead of with comments. If multiple algorithm options are preferred to be kept in the same version of code, prefer the use of conditional structures to switch between multiple options using a named constant instead of commented code. Make sure that code included in a conditional structure is up to date, or is removed if no longer needed (see the rule “Remove ‘dead’ code”).

### Keep comments current with code functionality and design
Out of date or incorrect comments make code more difficult to understand than if no comments were present. Irrelevant comments should at least be deleted when the corresponding code is updated, if not fully modified to describe new code.

### Write high quality comments (correct spelling and grammar)
Use correct English grammar, spelling, and punctuation. Poor quality comments may make the relevant code more difficult to understand than if there were no comments written at all.

## Functions
5.4.1. Prefer to structure code into small functions

5.5. Design conventions
5.5.1. Periodic functions must not take a long time to run
Avoid while loops for a condition to be met in periodic functions
Avoid sleep functions longer than 2 ms
Prefer to check state in the next cycle
FRC code will throw exception if periodic function not completed in time
5.5.2. Prefer to map inputs with commands instead reading directly in subsystems
Do not bound subsystems directly to other subsystems or driver interface
Should be able to run in either teleop or auton
Allows subsystems to be developed independently
5.5.3. Set motor controller configs on initialization to clear previous state
Call internal function for resetting
5.5.4. Singleton pattern for subsystem classes
Makes sure there is only one copy of values read from robot
5.5.5. Prefer print statements for errors and warnings
5.5.6. Prefer to publish live info to Dashboard instead of print statements
5.5.7. DRY (Don’t Repeat Yourself)
5.5.8. Property accessors start with “get”
Underscore after get?
5.6. Other style rules
5.6.1. Prefer named constants instead of “magic numbers”
A “magic number” in source code is a numerical constant used directly in code that offers no context to the reader for its meaning. 

“The use of unnamed magic numbers in code obscures the developers' intent in choosing that number, increases opportunities for subtle errors … and makes it more difficult for the program to be adapted and extended in the future. Replacing all significant magic numbers with named constants makes programs easier to read, understand and maintain.” Wikipedia: magic number

http://checkstyle.sourceforge.net/config_coding.html#MagicNumber
5.6.2. Consider listing constants for a class in a beginning section
The best place to store constants for a script or project is at the begging of a file or in a dedicated script. Prefer to include constants in these places when possible. Short simulations can have constants listed in the beginning of the code, but bigger projects should have a dedicated script for constants and configuration. This practice makes it easy to find and update any constants used in an algorithm.
5.6.3. Remove “dead” code
Can be found in a conditional statement that never executes.
5.6.4. Require curly brackets for blocks 
http://checkstyle.sourceforge.net/config_blocks.html#NeedBraces

6. Possible future rules
The following rules will be considered for the future, but are not currently considered part of the expectations for stable code.

Encoder reading unit naming
“NU” for native units (raw value read by encoder)
Different kinds of measurements:
Rotary position
Degrees
Linear position
“IN” for inches
Velocity
