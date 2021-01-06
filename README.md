# au554113_Iversen_Magnus
library(tidyverse)

data_til_digital_metode <- data_til_digital_metode %>%
  mutate(duration = End_date-Start_date, midyear = (End_date+Start_date)/2)
  
data_til_digital_metode %>%
  ggplot(aes(x = midyear, y = duration)) + geom_point() + 
  geom_smooth(mapping = aes(x = midyear, y = duration), method=lm) + 
  labs(title = "How long danish kings ruled over time", x = "Year ", y = "Year they ruled") +
  theme_bw() + theme(text = element_text(size = 14))

