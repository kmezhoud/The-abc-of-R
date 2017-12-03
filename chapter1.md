---
title       : The abc of R
description : This course in the french version of <a href="https://github.com/datacamp/courses-intro-to-r-beta">The introduction of R</a>
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf




---
## Comment ça marche!

```yaml
type: NormalExercise
key: a7f766d856
lang: r
xp: 100
skills: 1
```

L'interface `DataCamp` est composée de 4 zones: Exercice, Instructions, Script et Console. Les zones Exercice et Instruction sont à lire et à suivre.

Au niveau de la zone Instruction, il est possible d'otenir de l'aide indiqué par une lampe ou bien `Take Hint`.  Mais l'aide n'est pas gratuite. Elle diminue le nombre de point cumulé et qui est indiqué entre parenthèses.

La zone Script est un éditeur de texte pour écrire les lines de commandes R. La zone console c'est là où l'interface va exécuter les commandes écrite dans la zone Script. 

Au niveau de la zone `Script`, nous avons des lines vertes, initiées par des hachtag `#`. Ces lignes ne sont pas lues par R. Ils servent seulement à faciliter la compréhension des scripts. Dans notre cas, l'interpréteur va lire seulement les lignes sans `#`, càd `3 + 4` et va nous interpréter cela comme une caculatrice au niveua de la zone `Console`.

Le output du code R écrit dans la zone `Script` est visualisé dans la `Console` en bas à droite.
Les graphes et le spots sont visualisés en haut à droite à côté de la zone `Script`. Exécuter le commande **demo("graphics")** pour voire quelques plots.
Utiliser les flèchettes pour naviguer sur les graphes générer avec R sur votre fen^être à droite en haut. Noter que vous pouvez élargir votre fenêtre pour avoir une meilleure vue. 

`@instructions`
1. Click **Submit Answer** et regardez au niveau de la console l'exécution du code R: La solution `7` apparait pour la somme de `3` et `4`. A sa forme basique R peut être utiliser comme une calculatrice ou pour générer des plots. Mais en réalité, il peut faire mieux que cela ;-).

`@hint`
Juste cliquer sur le boutton `Submit Answer`

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r eval=FALSE}
# C'est l'éditeur des commandes et la partie en bas est la console R où on exécute les commandes.

# les hashtag sont utilisées pour ajouter des commentaires explicatives des commandes

# Calculer 3 + 4
3 + 4

# Visualiser quelques graphes demonstratives generés par R
# demo("graphics")
```

`@solution`
```{r eval:FALSE}
#Juste cliquer sur le boutton `Submit Answer` pour soummetre la/les commandes

# C'est l'éditeur et la partie en bas est la console 

# Le hashtag est utilisé pour ajouter des commentaires

# Calculer 3 + 4 
3 + 4 

# Visualiser quelques graphes générés par R
# demo("graphics")

```

`@sct`
```{r eval=FALSE}
DM.result <- TRUE
```

--- type:NormalExercise lang:r xp:100 skills:1 key:9d8a3d0b88
## R est une calculatrice

A la limite le language R peut être considérer comme une calculatrice scientifique. Considère les opérations arithmétiques suivantes:

- Addition: `+`
- Subtraction: `-`
- Multiplication: `*`
- Division: `/`
- Exponentiation: `^`
- Modulo: `%%`

Les deux dernières nécéssites une explication:
- L'opérateur `^` relève le nombre de sa gauche à la puissance du nombre à sa droite: par exemple `3^2` est égale à 9.
- Le modulo retourne le reste de la division du numbre à sa gauche par le nombre de sa droite. Par exemple, 5 modulo 3 `5 %% 3` est égale à 2.

*** =instructions
- Taper `2^5` dans la zone script pour calculer 2 à la puissance 5.
- Taper `28 %% 6` pour calculer le 28 modulo 6.
- Cliquer **Submit Answer** et observer le outout à la console.

*** =hint
Un autre exemple de l'opérateur modulo: `9 %% 2` est égale à `1`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Addition
5 + 5 

# Subtraction
5 - 5 

# Multiplication
3 * 5

 # Division
(5 + 5) / 2 

# Exponentiation


# Modulo

```

