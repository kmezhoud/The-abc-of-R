---
title_meta: 'Chapter 1'
title: Initiation
description: 'Initiation au language R'
attachments:
    slides_link: 'https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf'
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
Utiliser les flèchettes pour naviguer sur les graphes générer avec R sur votre fenêtre à droite en haut. Noter que vous pouvez élargir votre fenêtre pour avoir une meilleure vue.

`@instructions`
1. Click **Submit Answer** et regardez au niveau de la console l'exécution du code R: La solution `7` apparait pour la somme de `3` et `4`. A sa forme basique R peut être utiliser comme une calculatrice ou pour générer des plots. Mais en réalité, il peut faire mieux que cela ;-).

`@hint`
Juste cliquer sur le boutton `Submit Answer`

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r eval=FALSE}
# Juste cliquer sur le boutton `Submit Answer` pour soumettre la/les commandes

# C'est l'éditeur des commandes et la partie en bas est la console R où on exécute les commandes.

# Les hashtag sont utilisées pour ajouter des commentaires explicatives des commandes

# Calculer 3 + 4
3 + 4

# Visualiser quelques graphes demonstratives generés par R
# demo("graphics")
```

`@solution`
```{r eval:FALSE}
# Juste cliquer sur le boutton `Submit Answer` pour soumettre la/les commandes

# C'est l'éditeur des commandes et la partie en bas est la console R où on exécute les commandes.

# Les hashtag sont utilisées pour ajouter des commentaires explicatives des commandes

# Calculer 3 + 4
3 + 4

# Visualiser quelques graphes demonstratives generés par R
# demo("graphics")
```

`@sct`
```{r eval=FALSE}
test_output_contains("3 + 4", incorrect_msg = 'Faux, répétez.')
success_msg("Bien!")
```

---

## R est une calculatrice

```yaml
type: NormalExercise
key: 9d8a3d0b88
lang: r
xp: 100
skills: 1
```

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

`@instructions`
- Taper `2^5` dans la zone script pour calculer 2 à la puissance 5.
- Taper `28 %% 6` pour calculer le 28 modulo 6.
- Cliquer **Submit Answer** et observer le outout à la console.

`@hint`
Un autre exemple de l'opérateur modulo: `9 %% 2` est égale à `1`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
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

`@solution`
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

`@sct`
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

---

## Les avantages et les inconvénients de R

```yaml
type: MultipleChoiceExercise
key: 9d8819fb2e
xp: 50
skills: 1
```

D'une part, il y a des caractéristiques qui rendent le language R est populaire. D'autre part, il y a d'autres aspects qui le rendent moins attractif. Quelles sont parmis les phrases suivantes qui semblent correctes pour le language R?

1. Par opposition à SAS et SPSS, R est complétement open-source.
2. R est open-source, mais il est difficile de partager le code étant donnée qu'il faut une concole pour l'utiliser.
3. Typiquement, cela prendre beaucoup de temps pour que les mise à jour des package R soit disponibles publiquement.
4. R est facile à utiliser, mais cela limite les capacités à générer des graphes.
5. R fonctionne très bien avec une large série de données, si le code est proprement écrit et les données convient à la mémoire du système.

`@instructions`
- Phrases (1) et (2) sont correctes; les autres sont fausses.
- Phrases (1) et (4) sont correctes; les autres sont fausses.
- Phrases (1) et (5) sont correctes; les autres sont fausses.
- Phrases (2) et (4) sont correctes; les autres sont fausses.
- Phrases (3) et (5) sont correctes; les autres sont fausses.

`@hint`
Rappelez-vous que les données doivent convenir à la mémoire du système pour qu'elles puissent être traitées.

`@pre_exercise_code`
```{r}
# no pec
```

`@sct`
```{r}
msg1 = "Le fait que R nécéssite une console n'affecte pas qu'il foit plus difficile de partéger son code. Au contraire, partager son code R, devient très facile et simple."
msg2 = "R est l'outil parfait pour créer des visualisations soignées et perspicaces. Réessayer."
msg3 = "Génial! Dirigez-vous vers l'exercice suivant!"
msg4 = "R utilise une interface de ligne de commande, ce qui facilite le partage de son code. En outre, R est très approprié pour créer des visualisations. Réessayer."
msg5 = "Il est assez simple d'écrire, de maintenir et de partager des paquets R. Réessayer."
test_mc(3, feedback_msgs = c(msg1, msg2, msg3, msg4, msg5))
```

---

## Affectation de variable (1)

```yaml
type: NormalExercise
key: 6b6fb4974c
lang: r
xp: 100
skills: 1
```

Une variable permet au utilisateur de stocker une valeur ou un objet dans R. Ultérieurement, l'utilisateur pourrait utiliser ces variables pour accéder au valeur ou objet stockés dans la variable. Utiliser `<-` pour affecter une variable:

```
my_variable <- 4
```

`@instructions`
Compléter le code dan l'éditeur sachant qu'il affecte la valeur 42 à la variabel `x`. Cliquer `Submit Answer`. Noter que si vous demandez à R d'imprimer `x`, la valeur 42 parait.

`@hint`
Observer comment la valeur 4 est affectée à la variable `my_variable`. Faire exactement la même chose dans l'éditeur, mais affecter 42 à la variabel `x`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Affecter la valeur 42 à x


# Imprimer la valeur de la variable x

```

