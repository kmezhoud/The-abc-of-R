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
Au niveau de l'**éditeur** à votre droite, vous pouvez taper votre code pour résoudre l'exercice. Dance notre cas nous avons `3 + 4` et `demo("graphics")`.

Pour mieux comprendre le code, il est possible de faire des commentaires explicatifs pour chaque ligne de code. Le commentaire doit être précédé par un `#`. Ainsi, il ne sera pus considéré comme un code à lire et à interpréter.

Le output du code R est visualisé dans la **console** en bas à droite. Le graphe est visualisé en haut à droite.

`@instructions`
1. Click Submit Answer and see how the console now shows you the executed R code: the solution `7` appears as the sum of `3` and `4`. In its most basic form R can thus be used as a calculator or to generate plots, but there's much more ;-).
2. Use the arrows to browse through some cool visualizations generated with R, and shown here in upper right corner. Note that you can make the graph window larger, if you would like to have a closer look.
`@hint`
Just click the Submit Answer button on the right.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r eval=FALSE}
# This  is the editor and the part below the white line is called the console.

# The  hashtag is used to add comments

# Show some demo graphs generated with R
demo("graphics")

# Calculate 3+4
3+4
```

`@solution`
```{r eval:FALSE}
#Just click the Submit Answer button!

# This  is the editor and the part below the white line is called the console.

# The  hashtag is used to add comments

# Calculate 3+4
3+4

# Show some demo graphs generated with R
demo("graphics")

```

`@sct`
```{r eval=FALSE}
DM.result <- TRUE
```
---
## More movies

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: d94bc614aa
```

In the previous exercise, you saw a dataset about movies. In this exercise, we'll have a look at yet another dataset about movies!

A dataset with a selection of movies, `movie_selection`, is available in the workspace.

`@instructions`
- Check out the structure of `movie_selection`.
- Select movies with a rating of 5 or higher. Assign the result to `good_movies`.
- Use `plot()` to  plot `good_movies$Run` on the x-axis, `good_movies$Rating` on the y-axis and set `col` to `good_movies$Genre`.

`@hint`
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

`@pre_exercise_code`
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code
load(url("https://s3.amazonaws.com/assets.datacamp.com/course/teach/movies.RData"))
movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"), c("Genre", "Rating", "Run")]

# Clean up the environment
rm(Movies)
```

`@sample_code`
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection


# Select movies that have a rating of 5 or higher: good_movies


# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre

```

`@solution`
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection
str(movie_selection)

# Select movies that have a rating of 5 or higher: good_movies
good_movies <- movie_selection[movie_selection$Rating >= 5, ]

# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre
plot(good_movies$Run, good_movies$Rating, col = good_movies$Genre)
```

`@sct`
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

test_object("good_movies")

test_function("plot", args = "x")
test_function("plot", args = "y")
test_function("plot", args = "col")

test_error()

success_msg("Good work!")
```