*** =solution
```{r}
# Addition
5 + 5 

# Subtraction
5 - 5 

# Multiplication
3 * 5

 # Division
(5 + 5) / 2 

# Exponentiation
2 ^ 5

# Modulo
28 %% 6
```

*** =sct
```{r}
msg <- "Ne pas effacer les exemples codés pour vous!"
test_output_contains("5 + 5", incorrect_msg = msg)
test_output_contains("5 - 5", incorrect_msg = msg)
test_output_contains("3 * 5", incorrect_msg = msg)
test_output_contains("(5 + 5)/2", incorrect_msg = msg)
test_output_contains("2^5", incorrect_msg = "Regarder précisément comment est écrit l'opérateur exponentiel. Liser les instructions avec prudence.")
test_output_contains("28 %% 6", incorrect_msg = "Regarder précisément comment est écrit l'opérateur modulo. Liser les instructions avec prudence.")
success_msg("Nice one!")
```
--- type:MultipleChoiceExercise xp:50 skills:1 key:9d8819fb2e
## R's pros and cons

As Filip explained in the video, there are things that make R the awesome and immensely popular language that it is today. On the other hand, there are also aspects about R that are less attractive. Which of the following statements are true regarding this statistical programming language developed by Ihaka and Gentleman in the nineties?

1. As opposed to SAS and SPSS, R is completely open-source.
2. R is open-source, but it's hard to share your code with others since R uses a command-line interface.
3. It typically takes a long time for new and updated R packages to be released and made available to the public.
4. R is easy to use, but this comes at the cost of limited graphical abilities.
5. R works well with large data sets, if the code is properly written and the data fits into the working memory. 

*** =instructions
- statements (1) and (2) are correct; the others are false.
- statements (1) and (4) are correct; the others are false.
- statements (1) and (5) are correct; the others are false.
- statements (2) and (4) are correct; the others are false.
- statements (3) and (5) are correct; the others are false.

*** =hint
Remember that your data has to fit in the working memory for R to be able to process it.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sct
```{r}
msg1 = "Remember that the fact that R uses a command-line interface, does not make it hard to share code. On the contrary, sharing your results becomes very straightforward because you can easily share R scripts."
msg2 = "R is the perfect tool for creating neat and insightful visualizations. Try again."
msg3 = "Great! Head over to the next exercise and get your hands dirty!"
msg4 = "R uses a command-line interface, which makes it very easy to share one's code. Also, R is very suitable for creating visualizations. Try again."
msg5 = "It's fairly straightforward to write, maintain and share R packages. Try again."
test_mc(3, feedback_msgs = c(msg1, msg2, msg3, msg4, msg5))
```


--- type:NormalExercise lang:r xp:100 skills:1 key:6b6fb4974c
## Variable assignment (1)

A variable allows you store a value or an object in R. You can then later use this variable's name to easily access the value or the object that is stored within this variable. You use `<-` to assign a variable:

```
my_variable <- 4
```

*** =instructions
Complete the code in the editor such that it assigns the value 42 to the variable `x` in the editor. Click 'Submit Answer'. Notice that when you ask R to print `x`, the value 42 appears.

*** =hint
Look at how the value 4 was assigned to `my_variable` in the exercise's assignment. Do the exact same thing in the editor, but now assign 42 to the variable `x`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign the value 42 to x
x <- 

# Print out the value of the variable x
x
```

*** =solution
```{r}
# Assign the value 42 to x
x <- 42

# Print out the value of the variable x
x
```

*** =sct
```{r}
test_error()
test_object("x", 
            undefined_msg = "Make sure to define a variable <code>x</code>.",
            incorrect_msg = "Make sure that you assign the correct value to <code>x</code>.") 