`@solution`
```{r}
# Affecter la valeur 42 à x
x <- 42

# Imprimer la valeur de la variable x
x
```

`@sct`
```{r}
test_error()
test_object("x", 
            undefined_msg = "Assurez-vous de définir la variable <code>x</code>.",
            incorrect_msg = "Assurez-vous que l'affectation de la valeur à <code>x</code> est correcte.") 
success_msg("Bon travail! Notez que R n'imprime pas la valeur d'une variable sur la console lorsque vous effectuez l'affectation. <code> x <- 42 </ code> n'a généré aucune sortie, car R suppose que vous aurez besoin de cette variable dans le futur. Sinon, vous n'auriez pas stocké la valeur dans une variable en premier lieu, non? Passez à l'exercice suivant!")
```

---

## Affectation de variable (2)

```yaml
type: NormalExercise
key: a5b8028834
xp: 100
skills: 1
```

Supposer que vous avez un panier de fruits avec 5 pommes. Vous voulez stocker le nombre de pomme dans une variable nommée `my_apples`

`@instructions`
- Utiliser `<-`, affecter la valeur 5 à `my_apples` en dessous du premier commentaire.
- Taper `my_apples` en dessous du second commentaire. Cela va imprimer la valeur de `my_apples`.
- Après cliquer **Submit Answer**, Regarder au niveau de la console: Le nombre 5 est imprimé. R lie la variable `my_apples` à la valeur 5.

`@hint`
Rappelr que si vous voulez affecter un nombre ou un objet à une variable, utilisez l'opérateur `<-`. Alternativement, vous pouvez utiliser `=`, mais `<-` est recommandé dans la communauté de R.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Affecter la valeur 5 à la variable nommée my_apples


# Imprimer la valeur de la variable my_apples

```

`@solution`
```{r}
# Affecter la valeur 5 à la variable nommée my_apples
my_apples <- 5

# Imprimer la valeur de la variable my_apples
my_apples
```

`@sct`
```{r}
test_object("my_apples", incorrect_msg = "Avez-vous correctement assigné 5 à `my_apples`? Ecrivez `my_apples <- 5` sur une nouvelle ligne dans la zone script.")
test_output_contains("my_apples", incorrect_msg = "Avez-vous explicitement demandé à R d'imprimer la variable `my_apples` sur la console? Tapez simplement `my_apples` sur une nouvelle ligne.")
success_msg("Génial! Vous pouvez aussi utiliser `=` pour l'assignation de variable, mais `<-` est généralement préféré.")
```

---

## Affectation de variable (3)

```yaml
type: NormalExercise
key: a0cb1bea96
lang: r
xp: 100
skills: 1
```

Chaque panier de fruits savoureux a besoin d'oranges, vous décidez donc d'ajouter six oranges. Vous décidez de créer la variable `my_oranges` et lui assignez la valeur 6. Ensuite, vous voulez calculer combien de morceaux de fruits vous avez au total. Puisque vous avez donné des noms significatifs à ces valeurs, vous pouvez maintenant le coder de manière claire:

```
my_apples + my_oranges
```

`@instructions`
- Affecter à `my_oranges` la valeur 6.
- Ajouter les variables `my_apples` et `my_oranges` et imprimer le resultat.
- Combiner les variables `my_apples` et `my_oranges` dans une nouvelle variable `my_fruit`, qui est la totale des fruits dans el panier.

`@hint`
`my_fruit` est mla somme de `my_apples` et `my_oranges`. Vous pouvez utiliser l'opérateur `+` pour faire la somme et `<-` pour affecter la valeur à la variable `my_fruit`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Affecter 5 à my_apples


# Affecter 6 à my_oranges


# Ajouter my_apples et my_oranges: Imprimer le résultat


# Ajouter my_apples et my_oranges: Affecter à my_fruit

```

