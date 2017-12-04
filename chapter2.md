--- 
title_meta  : Chapter 2
title       : Ce chapitre va traiter la notion de vecteurs chez R. A la fin , l'utilisateur est capable de créer et nommer un vecteur, sélectioonner des élements et comparer plusieurs vecteurs.
attachments : 
  slides_link: https://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/slides/ch2_slides.pdf
  
--- type:VideoExercise lang:r xp:50 skills:1 key:b91dd847a0
## Create and Name Vectors

*** =video_link
//player.vimeo.com/video/138173896

*** =video_hls
//videos.datacamp.com/transcoded/732_intro_to_r/v1/hls-ch2_1.master.m3u8


--- type:NormalExercise lang:r xp:100 skills:1 key:2d1cb04427
## Créer un vecteur (1)


Thanks to R and your new data science skills, you will learn how to uplift your performance at the tables and fire off your career as a professional gambler. This chapter will show how you can easily keep track of your betting progress and how you can do some simple analyses on past actions.

Un vecteur est un tableau à une dimension. Il peut contenir les 4 types de variables vues précédemment.
POur créer un vecteur, on utilise la fonction [`c()`](http://www.rdocumentation.org/packages/base/functions/c). c revient au mot "combine". Les élement du vecteur sont mis entre parenthèses et séparés par une virgule. par exemple:

```
numeric_vector <- c(1, 2, 3)
character_vector <- c("a", "b", "c")
logical_vector <- c(TRUE, FALSE)
```

*** =instructions 
Créer un vecteur, `logical_vector`, qui contient les trois élements : `TRUE`, `FALSE` et `TRUE` (respecter l'ordre). 

*** =hint 
Affecter `c(TRUE, FALSE, TRUE)` à la variable `logical_vector` avec l'opérateur `<-`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
numeric_vector <- c(1, 10, 49)
character_vector <- c("x", "y", "z")

# Créer logical_vector

```

*** =solution
```{r}
numeric_vector <- c(1, 10, 49)
character_vector <- c("x", "y", "z")

# Créer logical_vector
logical_vector <- c(TRUE, FALSE, TRUE)
```

*** =sct
```{r}
msg <- "Ne pas changer comment `numeric_vector` et `character_vector` sont crées!"
lapply(c("numeric_vector", "character_vector"), test_object, undefined_msg = msg, incorrect_msg = msg)
test_object("logical_vector", incorrect_msg = "être sûrque vous avez affecté corrcetement la valeur à `logical_vector`. l'ordre est important!")
success_msg("Parfait! Pratiquons un peu plus avec la création de vecteurs.")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:c6e056b9c3
## Créer un vecteur (2)

Aprsè avoir jouer au casino, nous voulons faire une analyse des données pour croitre les probabilité de gagner dans le future.
Mais d'abord, nous allons collecter les données des gains et des pertes.

Pour `poker_vector`: 
- Lundi: gagner \$140
- Mardi:  **lost** \$50
- Mercredi: gagner \$20 
- Jeudi: **lost** \$120
- Vendredi: ganger \$240

Pour `roulette_vector`: 
- Lundi: **lost** \$24
- Mardi: **lost** \$50
- Mercredi: ganger \$100
- Jeudi: **lost** \$350
- Vendredi: ganger \$10

Pour utiliser ces données il faut créer les vecteurs `poker_vector` et `roulette_vector`.

*** =instructions

Affecter les gains et les pertes du jeu de la roulette  au vecteur `roulette_vector`. Utiliser le bon ordre.

*** =hint
Observer comme est crée le vecteur `poker_vector`. Affecter les valeurs indiquées dans l'exercice à `roulette_vector`. Ne pas oublier que les pertes sont des numéros négatifs. 

*** =pre_exercise_code
```{r}
```

*** =sample_code
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi: roulette_vector

```

*** =solution

```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi: roulette_vector
roulette_vector <- c(-24, -50, 100, -350, 10)
```

*** =sct
```{r}
test_object("poker_vector", 
            incorrect_msg = "Ne pas changer comment `poker_vector` est défini.")
test_object("roulette_vector", 
            incorrect_msg = paste("Etre sûrque vous avez bien affecté les valeurs correctes à `roulette_vector`.",
                                  "Les pertes sont précédées par le signe `-`."))
success_msg("Très bien! Pour vérifier le contenu de vos vecteurs, rappelez-vous que vous pouvez toujours taper simplement la variable dans la console et appuyer sur Entrée. Passez à l'exercice suivant!")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:ebb5aae2ff
## Nommer un vecteur (1)

Pour mieux analyser les doonées, il est important d'avoir une idée claire sur les données. Savoir chaque élement à quoi correspond est essentiel.

Dans l'execice précéden, nous avons créer des vecteurs de chaque type de jeu. Chaque vecteur contient des élements correspondants au gains/pertes pour chaque jour de la semaine. Mais les vecteurs n'indiquent pas quel jour de la semaine est associé chaque élément. ça serait meilleur si le vecteur indique aussi les jours de la semaines.
la fonction [`names()`](http://www.rdocumentation.org/packages/base/functions/names) nomine les éléments d'un vecteur. Par exemple:

```
some_vector <- c("Johnny", "Poker Player")
names(some_vector) <- c("Name", "Profession")
```

*** =instructions
`poker_vector` est déjà nominé par les jour de la semaine. faites la même chose pour `roulette_vector`. Attentien est sensible à la casse!

*** =hint
Affecter `c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")` à `names(roulette_vector)`.

*** =pre_exercise_code
```{r}
```

*** =sample_code
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi
roulette_vector <- c(-24, -50, 100, -350, 10)

# Ajouter des noms (names) au poker_vector
names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Ajouter des noms (names) au roulette_vector

```

*** =solution
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi
roulette_vector <- c(-24, -50, 100, -350, 10)

# Ajouter des noms (names) au poker_vector
names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Ajouter des noms (names) au roulette_vector
names(roulette_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
```

*** =sct
```{r}
msg <- "Ne pas changer les valeurs à l'intérieur de `%s`; c'est fait pour vous."
test_object("poker_vector", incorrect_msg = sprintf(msg, "poker_vector"))
test_object("roulette_vector", incorrect_msg = sprintf(msg, "roulette_vector"))
msg <- "être sûrque vous avez bien choisi les noms à l'intérieur de `%s`. Les noms des jours doivent commencer par une lettre juscule!"
test_object("poker_vector", eq_condition = "equal", incorrect_msg = sprintf(msg, "poker_vector"))
test_object("roulette_vector", eq_condition = "equal", incorrect_msg = sprintf(msg, "roulette_vector"))
success_msg("Bien fait!")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:5c026ed9fb
## Nommer un vecteur (2)

Dans l'exercice précédent, il était ennuieu de taper et retaper les jours de la semaines. IL est possible de créer un vecteur avec les jour de la semaine et l'utiliser mainte fois. 
Créer une variable contenant les jours de la semaines. ainsi, il est possible de l'utiliser plusieurs fois.
Le variable `days_vector` est définie dans la zone script.

*** =instructions
- Utiliser la variable `days_vector` pour attribuer des noms au  `poker_vector`.
- Utiliser la variable `days_vector` pour attribuer des noms au `roulette_vector`.

*** =hint
Vous pouvez utiliser `names(poker_vector) <- ` pour attribuer des noms à la variable `poker_vector`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi
roulette_vector <- c(-24, -50, 100, -350, 10)

# Créer la variable days_vector
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
 
# Utiliser days_vector pour nommer  poker_vector


# Utiliser days_vector pour nommer roulette_vector
```

*** =solution
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi
roulette_vector <- c(-24, -50, 100, -350, 10)

# Créer la variable days_vector
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Utiliser days_vector pour nommer  poker_vector
names(poker_vector) <- days_vector

# Utiliser days_vector pour nommer roulette_vector
names(roulette_vector) <- days_vector
```

*** =sct
```{r}
msg <- "Ne pas changer les valeurs dans `%s`; c'est fait pour vous."
test_object("poker_vector", incorrect_msg = sprintf(msg, "poker_vector"))
test_object("roulette_vector", incorrect_msg = sprintf(msg, "roulette_vector"))
test_object("days_vector", incorrect_msg = sprintf(msg, "days_vector"))

msg <- "être sûrMake sûrde vient affecter `days_vector` au noms de `%s`. Utiliser la fonction `names()`."
test_object("poker_vector", eq_condition = "equal", incorrect_msg = sprintf(msg, "poker_vector"))
test_object("roulette_vector", eq_condition = "equal", incorrect_msg = sprintf(msg, "roulette_vector"))

success_msg("Joli! Un conseil: essayez d'éviter la duplication de code à tout moment.")
```

--- type:VideoExercise lang:r xp:50 skills:1 key:b47466f033
## Vector Arithmetic

*** =video_link
//player.vimeo.com/video/141163398

*** =video_hls
//videos.datacamp.com/transcoded/732_intro_to_r/v1/hls-ch2_2.master.m3u8


--- type:NormalExercise lang:r xp:100 skills:1 key:6b17fc50b9
## Calculer les gains

Il est possible de faire un calcul arithmétique avec les vecteurs. Par example, sommer deux vecteurs, faire de la multiplication ou autre opération.
`c(2,4,6) * 2 est égale à c(4,8,12)`. Chaque élément va être multiplier par 2. `c(2,4,6) - c(1,5,2) = c(1,-1, 4)`. 

Maintenant pour savoir le profit journalié des gains pour les deux jeux, il est possible de faire la somme des deux vecteurs.
Now that you understand how R does arithmetic calculations with vectors, it is time to get those Ferraris in your garage! First, you need to understand what the overall profit or loss per day of the week was. The total daily profit is the sum of the profit/loss you realized on poker per day, and the profit/loss you realized on roulette per day.

Rapelle: les opérations sur les vecteurs se font élément par élément. ces trois écriture sont équivalentes:

```
c(1, 2, 3) + c(4, 5, 6)
c(1 + 4, 2 + 5, 3 + 6)
c(5, 7, 9)
```

*** =instructions
- Affecter à la variable `total_daily` combien y a t il de gain/perte avec les deux jeux (pocker et roulette) pour chaque jour. `total_daily` doit ^être un vecteur de 5 valeurs.
- Imprimer `total_daily`.

*** =hint
Affecter la somme des deux vecteurs à la nouvelle variable `total_daily`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Calculer les entrée journalière: total_daily


# Imprimer total_daily
```

*** =solution
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Calculer les entrée journalière: total_daily
total_daily <- poker_vector + roulette_vector

# Imprimer total_daily
total_daily
```

*** =sct
```{r}
msg = "Ne pas changer des définitions et les noms de `poker_vector` and `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("total_daily", 
            incorrect_msg = "être sureque vous avez affecté la somme de `poker_vector` et `roulette_vector` au `total_daily`. Utiliser `+`.")
test_output_contains("total_daily", incorrect_msg = "Ne pas oublier d'imprimer `total_daily`.")
success_msg("Génial, passer à l'exercice suivant")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:a9a1a50a31
## Calculer les gains totaux: sum()

En se basant sur l'exercice précédent, il parait qu'il y a des jours bons et d'autres mauvais.Mais comment savoir au total s'il y a une perte ou gain d'argent?
 
Pour répondre à cette question, utiliser la fonction [`sum()`](http://www.rdocumentation.org/packages/base/functions/sum) pour calculer la somme de tous les élements de chaque vecteur.

*** =instructions
- Calculez le montant total d'argent que vous avez gagné / perdu avec le poker et attribuez-le à la variable `total_poker`.
- Faites la même chose pour la roulette et assignez le résultat à `total_roulette`.
- Utiliser `+` pour sommer `total_poker` et `total_roulette`, qui est la somme de tous les gains et pertes de la semaine. Imprimer le résultat sur la console.

*** =hint
Utiliser la fonction [`sum()`](http://www.rdocumentation.org/packages/base/functions/sum) pour avoir la total de `poker_vector`. Faites la même chose pour la `roulette_vector`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Les gains totaux avec le Poker: total_poker


# Les gains totaux  avec la Roulette: total_roulette


# Les gains totaux: Imprimer le résultat

```

*** =solution
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Les gains totaux avec le Poker: total_poker
total_poker <- sum(poker_vector)

# Les gains totaux  avec la Roulette: total_roulette
total_roulette <-  sum(roulette_vector)

# Les gains totaux: Imprimer le résultat
total_roulette + total_poker
```

*** =sct
```{r}
msg <- "Ne pas changer les définitions et les noms de `poker_vector` et `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("total_poker", 
            undefined_msg = "Prière d'être sûrde bien définir `total_poker`.",
            incorrect_msg = "être sûrd'affecter à `total_poker` la somme des éléments de `poker_vector`.")
test_object("total_roulette",
            undefined_msg = "Prière d'être sûr de la definition de la variable `total_roulette`.",
            incorrect_msg = "être sûr Make sûr d'affecter à la variable `total_roulette` la somme des éléments de `roulette_vector`.")
test_output_contains("total_poker + total_roulette", incorrect_msg = "Imprimer la somme de `total_poker` et de `total_roulette` au niveau de la console.")
success_msg("Oops, Il semble perdre de l'argent comme vous. Il est temps de penser et adapter à une autre stratégie! Cela exige une analyse approfondie ...")
```


--- type:VideoExercise lang:r xp:50 skills:1 key:513029f4ac
## Vector Subsetting

*** =video_link
//player.vimeo.com/video/138173916

*** =video_hls
//videos.datacamp.com/transcoded/732_intro_to_r/v1/hls-ch2_3.master.m3u8


--- type:NormalExercise lang:r xp:100 skills:1 key:6112e74425
## Selection by index (1)

After you figured that roulette is not your forte, you decide to compare your performance at the beginning of the week to your performance at the end of the week. You did have a couple of Margarita cocktails at the end of the week...

To answer that question, you only want to focus on a selection of the `total_vector`. In other words, our goal is to select specific elements of the vector.

*** =instructions
- Assign the poker results of Wednesday to the variable `poker_wednesday`.
- Assign the roulette results of Friday to the variable `roulette_friday`.

*** =hint
Wednesday is the third element of `poker_vector`, and can thus be selected with `poker_vector[3]`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Poker results of Wednesday: poker_wednesday


# Roulette results of Friday: roulette_friday

```

*** =solution
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Poker results of Wednesday: poker_wednesday
poker_wednesday <- poker_vector[3]

# Roulette results of Friday: roulette_friday
roulette_friday <- roulette_vector[5]
```

*** =sct
```{r}

msg = "Do not change anything about the definition and naming of `poker_vector` and `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_wednesday",
            incorrect_msg = "It looks like `poker_wednesday` does not contain the correct value of `poker_vector`.")
test_object("roulette_friday",
            incorrect_msg = "It looks like `roulette_friday` does not contain the correct value of `roulette_vector`.")
success_msg("Great! R also makes it possible to select multiple elements from a vector at once, remember? Put the theory to practice in the next exercise!")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:ae2832fbd1
## Selection by index (2) 

How about analyzing your midweek results? 

Instead of using a single number to select a single element, you can also select multiple elements by passing a vector inside the square brackets. For example,

```
poker_vector[c(1,5)]
```

selects the first and the fifth element of `poker_vector`.


*** =instructions
- Assign the poker results of Tuesday, Wednesday and Thursday to the variable `poker_midweek`.
- Assign the roulette results of Thursday and Friday to the variable `roulette_endweek`.

*** =hint
Use the vector `c(2,3,4)` between square brackets to select the correct elements of `poker_vector`.

*** =pre_exercise_code
```{r}
# no pec
``` 

*** =sample_code
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Mid-week poker results: poker_midweek


# End-of-week roulette results: roulette_endweek


```

*** =solution
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Mid-week poker results: poker_midweek
poker_midweek <- poker_vector[c(2, 3, 4)]

# End-of-week roulette results: roulette_endweek
roulette_endweek <- roulette_vector[c(4,5)]
```

*** =sct
```{r}
msg <- "Do not change anything about the definition and naming of `poker_vector` and `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

msg <- "It looks like `%s` does not contain the correct elements from `%s`."
test_object("poker_midweek", 
            incorrect_msg = sprintf(msg, "poker_midweek", "poker_vector"))
test_object("roulette_endweek",
            incorrect_msg = sprintf(msg, "roulette_endweek", "roulette_vector"))

success_msg("Well done! Another way to find the mid-week results is `poker_vector[2:4]`. Continue to the next exercise to specialize in vector selection some more!");
```

--- type:NormalExercise lang:r xp:100 skills:1 key:5919f3fc05
## Selection by name

Another way to tackle the previous exercise is by using the names of the vector elements (Monday, Tuesday, ...) instead of their numeric positions. For example, 

```
poker_vector["Monday"]
```

will select the first element of `poker_vector` since `"Monday"` is the name of that first element.

*** =instructions
- Select the fourth element, corresponding to Thursday, from `roulette_vector`. Name it `roulette_thursday`.
- Select Tuesday's poker gains using subsetting by name. Assign the result to `poker_tuesday`.

*** =hint
You can use `mean(my_vector)` to get the mean of the vector `my_vector`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Select Thursday's roulette gains: roulette_thursday


# Select Tuesday's poker gains: poker_tuesday

```

*** =solution
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Select Thursday's roulette gains: roulette_thursday
roulette_thursday <- roulette_vector["Thursday"]

# Select Tuesday's poker gains: poker_tuesday
poker_tuesday <- poker_vector["Tuesday"]
```

*** =sct
```{r}
msg <- "Do not change anything about the definition and naming of `poker_vector` and `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

test_object("roulette_thursday")
test_object("poker_tuesday")
success_msg("Good job! Head over to the next exercise.");
```

--- type:NormalExercise lang:r xp:100 skills:1 key:22121c6c46
## Selection by logicals (1)

There are basically three ways to subset vectors: by using the indices, by using the names (if the vectors are named) and by using logical vectors. Filip already told you about the internals in the instructional video. As a refresher, have a look at the following statements to select elements from `poker_vector`, which are all equivalent:

```
# selection by index
poker_vector[c(1,3)]

# selection by name
poker_vector[c("Monday", "Wednesday")]

# selection by logicals
poker_vector[c(TRUE, FALSE, TRUE, FALSE, FALSE)]
```

*** =instructions
- Assign the roulette results from the first, third and fifth day to `roulette_subset`.
- Select the first three days from `poker_vector` using a vector of logicals. Assign the result to `poker_start`.

*** =hint
The logical vector to use inside square brackets for the first instruction is `c(TRUE, FALSE, TRUE, FALSE, TRUE)`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Roulette results for day 1, 3 and 5: roulette_subset

  
# Poker results for first three days: poker_start
```

*** =solution
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Roulette relsults for day 1, 3 and 5: roulette_subset
roulette_subset <- roulette_vector[c(TRUE, FALSE, TRUE, FALSE, TRUE)]
  
# Poker results for first three days: poker_start
poker_start <- poker_vector[c(TRUE, TRUE, TRUE, FALSE, FALSE)]
```

*** =sct
```{r}
msg = "Do not change anything about the definition and naming of `poker_vector` and `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_subset")
test_object("poker_start")
success_msg("Nice one! Using logical vectors to perform subsetting might seem somewhat tedious, but its true power will become clear in the next exercise!")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:aa2e5f6e97
## Selection by logicals (2)

By making use of a combination of comparison operators and subsetting using logicals, you can investigate your casino performance in a more pro-active way.

The (logical) comparison operators known to R are:
- `<` for less than
- `>` for greater than
- `<=` for less than or equal to
- `>=` for greater than or equal to
- `==` for equal to each other
- `!=` not equal to each other

Experiment with these operators in the console:

```
lost_roulette_days <- roulette_vector < 0
lost_roulette_days
```

The result will be a logical vector, which you can use to perform subsetting, like this example:

```
roulette_vector[lost_roulette_days]
```

The result is a subset of `roulette_vector` that contains only your losses in roulette.

*** =instructions
- Check if your poker winnings are positive on the different days of the week (i.e. > 0), and assign this to `selection_vector`.
- Assign the amounts that you won on the profitable days to the variable `poker_profits` by using `selection_vector`.

*** =hint
- In order to check for which days your poker gains are positive, R should check for each element of `poker_vector` whether it is larger than zero. `some_vector > 0` is the way to tell R what you are after.
- After creating `selection_vector`, you can use it to subset `poker_vector` like this: `poker_vector[selection_vector]`.

*** =pre_exercise_code
```{r}
# no pec
```

*** =sample_code
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Create logical vector corresponding to profitable poker days: selection_vector


# Select amounts for profitable poker days: poker_profits
 
```

*** =solution
```{r}
# Casino winnings from Monday to Friday
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Create logical vector corresponding to profitable poker days: selection_vector
selection_vector <- poker_vector > 0

# Select amounts for profitable poker days: poker_profits
poker_profits <- poker_vector[selection_vector]
```

*** =sct
```{r}
msg = "Do not change anything about the definition and naming of `poker_vector` and `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("selection_vector", 
            undefined_msg = "Please make sûrto define a variable `selection_vector`.",
            incorrect_msg = "It looks like `selection_vector` does not contain the correct result. Remember that R uses element wise operations for vectors.")
test_object("poker_profits",
            undefined_msg =  "Please make sûrto define a variable `poker_profits`.",
            incorrect_msg =  "It looks like `poker_profits` does not contain the correct result. Remember that R uses element wise operations for vectors.")
success_msg("Great! Move on to the Matrices chapter!")
```