success_msg("Good job! Notice that R does not print the value of a variable to the console when you do the assignment. <code>x <- 42</code> did not generate any output, because R assumes that you will be needing this variable in the future. Otherwise you wouldn't have stored the value in a variable in the first place, right? Proceed to the next exercise!")
```




--- type:NormalExercise xp:100 skills:1 key:a5b8028834
## Variable assignment (2)

Suppose you have a fruit basket with five apples. You want to store the number of apples in a variable with the name `my_apples`. 

*** =instructions
- Using `<-`, assign the value 5 to `my_apples` below the first comment.
- Type `my_apples` below the second comment. This will print out the value of `my_apples`.
- After clicking _Submit Answer_, have a look at the console: the number 5 is printed, so R now links the variable `my_apples` to the value 5.

*** =hint
Remember that if you want to assign a number or an object to a variable in R, you can make use of the assignment operator `<-`. Alternatively, you can use `=`, but `<-` is widely preferred in the R community.

*** =pre_exercise_code
```{r}
```

*** =sample_code
```{r}
# Assign the value 5 to the variable called my_apples


# Print out the value of the variable my_apples

```

*** =solution
```{r}
# Assign the value 5 to the variable called my_apples
my_apples <- 5

# Print out the value of the variable my_apples
my_apples
```

*** =sct
```{r}
test_object("my_apples", incorrect_msg = "Have you correctly assigned 5 to `my_apples`? Write `my_apples <- 5` on a new line in the script.")
test_output_contains("my_apples", incorrect_msg = "Have you explicitly told R to print out the `my_apples` variable to the console? Simply type `my_apples` on a new line.")
success_msg("Great! You could also use `=` for variable assignment, but `<-` is typically preferred.")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:a0cb1bea96
## Variable assignment (3)

Every tasty fruit basket needs oranges, so you decide to add six oranges. You decide to create the variable `my_oranges` and assign the value 6 to it. Next, you want to calculate how many pieces of fruit you have in total. Since you have given meaningful names to these values, you can now code this in a clear way:

```
my_apples + my_oranges
```

*** =instructions
- Assign to `my_oranges` the value 6.
- Add the variables `my_apples` and `my_oranges` and have R simply print the result.
- Combine the variables `my_apples` and `my_oranges` into a new variable `my_fruit`, which is the total amount of fruits in your fruit basket.

*** =hint
`my_fruit` is just the sum of `my_apples` and `my_oranges`. You can use the `+` operator to sum the two and `<-` to assign that value to the variable `my_fruit`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign 5 to my_apples
my_apples <- 5

# Assign 6 to my_oranges


# Add my_apples and my_oranges: print the result


# Add my_apples and my_oranges: assign to my_fruit

```

*** =solution
```{r}
# Assign 5 to my_apples
my_apples <- 5

# Assign 6 to my_oranges
my_oranges <- 6

# Add my_apples and my_oranges: print the result
my_apples + my_oranges

# Add my_apples and my_oranges: assign to my_fruit
my_fruit <- my_apples + my_oranges
```

*** =sct
```{r}
test_object("my_apples", incorrect_msg = "Do not change the assignment of the `my_apples` variable!")
test_object("my_oranges")
test_output_contains("my_apples + my_oranges",
                     incorrect_msg = "The output does not contain the result of adding `my_apples` and `my_oranges` (second instruction). Try again.")
test_object("my_fruit")
success_msg("Nice one! The great advantage of doing calculations with variables is reusability. If you just change `my_apples` to equal 12 instead of 5 and rerun the script, `my_fruit` will automatically update as well.")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:6192f64167
## The workspace

If you assign a value to a variable, this variable is stored in the workspace. It's the place where all user-defined variables live. The command [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls) lists the contents of this workspace. 

```
a <- 1
b <- 2
ls()
```

The first two lines create the variables `a` and `b`. Calling [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls) now shows you that `a` and `b` are in the workspace. 

