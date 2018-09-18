1. How many vowels are there in the names of USA States?

library(stringr)
library(readxl)
US <- read_xlsx(file.choose())  
View(US)
states <- c(US$STATES)
vowels = c("a", "e", "i", "o", "u")
num_vowel = vector(mode = "integer", length = 5L)
for (j in seq_along(vowels)) {
  num_aux = str_count(tolower(states), vowels[j])
  num_vowel[j] = sum(num_aux)
}
num_vowel
names(num_vowel) = vowels

# Result

> num_vowel
 a  e  i  o  u 
61 28 44 36  8 

2. Visualize the vowels distribution.

barplot(num_vowel, main = "Number of vowels in US State Names", ylim = c(0,70), width = 1, xlim = c(0,20))