`@solution`
```{r}
# Affecter 5 à my_apples
my_apples <- 5

# Affecter 6 à my_oranges
my_oranges <- 6

# Ajouter my_apples et my_oranges: Imprimer le résultat
my_apples + my_oranges

# Ajouter my_apples et my_oranges: Affecter à my_fruit
my_fruit <- my_apples + my_oranges
```

`@sct`
```{r}
test_object("my_apples", incorrect_msg = "Ne changez pas l'affectation de la variable `my_apples`!")
test_object("my_oranges")
test_output_contains("my_apples + my_oranges",
                     incorrect_msg = "La sortie ne contient pas le résultat de la somme de `my_apples` et` my_oranges` (seconde instruction). Réessayer.")
test_object("my_fruit")
success_msg("Bien! Le grand avantage de faire des calculs avec des variables est la réutilisabilité. Si vous changez simplement `my_apples` à 12 au lieu de 5 et relancez le script,` my_fruit` sera automatiquement mis à jour.")

```

---

## L'espace de travail

```yaml
type: NormalExercise
key: 6192f64167
lang: r
xp: 100
skills: 1
```

Si vous attribuez une valeur à une variable, cette variable est stockée dans l'espace de travail. C'est l'endroit où vivent toutes les variables définies par l'utilisateur. La commande [`ls ()`] (http://www.rdocumentation.org/packages/base/functions/ls) répertorie le contenu de cet espace de travail.

```
a <- 1
b <- 2
ls()
```

les premières lignes créent les variables `a` et `b`. 
The first two lines create the variables `a` and `b`. Appelant [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls) nous montre que `a` et `b` sont dans l'espace de travail.

Vous pouvez aussi éliminer des variables de l'espace de travail. Vous pouvez faire cela avec la commande [`rm()`](http://www.rdocumentation.org/packages/base/functions/rm). `rm(a)`, par exemple efface la variables `a` de l'espace de travail. la commande `rm(list = ls())` est utilisée au début de votre script pour  tout effacer de votre espace de travail.

`@instructions`
- Créer une variable, `horses`, égale à 3, et a une variable `dogs`, égale à 7.
- Lister le contenu de votre espace de travail avec [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls), qui montre que les variables sont bien stockées.

`@hint`
tout ce que vous avez besoin est [`ls()`](http://www.rdocumentation.org/packages/base/functions/ls) et [`rm()`](http://www.rdocumentation.org/packages/base/functions/rm). Essayez-les et laissez-vous guider par les messages de rétroaction.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Effacer entièrement votre espace de travail
rm(list = ls())

# Créer les variables horses et dogs


# Lister le contenu de votre espace de travail


```

`@solution`
```{r}
# Effacer entièrement votre espace de travail
rm(list = ls())

# Créer les variables horses et dogs
horses <- 3
dogs <- 7

# Lister le contenu de votre espace de travail
ls()
```

`@sct`
```{r}
test_student_typed("rm(list = ls())", not_typed_msg = "Ne pas effacer la ligne `rm(list = ls())`.")
test_object("horses")
test_object("dogs")
test_output_contains('c("dogs", "horses")',
                     incorrect_msg = "Assurez-vous d'inspecter les objets dans votre espace de travail après avoir créé  `horses` et `dogs`.")
success_msg("Impressionnant! Vous pouvez maintenant construire et inspecter votre espace de travail, génial!")
```

---

## Découvrir le type des données

```yaml
type: NormalExercise
key: 1866cdd202
lang: r
xp: 100
skills: 1
```

ici, il y a les 4 types de données qu'on peut avoir dans R:

- La valeur décimale `4.5` est nommée **numérique** ou  **numerics**.
- Le nombre naturel `4L` est nommé **entier** ou **integer**. L'entier est aussi numérique.
- Les valeur booliennes (`TRUE` or `FALSE`) sont nommées **logique** ou **logic**. Les lettres majuscules sont importantes; `true` and `false` ne sont pas booléens. 
- texte (ou string) sont nommées **characters**.

Noter que le texte est mis entre double quotes `"some text"`.

`@instructions`
Changer la valeur de:

- La variable `my_numeric` à `42`.
- La variable `my_character` à `"forty-two"`. Noter que les double quotes indiquent que `"forty-two"` est une caractère.
- La variable `my_logical` à `FALSE`.

`@hint`
Remplacer les valeurs dans le script avec les valeurs fournies dans l'exercice.
```
my_numeric <- 42
```
Affecter la valeur 42 à la variable `my_numeric`.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Quelle est la réponse de "universe"?
my_numeric <- 42.5

# Les doubles quotes indiquent que la variable est de type caractère
my_character <- "some text"

# Changer la valeur de my_logical
my_logical <- TRUE
```

`@solution`
```{r}
# Quelle est la réponse de "universe"?
my_numeric <- 42

# Les doubles quotes indiquent que la variable est de type caractère
my_character <- "forty-two"

# Changer la valeur de my_logical
my_logical <- FALSE
```

`@sct`
```{r}
test_object("my_numeric", 
            incorrect_msg = "Soyez sûrque vous affectez correctement une valeur à `my_numeric.`")
test_object("my_character",
            incorrect_msg = paste("Soyez sûrque vus affectez correctement la valeur à `my_character`.",
                                  "Ne pas oublier les doubles quotes et attention aux majuscules! R est sensible à la ponctuation!"))
test_object("my_logical",
            undefined_msg = "Prière de faire attention à la définition de la variable `my_logical`.",
            incorrect_msg = "Soyez sûrque vous affectez correctement la valeur à `my_logical`.") 
success_msg("Bon travail! Continuez à l'exercice suivant.")
```

---

## Retour aux pommes et aux oranges

```yaml
type: NormalExercise
key: c52153af0b
lang: r
xp: 100
skills: 1
```

Dans l'exercice précédent, nous avons additionné les variables numériques `my_apples`et `my_oranges` avec l'opérateur `+`.
Par contre, si nous voulons additionner une variable nuémrique avec un caractère, R va se plaindre.

`@instructions`
- Cliquer **Submit Answer**  et liser le message d'erreur. Essayer de comprendre pourquoi cela ne marche pas.
- Adjuster `my_oranges <- "six"` comme que R connait que vous avez 6 oranges avec une corbeille de fruit contenat 11 pièces. Cliquer **Submit Answer**.

`@hint`
Vous avez affecté une valeur numérique `6` à la variable `my_orange` au lieu d'une valeur carcatère `"six"`. Noter comment les doubles quotes sont utilisées pour indiquer que `"six"` est une carcatère.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Affecter la valeur à la variable my_apples  et l'imprimer
my_apples <- 5
my_apples       

# Affecter la valeur à la variable my_oranges et l'imprimer
my_oranges <- "six" 
my_oranges 

# Nouvelle variable qui contient le total du nombre de fruits
my_fruit <- my_apples + my_oranges 
my_fruit
```

`@solution`
```{r}
# Affecter la valeur à la variable my_apples et l'imprimer
my_apples <- 5  
my_apples  

# Affecter la valeur à la variable my_oranges et l'imprimer
my_oranges <- 6
my_oranges 

# Nouvelle variable qui contient le total du nombre de fruits
my_fruit <- my_apples + my_oranges 
my_fruit
```

`@sct`
```{r}
test_object("my_apples", incorrect_msg = "Ne pas changer le code qui affecte 5 à `my_apples`.")
test_object("my_oranges", incorrect_msg = "Changer l'affectation de la variable `my_oranges` comme il le faut, sans erreur.")
test_object("my_fruit", 
            undefined_msg = "Prière, soyez sûrde définir la variable `my_fruit`.",
            incorrect_msg = "Faites attention que vous avez la valeur correct à la variable`my_fruit`.")
test_output_contains("my_fruit", incorrect_msg = "le output ne contient pas le résultat de la somme de `my_apples` et `my_oranges`.")
success_msg("Awesome, keep up the good work!")
```

---

## Quel est ce type de données?

```yaml
type: MultipleChoiceExercise
key: 7806ca24d2
lang: r
xp: 50
skills: 1
```

Lorsque vous avez ajouté les variables contenant `5` et` "six" `, vous avez une erreur due à une discordance dans les types de données. Vous pouvez éviter ces situations embarrassantes en vérifiant préalablement le type de données d'une variable:

```
class(my_var)
```

Dans l'espace de travail (vous pouvez voir ce qu'il contient en tapant [`ls ()`] (http://www.rdocumentation.org/packages/base/functions/ls) dans la console), certaines variables ont déjà été définies. Quelle est la phrase concernant ces variables est correcte?

`@instructions`
- Les classes de `a` est `integer`, `b` est `character`, et `c` est `boolean`.
- Les classes de `a` est `character`, `b` est `character`, et `c` est `logical`.
- Les classes de `a` est `numeric`, `b` est `string`, et `c` est `logical`.
- Les classes de `a` est `numeric`, `b` est `character`, et `c` est `logical`.

`@hint`
Vous pouvez trouver le type de données de la variable `a` par exemple en tapant` class (a) `. Vous pouvez faire des choses similaires pour `b` et` c`.

`@pre_exercise_code`
```{r}
a <- 42
b <- "forty-two"
c <- FALSE
```

`@sct`
```{r}
msg1 <- "`boolien n'est pas la classe d'une valeur logique. ré-essayer."
msg2 <- "`a` est de classe numérique, Donner lui une autre valeur."
msg3 <- "`string` n'est pas une classes dans R. `character` est une classe dans R!"
msg4 <- "Joli. Allons-y d'un cran et commençons à contraindre les variables!"
test_mc(correct = 4, feedback_msgs = c(msg1, msg2, msg3, msg4))
```

---

## Coertion: Apprivoiser vos données (contrainte, pression)

```yaml
type: NormalExercise
key: c75fe45544
lang: r
xp: 100
skills: 1
```

La coertion est possible poyr transformer un type de donnée à un autre. la fonction `is.*()` permet de vérifier le type de donnée. Mais la fonction `as.*()` permet de forcer de changer de type de donnée. L'astérisque `*` est une variable qui doit être remplacer par les 4 type de données `numeric`, `character`, `ìnterger`, `logical`.

Voici un exemple:

```
var <- "3"
var_num <- as.numeric(var)
```

`var`, est une chaine de caractère (`" "`), elle est convertie à une variable numérique en utilisant [`as.numeric()`](http://www.rdocumentation.org/packages/base/functions/numeric). Le résultat est stocké dans `var_num`.

`@instructions`
- Convertir une variable logique (`logical`) `var`, à une variable `charcater` . Affecter le résultat à la variable `var_char`.
- Inspecter la classe de `var_char` en utilisant [`class()`](http://www.rdocumentation.org/packages/base/functions/class).

`@hint`
Utiliser la fonction [`as.character()`](http://www.rdocumentation.org/packages/base/functions/character) pour convertir `var` à  `character`.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Définir var
var <- TRUE

# Convertir var au type caractère: var_char


# Imprimer la classe de var_char


```

`@solution`
```{r}
# Définir var
var <- TRUE

# Convertir var au type caractère: var_char
var_char <- as.character(var)

# Imprimer la classe de var_char
class(var_char)
```

`@sct`
```{r}
test_error()
msg <- "Ne pas supprimer ou modifier la définition de la variable `var`."
test_object("var", undefined_msg = msg, incorrect_msg = msg)
test_function("as.character", "x",
              not_called_msg = "Assurez-vous d'appeler la fonction [`as.character ()`] (http://www.rdocumentation.org/packages/base/functions/character) pour convertir `var` en caractère.",
              incorrect_msg = "Avez-vous passé la bonne variable à la fonction [`as.character ()`] (http://www.rdocumentation.org/packages/base/functions/character)?")
test_object("var_char")
test_function("class", "x", 
              not_called_msg = "Soyez sûrdans l'usage de la fonction <code>class()</code> pour inspecter la classe de <code>var_char</code>.",
              incorrect_msg = "Avez-vous passé la bonne variable à la fonction <code> class () / <code>?")
success_msg("Bellissimo!")
```