You can also remove variables from the workspace. You do this with [`rm()`](http://www.rdocumentation.org/packages/base/functions/rm). `rm(a)`, for example, would remove `a` from the workspace again. `rm(list = ls())`, which is used in the beginning of your script, clears everything from the workspace.

*** =instructions
- Create a variable, `horses`, equal to 3, and a variable `dogs`, equal to 7.
- List the contents of your workspace with [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls) to see that indeed, these two variables are in there.

*** =hint
All you need is a combination of [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls) and [`rm()`](http://www.rdocumentation.org/packages/base/functions/rm) at the right time. Give it a try and let the feedback messages guide you.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Clear the entire workspace
rm(list = ls())

# Create the variables horses and dogs


# List the contents of your workspace


```

*** =solution
```{r}
# Clear the entire workspace
rm(list = ls())

# Create the variables horses and dogs
horses <- 3
dogs <- 7

# Inspect the contents of the workspace again
ls()
```

*** =sct
```{r}
test_student_typed("rm(list = ls())", not_typed_msg = "Do not remove the line `rm(list = ls())`.")
test_object("horses")
test_object("dogs")
test_output_contains('c("dogs", "horses")',
                     incorrect_msg = "Make sure to inspect the objects in your workspace after creating `horses` and `dogs`.")
success_msg("Awesome! You can now build up and inspect your workspace, great!")
```


--- type:VideoExercise lang:r xp:50 skills:1 key:9f9019501e
## Basic Data Types

*** =video_link
//player.vimeo.com/video/138173888

*** =video_hls
//videos.datacamp.com/transcoded/732_intro_to_r/v1/hls-ch1_2.master.m3u8



--- type:NormalExercise lang:r xp:100 skills:1 key:1866cdd202
## Discover Basic Data Types

To get started, here are some of R's most basic data types:

- Decimal values like `4.5` are called **numerics**.
- Natural numbers like `4L` are called **integers**. Integers are also numerics.
- Boolean values (`TRUE` or `FALSE`) are called **logical**. Capital letters are important here; `true` and `false` are not valid.
- Text (or string) values are called **characters**.

Note how the quotation marks on the right indicate that `"some text"` is of type character.

*** =instructions
Change the value of the:

- `my_numeric` variable to `42`.
- `my_character` variable to `"forty-two"`. Note that the quotation marks indicate that `"forty-two"` is a character.
- `my_logical` variable to `FALSE`.

*** =hint 
Replace the values in the script with the values that are provided in the exercise.
```
my_numeric <- 42
```
assigns the value 42 to the variable `my_numeric`. 

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# What is the answer to the universe?
my_numeric <- 42.5

# The quotation marks indicate that the variable is of type character
my_character <- "some text"

# Change the value of my_logical
my_logical <- TRUE
```

*** =solution
```{r}
# What is the answer to the universe?
my_numeric <- 42

# The quotation marks indicate that the variable is of type character
my_character <- "forty-two"

# Change the value of my_logical
my_logical <- FALSE
```

*** =sct
```{r}
test_object("my_numeric", 
            incorrect_msg = "Make sure that you assign the correct value to `my_numeric.`")
test_object("my_character",
            incorrect_msg = paste("Make sure that you assign the correct value to `my_character`.",
                                  "Do not forget the quotes and beware of capitalization! R is case sensitive!"))
test_object("my_logical",
            undefined_msg = "Please make sure to define a variable `my_logical`.",
            incorrect_msg = "Make sure that you assign the correct value to `my_logical`.") 
success_msg("Great work! Continue to the next exercise.")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:c52153af0b
## Back to Apples and Oranges

Common knowledge tells you not to add apples and oranges. But hey, that is what you just did! The `my_apples` and `my_oranges` variables both contained a number in the previous exercise. The `+` operator works with numeric variables in R. 

However, if you try to add a numeric and a character string, R will complain.

*** =instructions
- Click _Submit Answer_ and read the error message. Make sure you understand why this did not work.
- Adjust `my_oranges <- "six"` such that R knows you have 6 oranges and thus a fruit basket with 11 pieces of fruit. Click _Submit Answer_ again.

*** =hint
You have to assign the numeric value `6` to the `my_oranges` variable instead of the character value `"six"`. Notice how the quotation marks are used to indicate that `"six"` is a character.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Assign a value to the variable my_apples and print it out
my_apples <- 5
my_apples       

# Assign a value to the variable my_oranges and print it out
my_oranges <- "six" 
my_oranges 

# New variable that contains the total amount of fruit
my_fruit <- my_apples + my_oranges 
my_fruit
```

*** =solution
```{r}
# Assign a value to the variable my_apples and print it out
my_apples <- 5  
my_apples  

# Assign a value to the variable my_oranges and print it out
my_oranges <- 6
my_oranges 

# New variable that contains the total amount of fruit
my_fruit <- my_apples + my_oranges 
my_fruit
```

*** =sct
```{r}
test_object("my_apples", incorrect_msg = "Don't change the code that assigns 5 to `my_apples`.")
test_object("my_oranges", incorrect_msg = "Change the assignment of the `my_oranges` variable such that the code runs without errors.")
test_object("my_fruit", 
            undefined_msg = "Please make sure to define a variable `my_fruit`.",
            incorrect_msg = "Make sure that you assign the correct value to `my_fruit`.")
test_output_contains("my_fruit", incorrect_msg = "The output does not contain the result of adding `my_apples` and `my_oranges`.")
success_msg("Awesome, keep up the good work!")
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:7806ca24d2
## What's that data type?

When you added the variables containing `5` and `"six"`, you got an error due to a mismatch in data types. You can avoid such embarrassing situations by checking the data type of a variable beforehand:

```
class(my_var)
```

In the workspace (you can see what it contains by typing [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls) in the console), some variables have already been defined. Which statement concerning these variables are correct?

*** =instructions
- `a`'s class is `integer`, `b` is a `character`, `c` is a `boolean`.
- `a`'s class is `character`, `b` is a `character` as well, `c` is a `logical`.
- `a`'s class is `numeric`, `b` is a `string`, `c` is a `logical`.
- `a`'s class is `numeric`, `b` is a `character`, `c` is a `logical`.

*** =hint
You can find out the data type of the `a` variable for example by typing `class(a)`. You can do similar things for `b` and `c`.

*** =pre_exercise_code
```{r}
a <- 42
b <- "forty-two"
c <- FALSE
```

*** =sct
```{r}
msg1 <- "`boolean` is not the class for logical values. Try again."
msg2 <- "`a` is of the class `numeric`, give it another go."
msg3 <- "`string` is not a class in R. `character` is!"
msg4 <- "Nice one. Let's step it up a notch and start coercing variables!"
test_mc(correct = 4, feedback_msgs = c(msg1, msg2, msg3, msg4))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:c75fe45544
## Coercion: Taming your data

As Filip explained in the video, coercion to transform your data from one type to another is perfectly possible. Next to the [`class()`](http://www.rdocumentation.org/packages/base/functions/class) function and the `is.*()` functions, you can use the `as.*()` functions to force data to change types.

Take this example:

```
var <- "3"
var_num <- as.numeric(var)
```

`var`, a character string, is converted into a numeric using [`as.numeric()`](http://www.rdocumentation.org/packages/base/functions/numeric). The resulting numeric is stored as `var_num`.

*** =instructions
- Convert `var`, a logical, to a character. Assign to resulting character string to the variable `var_char`.
- Inspect the class of `var_char` by using [`class()`](http://www.rdocumentation.org/packages/base/functions/class) on it.

*** =hints
Use the [`as.character()`](http://www.rdocumentation.org/packages/base/functions/character) function to convert `var` to a character.

*** =pre_exercise_code
```{r}
```

*** =sample_code
```{r}
# Definition of var
var <- TRUE

# Convert var to a character: var_char


# Display the class of var_char


```

*** =solution
```{r}
# Definition of var
var <- TRUE

# Convert var to a character: var_char
var_char <- as.character(var)

# Display the class of var_char
class(var_char)
```

*** =sct
```{r}
test_error()
msg <- "Do not remove or change the definition of the variable `var`."
test_object("var", undefined_msg = msg, incorrect_msg = msg)
test_function("as.character", "x",
              not_called_msg = "Make sure to call the function [`as.character()`](http://www.rdocumentation.org/packages/base/functions/character) to convert `var` to a character.",
              incorrect_msg = "Have you passed the correct variable to the function [`as.character()`](http://www.rdocumentation.org/packages/base/functions/character)?")
test_object("var_char")
test_function("class", "x", 
              not_called_msg = "Make sure to call the function <code>class()</code> to inspect the class of <code>var_char</code>.",
              incorrect_msg = "Have you passed the correct variable to the function <code>class()/<code>?")
success_msg("Bellissimo!")
```

