# Hi, everyone

Welcome to my wbsite.

Briefly introduce myself: 
* I am a student from University of Auckland and major is data science.
* My habbit is reading detective stories. 
* I have a dog and her name is Doudou, she was my 16 years old brithday gift.

## About the website

This website is about labrador dogs. The reson why I chose this topic is that I have a cute labrador, and I want to introduce labrador to more people.

## Meme of labrador

**Important thing: Why create the meme**

To show the difference about puppy labrador to adult labrador.

*The meme below is a labrador from a puppy dog to a adult dog. 
I made it by myself and it is very easy to do that, just need some steps:*

1. Find a puppy labrador image, and sclaed it
2. Create a blank square(500 * 500) and then annotate puppy labrador which is puppy labrador text square 
3. Find a adult labrador image, and sclaed it
4. Create a blank square(500 * 500) and then annotate adult labrador which is adult labrador text square
5. Put puppy labrador image and puppy labrador text square side by side and it is first row
6. Put adult labrador image and adult labrador text square side by side and it is second row
7. Add first row and second reow together


![](https://github.com/jq77y/stats220/blob/main/my_meme.png)


### Code of my meme
Below is code to create the labrador meme and useing the R package [magick](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).

```r
library(magick)

puppy_labrador <- image_read("https://i.pinimg.com/originals/dd/da/89/ddda899cbe2e18766ca1797806efe8b8.jpg") %>%
  image_scale(500)

adult_labradors <- image_read("https://i.pinimg.com/736x/05/d2/20/05d220bf723f6338d99f653070ac9a06--yellow-labs.jpg") %>%
  image_scale(500)

puppy_labradors_text <- image_blank(width = 500, 
                                    height = 500, 
                                    color = "#008000") %>%
  image_annotate(text = "puppy labrador",
                 color = "#FFFFFF",
                 size = 50,
                 font = "Impact",
                 gravity = "center")


adult_labradors_text <- image_blank(width = 500, 
                                    height = 500, 
                                    color = "#006666") %>%
  image_annotate(text = "adult labrador",
                 color = "#FFFFFF",
                 size = 50,
                 font = "Impact",
                 gravity = "center")




first_row <- c(puppy_labrador, puppy_labradors_text) %>%
  image_append()

second_row <- c(adult_labradors, adult_labradors_text) %>% 
  image_append()

final_image <- c(first_row, second_row) %>% 
  image_append(stack = TRUE)

final_image

image_write(final_image, "my_meme.png")

```

##  Some useful website to see labrador behavior.
* [Loving Your Lab](https://www.lovingyourlab.com/9-common-labrador-behavior-problems/#:~:text=Barking%2C%20digging%2C%20and%20chewing%20are,Labs%20because%20of%20their%20intelligence.) 

* [The Labrador Site](https://www.thelabradorsite.com/labrador-behaviour/)



## End
**This is the end of my website, hope you like it**
