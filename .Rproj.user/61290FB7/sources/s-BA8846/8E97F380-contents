install.packages("dplyr")
library(dplyr)

msleep <- msleep_ggplot2
count(x = msleep)
names(msleep)
head(msleep)

number
summary(msleep)

#count number of observations
msleep %>% 
  count()
count(msleep)

#Select the column **sleep_total**
msleep %>% 
  select(sleep_total)

#Select all the columns starting with **sl**
select(msleep, starts_with("sl")) #or
msleep %>% 
  select(starts_with("sl"))

#summarise mean sleep_total
summarise(msleep, mean(sleep_total)) #or
msleep %>% 
  summarise(mean(sleep_total))

#vore and sleep_total
g_msleep <- group_by(msleep,vore)
summarise(.data=msleep, mean(sleep_total))

####average sleep_total of eacht type
msleep %>% 
  group_by(vore) %>% 
  summarise(mean(sleep_total))

#Filter the animals that sleep more than 2 hours
filter(msleep, sleep_total>2) #or
msleep %>% 
  filter(sleep_total>2)

#Filter the animals that sleep more than 2 hours or less than 19 hours
msleep %>% 
  filter(sleep_total>2 | sleep_total<19)

#Filter the animals that sleep more than 2 hours and less than 19 hours
msleep %>% 
  filter(sleep_total>2 & sleep_total<19)

#Filter the that sleep between 2 and 19 hours, and they are NOT domesticated
msleep %>% 
  filter(sleep_total>2 & sleep_total<19, conservation != "domesticate")

#Check if your filter is filtering `NA` for the variable **conservation**. If not, filter them.
msleep %>% 
  na.omit %>% 
  filter(sleep_total>2 & sleep_total<19, conservation != "domesticate")

#create a new column with their brain-to-body mass ratio (**brainwt** / **bodywt**)
msleep2 <- msleep %>% 
  na.omit %>%
  mutate(brain.to.body.mass.ratio = brainwt / bodywt)

#Summarize the information with the mean of brain-to-body variable for each level of the **vore** variable.
msleep2 %>% 
  group_by(vore) %>% 
  summarise(mean(brain.to.body.mass.ratio))
msleep2

#Add a column with the counter for observations for each row with `n()`
msleep3 <- msleep2 %>% 
  mutate(counter = n())
msleep3

#us3 the function `arrange()` to order the information. 
## arrange by name, genus, vore, order, in this order
msleep4 <- msleep3 %>% 
  arrange(name, genus, vore, order)
msleep4

## arrange by sleep_total, from low to high
msleep5 <- msleep3 %>% 
  arrange(sleep_total)
msleep5