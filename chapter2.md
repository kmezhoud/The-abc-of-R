---
title_meta: 'Chapter 2'
title: 'Les vecteurs'
description: 'Ce chapitre va traiter la notion de vecteurs chez R. A la fin , l''utilisateur est capable de créer et nommer un vecteur, sélectioonner des élements et comparer plusieurs vecteurs.'
attachments:
    slides_link: 'https://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/slides/ch2_slides.pdf'
---

## Create and Name Vectors

```yaml
type: VideoExercise
key: b91dd847a0
lang: r
xp: 50
skills: 1
video_link: //player.vimeo.com/video/138173896
video_hls: //videos.datacamp.com/transcoded/732_intro_to_r/v1/hls-ch2_1.master.m3u8
```


---

## Créer un vecteur (1)

```yaml
type: NormalExercise
key: 2d1cb04427
lang: r
xp: 100
skills: 1
```

Thanks to R and your new data science skills, you will learn how to uplift your performance at the tables and fire off your career as a professional gambler. This chapter will show how you can easily keep track of your betting progress and how you can do some simple analyses on past actions.

Un vecteur est un tableau à une dimension. Il peut contenir les 4 types de variables vues précédemment.
POur créer un vecteur, on utilise la fonction [`c()`](http://www.rdocumentation.org/packages/base/functions/c). c revient au mot "combine". Les élement du vecteur sont mis entre parenthèses et séparés par une virgule. par exemple:

```
numeric_vector <- c(1, 2, 3)
character_vector <- c("a", "b", "c")
logical_vector <- c(TRUE, FALSE)
```

`@instructions`
Créer un vecteur, `logical_vector`, qui contient les trois élements : `TRUE`, `FALSE` et `TRUE` (respecter l'ordre).

`@hint`
Affecter `c(TRUE, FALSE, TRUE)` à la variable `logical_vector` avec l'opérateur `<-`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
numeric_vector <- c(1, 10, 49)
character_vector <- c("x", "y", "z")

# Créer logical_vector

```

`@solution`
```{r}
numeric_vector <- c(1, 10, 49)
character_vector <- c("x", "y", "z")

# Créer logical_vector
logical_vector <- c(TRUE, FALSE, TRUE)
```

`@sct`
```{r}
msg <- "Ne pas changer comment `numeric_vector` et `character_vector` sont crées!"
lapply(c("numeric_vector", "character_vector"), test_object, undefined_msg = msg, incorrect_msg = msg)
test_object("logical_vector", incorrect_msg = "être sûrque vous avez affecté corrcetement la valeur à `logical_vector`. l'ordre est important!")
success_msg("Parfait! Pratiquons un peu plus avec la création de vecteurs.")
```

---

## Créer un vecteur (2)

```yaml
type: NormalExercise
key: c6e056b9c3
lang: r
xp: 100
skills: 1
```

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

`@instructions`
Affecter les gains et les pertes du jeu de la roulette  au vecteur `roulette_vector`. Utiliser le bon ordre.

`@hint`
Observer comme est crée le vecteur `poker_vector`. Affecter les valeurs indiquées dans l'exercice à `roulette_vector`. Ne pas oublier que les pertes sont des numéros négatifs.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi: roulette_vector

```

`@solution`
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi: roulette_vector
roulette_vector <- c(-24, -50, 100, -350, 10)
```

`@sct`
```{r}
test_object("poker_vector", 
            incorrect_msg = "Ne pas changer comment `poker_vector` est défini.")
test_object("roulette_vector", 
            incorrect_msg = paste("Etre sûrque vous avez bien affecté les valeurs correctes à `roulette_vector`.",
                                  "Les pertes sont précédées par le signe `-`."))
success_msg("Très bien! Pour vérifier le contenu de vos vecteurs, rappelez-vous que vous pouvez toujours taper simplement la variable dans la console et appuyer sur Entrée. Passez à l'exercice suivant!")
```

---

## Nommer un vecteur (1)

```yaml
type: NormalExercise
key: ebb5aae2ff
lang: r
xp: 100
skills: 1
```

Pour mieux analyser les doonées, il est important d'avoir une idée claire sur les données. Savoir chaque élement à quoi correspond est essentiel.

Dans l'execice précéden, nous avons créer des vecteurs de chaque type de jeu. Chaque vecteur contient des élements correspondants au gains/pertes pour chaque jour de la semaine. Mais les vecteurs n'indiquent pas quel jour de la semaine est associé chaque élément. ça serait meilleur si le vecteur indique aussi les jours de la semaines.
la fonction [`names()`](http://www.rdocumentation.org/packages/base/functions/names) nomine les éléments d'un vecteur. Par exemple:

```
some_vector <- c("Johnny", "Poker Player")
names(some_vector) <- c("Name", "Profession")
```

`@instructions`
`poker_vector` est déjà nominé par les jour de la semaine. faites la même chose pour `roulette_vector`. Attentien est sensible à la casse!

`@hint`
Affecter `c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")` à `names(roulette_vector)`.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Vecteur du jeu de Poker de lundu au vendredi
poker_vector <- c(140, -50, 20, -120, 240)

# Vecteur du jeu de la Roulette de lundi au vendredi
roulette_vector <- c(-24, -50, 100, -350, 10)

# Ajouter des noms (names) au poker_vector
names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")

# Ajouter des noms (names) au roulette_vector

```

`@solution`
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

`@sct`
```{r}
msg <- "Ne pas changer les valeurs à l'intérieur de `%s`; c'est fait pour vous."
test_object("poker_vector", incorrect_msg = sprintf(msg, "poker_vector"))
test_object("roulette_vector", incorrect_msg = sprintf(msg, "roulette_vector"))
msg <- "être sûrque vous avez bien choisi les noms à l'intérieur de `%s`. Les noms des jours doivent commencer par une lettre juscule!"
test_object("poker_vector", eq_condition = "equal", incorrect_msg = sprintf(msg, "poker_vector"))
test_object("roulette_vector", eq_condition = "equal", incorrect_msg = sprintf(msg, "roulette_vector"))
success_msg("Bien fait!")
```

---

## Nommer un vecteur (2)

```yaml
type: NormalExercise
key: 5c026ed9fb
lang: r
xp: 100
skills: 1
```

Dans l'exercice précédent, il était ennuieu de taper et retaper les jours de la semaines. IL est possible de créer un vecteur avec les jour de la semaine et l'utiliser mainte fois. 
Créer une variable contenant les jours de la semaines. ainsi, il est possible de l'utiliser plusieurs fois.
Le variable `days_vector` est définie dans la zone script.

`@instructions`
- Utiliser la variable `days_vector` pour attribuer des noms au  `poker_vector`.
- Utiliser la variable `days_vector` pour attribuer des noms au `roulette_vector`.

`@hint`
Vous pouvez utiliser `names(poker_vector) <- ` pour attribuer des noms à la variable `poker_vector`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
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

`@solution`
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

`@sct`
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

---

## Vector Arithmetic

```yaml
type: VideoExercise
key: b47466f033
lang: r
xp: 50
skills: 1
video_link: //player.vimeo.com/video/141163398
video_hls: //videos.datacamp.com/transcoded/732_intro_to_r/v1/hls-ch2_2.master.m3u8
```


---

## Calculer les gains

```yaml
type: NormalExercise
key: 6b17fc50b9
lang: r
xp: 100
skills: 1
```

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

`@instructions`
- Affecter à la variable `total_daily` combien y a t il de gain/perte avec les deux jeux (pocker et roulette) pour chaque jour. `total_daily` doit ^être un vecteur de 5 valeurs.
- Imprimer `total_daily`.

`@hint`
Affecter la somme des deux vecteurs à la nouvelle variable `total_daily`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
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

`@solution`
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

`@sct`
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

---

## Calculer les gains totaux: sum()

```yaml
type: NormalExercise
key: a9a1a50a31
lang: r
xp: 100
skills: 1
```

En se basant sur l'exercice précédent, il parait qu'il y a des jours bons et d'autres mauvais.Mais comment savoir au total s'il y a une perte ou gain d'argent?
 
Pour répondre à cette question, utiliser la fonction [`sum()`](http://www.rdocumentation.org/packages/base/functions/sum) pour calculer la somme de tous les élements de chaque vecteur.

`@instructions`
- Calculez le montant total d'argent que vous avez gagné / perdu avec le poker et attribuez-le à la variable `total_poker`.
- Faites la même chose pour la roulette et assignez le résultat à `total_roulette`.
- Utiliser `+` pour sommer `total_poker` et `total_roulette`, qui est la somme de tous les gains et pertes de la semaine. Imprimer le résultat sur la console.

`@hint`
Utiliser la fonction [`sum()`](http://www.rdocumentation.org/packages/base/functions/sum) pour avoir la total de `poker_vector`. Faites la même chose pour la `roulette_vector`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
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

`@solution`
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

`@sct`
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

---

## Vector Subsetting

```yaml
type: VideoExercise
key: 513029f4ac
lang: r
xp: 50
skills: 1
video_link: //player.vimeo.com/video/138173916
video_hls: //videos.datacamp.com/transcoded/732_intro_to_r/v1/hls-ch2_3.master.m3u8
```


---

## Selection par index (1)

```yaml
type: NormalExercise
key: 6112e74425
lang: r
xp: 100
skills: 1
```

Notre objectif est de sélectionner des éléments spécifiques du vecteur. Pour sélectionner des éléments d'un vecteur  (des matrices , des blocs de données, ...), vous pouvez utiliser des crochets [...]. Entre les crochets, vous indiquez quels éléments sélectionner. Par exemple, pour sélectionner le premier élément du vecteur, vous devez taper `poker_vector[1]`. Pour sélectionner le second élément du vecteur, vous tapez `taper_vector[2]`, etc. Notez que le premier élément d'un vecteur a l'index 1, et non 0 comme dans beaucoup d'autres langages de programmation.

`@instructions`
- Affecter le résulat du poker  de mercredi à la variable `poker_wednesday`.
- Affecter le résultat de la roulette de vendredi à la variable `roulette_friday`.

`@hint`
Mercredi est le troisième élément de `poker_vector`, il est sélectionner par l'opération `poker_vector[3]`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Le résulat du poker de mercredi: poker_wednesday


# le résulat de la roulette de vendredi: roulette_friday

```

`@solution`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Le résulat du poker de mercredi: poker_wednesday
poker_wednesday <- poker_vector[3]

# le résulat de la roulette de vendredi: roulette_friday
roulette_friday <- roulette_vector[5]
```

`@sct`
```{r}

msg = "Ne changer rien aux définitions et aux noms de `poker_vector` et `roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_wednesday",
            incorrect_msg = "Il semble que `poker_wednesday` ne contient pas la valeur juste de `poker_vector`.")
test_object("roulette_friday",
            incorrect_msg = "Il semble que `roulette_friday` ne contient pas la valeur juste de `roulette_vector`.")
success_msg("Génial! R permet également de sélectionner plusieurs éléments d'un vecteur à la fois, souvenez-vous? Mettez la théorie à la pratique dans l'exercice suivant!")
```

---

## Selection par index (2)

```yaml
type: NormalExercise
key: ae2832fbd1
lang: r
xp: 100
skills: 1
```

Que diriez-vous d'analyser vos résultats en milieu de semaine?

Au lieu d'utiliser un seul nombre pour sélectionner un seul élément, vous pouvez également sélectionner plusieurs éléments en passant un vecteur dans les crochets. Par exemple,

```
poker_vector[c(1,5)]
```

sélectionne le premier et le cinquième élément de `poker_vector`.

`@instructions`
- Affectez les résultats de poker des mardi, mercredi et jeudi à la variable `poker_midweek`.
- Attribuer les résultats de la roulette de jeudi et vendredi à la variable `roulette_endweek`.

`@hint`
Utilisez le vecteur `c (2,3,4)` entre crochets pour sélectionner les éléments corrects de `poker_vector`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Résultats de poker en milieu de semaine: poker_midweek


# Résultats de la roulette à la fin de la semaine: roulette_endweek


```

`@solution`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Résultats de poker en milieu de semaine: poker_midweek
poker_midweek <- poker_vector[c(2, 3, 4)]

# Résultats de la roulette à la fin de la semaine: roulette_endweek
roulette_endweek <- roulette_vector[c(4,5)]
```

`@sct`
```{r}
msg <- "Ne changez rien aux définitions et aux noms de `poker_vector` et` roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

msg <- "Il semble que `% s` ne contienne pas les éléments corrects de`% s`."
test_object("poker_midweek", 
            incorrect_msg = sprintf(msg, "poker_midweek", "poker_vector"))
test_object("roulette_endweek",
            incorrect_msg = sprintf(msg, "roulette_endweek", "roulette_vector"))

success_msg("Bien joué! Une autre façon de trouver les résultats en milieu de semaine est `poker_vector [2: 4]`. Passez à l'exercice suivant pour vous spécialiser encore plus dans la sélection de vecteurs!");
```

---

## Selection par nom  (name)

```yaml
type: NormalExercise
key: 5919f3fc05
lang: r
xp: 100
skills: 1
```

Une autre façon d'aborder l'exercice précédent consiste à utiliser les noms des éléments vectoriels (lundi, mardi, ...) au lieu de leurs positions numériques. Par exemple, 

```
poker_vector["Monday"]
```

sélectionnera le premier élément de `poker_vector` puisque` "Monday" `est le nom de ce premier élément.

`@instructions`
- Sélectionnez le quatrième élément, correspondant à jeudi, à partir de `roulette_vector`. Nommez-le `roulette_thursday`.
- Sélectionnez les gains de poker de mardi en utilisant le sous-ensemble par nom. Affectez le résultat à `poker_tuesday`.

`@hint`
Vous pouvez utiliser `mean(my_vector)` pour obtenir la moyenne du vecteur `my_vector`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Sélectionnez les gains de la roulette du jeudi: roulette_thursday


# Sélectionnez les gains de poker du mardi: poker_tuesday

```

`@solution`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Sélectionnez les gains de la roulette du jeudi: roulette_thursday
roulette_thursday <- roulette_vector["Thursday"]

# Sélectionnez les gains de poker du mardi: poker_tuesday
poker_tuesday <- poker_vector["Tuesday"]
```

`@sct`
```{r}
msg <- "Ne changez rien aux définitions et aux noms de `poker_vector` et` roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)

test_object("roulette_thursday")
test_object("poker_tuesday")
success_msg("Bon travail! Rendez-vous au prochain exercice.");
```

---

## Selection par logique (1)

```yaml
type: NormalExercise
key: 22121c6c46
lang: r
xp: 100
skills: 1
```

Il existe essentiellement trois façons de sous-ensembles de vecteurs: en utilisant les indices, en utilisant les noms (si les vecteurs sont nommés) et en utilisant des vecteurs logiques. Jetez un oeil aux instructions suivantes pour sélectionner les éléments de `poker_vector`, qui sont tous équivalents:

```
# selection by index
poker_vector[c(1,3)]

# selection by name
poker_vector[c("Monday", "Wednesday")]

# selection by logicals
poker_vector[c(TRUE, FALSE, TRUE, FALSE, FALSE)]
```

`@instructions`
- Assignez les résultats de la roulette du premier, troisième et cinquième jour à `roulette_subset`.
- Sélectionnez les trois premiers jours à partir de `poker_vector` en utilisant un vecteur de logique. Affectez le résultat à `poker_start`.

`@hint`
Le vecteur logique à utiliser entre crochets pour la première instruction est `c (TRUE, FALSE, TRUE, FALSE, TRUE)`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Résultats de la roulette pour les jours 1, 3 et 5: roulette_subset

  
# Résultats du poker pour les trois premiers jours: poker_start
```

`@solution`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Résultats de la roulette pour les jours 1, 3 et 5: roulette_subset
roulette_subset <- roulette_vector[c(TRUE, FALSE, TRUE, FALSE, TRUE)]
  
# Résultats du poker pour les trois premiers jours: poker_start
poker_start <- poker_vector[c(TRUE, TRUE, TRUE, FALSE, FALSE)]
```

`@sct`
```{r}
msg = "Ne changez rien à la définition et à l'appellation de `poker_vector` et` roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_subset")
test_object("poker_start")
success_msg("Joli! L'utilisation de vecteurs logiques pour effectuer le sous-ensemble peut sembler quelque peu fastidieuse, mais sa véritable puissance apparaîtra clairement dans l'exercice suivant.!")
```

---

## Selection par logique (2)

```yaml
type: NormalExercise
key: aa2e5f6e97
lang: r
xp: 100
skills: 1
```

En utilisant une combinaison d'opérateurs de comparaison et de sous-ensembles utilisant des logiques, vous pouvez étudier les gains et les pertes de manière plus précise.

Les opérateurs de comparaison (logiques) connus de R sont:
- `<`   moins de
- `>`   plus de
- `<=`  moins que ou égal à
- `> =` plus grand que ou égal à
- `==`  égal à l'autre
- `! =` pas égal l'un à l'autre

Expérimentez avec ces opérateurs dans la console:

```
lost_roulette_days <- roulette_vector < 0
lost_roulette_days
```

Le résultat sera un vecteur logique, que vous pouvez utiliser pour effectuer un sous-ensemble, comme dans cet exemple:

```
roulette_vector[lost_roulette_days]
```

Le résultat est un sous-ensemble de `roulette_vector` qui contient uniquement vos pertes à la roulette.

`@instructions`
- Vérifiez si vos gains de poker sont positifs les différents jours de la semaine (c.-à-d.> 0) et affectez-les à `selection_vector`.
- Affectez les montants que vous avez gagnés sur les jours rentables à la variable `poker_profits` en utilisant` selection_vector`.

`@hint`
- Afin de vérifier quels jours vos gains de poker sont positifs, R devrait vérifier pour chaque élément de `poker_vector` s'il est plus grand que zéro. `some_vector> 0` est le moyen de dire à R ce que vous recherchez.
- Après avoir créé `selection_vector`, vous pouvez l'utiliser pour le sous-ensemble` poker_vector` comme ceci: `poker_vector [selection_vector]`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Créer un vecteur logique correspondant aux jours de poker rentables: selection_vector


# Sélectionnez les montants pour les jours de poker rentables: poker_profits
 
```

`@solution`
```{r}
# Les gains de lundi à vendredi
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Créer un vecteur logique correspondant aux jours de poker rentables: selection_vector
selection_vector <- poker_vector > 0

# Sélectionnez les montants pour les jours de poker rentables: poker_profits
poker_profits <- poker_vector[selection_vector]
```

`@sct`
```{r}
msg = "Ne changez rien à la définition et à l'appellation de `poker_vector` et` roulette_vector`."
test_object("days_vector", undefined_msg = msg, incorrect_msg = msg)
test_object("poker_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("roulette_vector", eq_condition = "equal", undefined_msg = msg, incorrect_msg = msg)
test_object("selection_vector", 
            undefined_msg = "Assurez-vous de définir une variable `selection_vector`.",
            incorrect_msg = "Il semble que `selection_vector` ne contienne pas le bon résultat. Rappelez-vous que R utilise des opérations élémentaires pour les vecteurs. ")
test_object("poker_profits",
            undefined_msg =  "Assurez-vous de définir une variable `poker_profits`.",
            incorrect_msg =  "Il semble que `poker_profits` ne contienne pas le bon résultat. Rappelez-vous que R utilise des opérations élémentaires pour les vecteurs. ")
success_msg("Great! Passez au chapitre des Matrices!")
```
