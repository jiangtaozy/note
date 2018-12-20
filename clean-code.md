# Names

- Intention-Revealing Names

  The name of a variable, function, or class, should answer all the big questions. It should tell you why it exists, what it does, and how it is used. If a name requires a comment, then the name does not reveal its intent. - Robert C. Martin, Clean Code

      let d; // days since creation
      let daysSinceCreation;

- Use Pronounceable Names

      let genymdhms;
      let generationTimestamp;

- Use Searchable Names

  Single letter-variables and number constants are not easily searched

      const NUMBER_OF_TASKS = 34;

- Class names

  - Avoid prefixing interfaces with I
  - Classes and objects should have noun or noun phrase names

- Method names

  - Methods should have verb or verb phrase names

- Avoid Encodings

  - Hungarian notation

      let phoneString;

# Functions

- Small

  - The first rule of functions is that they should be small.
  - The second ruld of functions is that they should be smaller than that.

- Do Only One Thing

  - Functions
    - should do one thing
    - should do it well
    - should do it only

- Avoid Switch Statements

  - Replace them with configuration
    - maps, properties, xml, etc.

- Function arguments

  - Idealy have no arguments (niladic)
  - One argument (monadic) or two (dyadic) also acceptable
  - Three arguments (triadic) to be avoided where possible
  - Over three (polyadic) should never be used

- Apply Verbs To Key Words

      function write()
      // not as clean as
      function writeField()

- Have No Side Effects

  - Often introduces temporal coupling / function call order dependencies

- Avoid Output Arguments

  - make the output argument a field

- DRY - Don't Repeat Yourself

  - Duplication: the root of all evil in software
  - Difficult to modify / extend
  - Difficult to troubleshoot
