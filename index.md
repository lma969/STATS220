# 你好 everyone and welcome to my test website ≧◡≦
## About me:
1. I am currently a 2nd year student studying at the [University of Auckland](https://www.auckland.ac.nz/en.html?gclid=CjwKCAjwoduRBhA4EiwACL5RP6MthljPRKcc8PhTY_jxO_J6JM9hHi7AhzhLUtSszSO7zxLNJFda4RoCrooQAvD_BwE&gclsrc=aw.ds)
2. My family is from China, but I grew up in New Zealand 
3. I love coffee and bubble tea
<img src="https://cdn.pixabay.com/photo/2018/07/18/07/56/drink-3545791__340.jpg" width="250" height="280" /> 
<img src="https://cdn.pixabay.com/photo/2017/12/17/21/44/coffee-3025022_1280.jpg" width="250" height"300" />

5. I have 2 cats, one called snoopy and the other called Aries
6. One of my favourite quotes are:
      * *"Happiness is not by chance, but by choice"* **and**
      *  *"Life goes on"*

### Below is a meme I made using the R package [{Magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html)
<img src="https://github.com/lma969/STATS220/blob/main/my_meme.png" width="500" height="500" />

**The moivation for my meme** was from my 2 cats, but at the same time it was also becuase I enjoy STATS220 lectures more than my other courses at the moment. STATS220 lectures are always very interesting and engaging for me, and I love my lecturer [Anna Fergusson](https://unidirectory.auckland.ac.nz/profile/a-fergusson). I think my meme is unique because my friends tell me that I have bad humour and react to things very slowly, so my meme probably isn't as funny compared to the others. 
### Here is the R code I used to make the meme
```r
library(magick)

sleepy_cat <- image_read("https://cdn.pixabay.com/photo/2018/08/06/23/05/cat-3588643_1280.jpg") %>%  
  image_scale(500)
awake_cat <- image_read("https://cdn.pixabay.com/photo/2019/09/08/16/23/ginger-4461355_1280.jpg") %>%
  image_scale(500)

first_text <- image_blank(width = 500, 
                          height = 500, 
                          color = "#000000") %>%
  image_annotate(text = "STATS lectures",
                 color = "#FFFFFF",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

second_text <- image_blank(width = 500, 
                         height = 500, 
                         color = "#000000") %>%
  image_annotate(text = "Other lectures",
                 color = "#FFFFFF",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

first_row <- c(sleepy_cat, second_text) %>%
  image_append()

second_row <- c(awake_cat, first_text) %>%
  image_append()

meme <- c(second_row, first_row) %>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")
```

