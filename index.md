# Lion King inspired meme
## Mind of a uni student

* **Code for images**
  * *3 images from web*

install.packages("magick")
library(magick)
simba_happy <- image_read("https://th.bing.com/th/id/R.436baa80684ebc2d38e8b7b40a96e7c5?rik=9RbJIBsYx%2b4kIg&riu=http%3a%2f%2fwww.fromscreentotheme.com%2fWhosWhoNala-1.jpg&ehk=0K0mGiY5oSbsVxTkzXVsU6th4i66o7TYA1Q87UvGg94%3d&risl=&pid=ImgRaw&r=0") %>%
  image_scale(400)

worried_simba <- image_read("https://th.bing.com/th/id/R.0418d78d689038f85e4ca582c7da4cf1?rik=0rVbgarT87aIAA&riu=http%3a%2f%2fimages6.fanpop.com%2fimage%2fphotos%2f33100000%2fsimba-and-sarabi-the-lion-king-33165307-999-800.jpg&ehk=sUnk58JeZNDD6PpJW7Y4ejKB53arWaaxmKZnogZ5nIQ%3d&risl=&pid=ImgRaw&r=0")%>%
  image_scale(400)

falling_lion <- image_read("https://th.bing.com/th/id/R.85add23aff32b0389e01aeaa05e83910?rik=fufAxwaklRrqBg&riu=http%3a%2f%2fimages2.fanpop.com%2fimages%2fpolls%2f278000%2f278987_1249410261885_full.jpg&ehk=rZ5JCN1i0PAzn%2fSgpr%2b3RXNhRBjQol3BVqQPh5JtFtk%3d&risl=&pid=ImgRaw&r=0&sres=1&sresct=1")%>%
  image_scale(400)
* **Code for text on side**
  * *a text for each (3) images*

happy_text <- image_blank(width = 400, height = 320, color = "#ff0000") %>%
  image_annotate(text = "Getting 2 weeks to\ndo an assignment ;)", color = "#ffffff", size = 30,
                 font = "Comic Sans", gravity = "center")

worried_text <- image_blank(width = 400, height = 310, color = "#ff0000") %>%
  image_annotate(text = "Assignment now due\nin 2 days!\n*convinced there's\nstill a lot of time*", color = "#ffffff", size = 30,
                 font = "Comic Sans", gravity = "center")

falling_text <- image_blank(width = 400, height = 320, color = "#ff0000") %>%
  image_annotate(text = "DUE IN THE\nNEXT 2 HOURS!!!", color = "#ffffff", size = 25,
                 font = "Comic Sans", gravity = "center")
first_row <- c(simba_happy, happy_text)%>%
  image_append()

sec_row <- c(worried_simba, worried_text)%>%
  image_append()

third_row<- c(falling_lion, falling_text)%>%
  image_append()

c(first_row, sec_row, third_row)%>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")
![preview](https://user-images.githubusercontent.com/101149082/159185457-b74f65e2-fd30-47cb-8aaa-293df0debb00.jpg)
