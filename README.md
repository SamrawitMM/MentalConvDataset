# MentalConvDataset
Mental conversational dataset 



Convert mental conversation json datset to csv

https://www.kaggle.com/code/mpwolke/json-mental-health-conversational/comments#2036350
library(jsonlite)
library(tidyverse)

test_1 <- jsonlite::fromJSON('intents.json', simplifyVector = FALSE,
simplifyDataFrame = TRUE, flatten=TRUE)
test_2 <- test_1$intents

glimpse(test_2)

test_3 <- test_2 |>
unnest(cols = c(responses))|>
unnest(cols = c(patterns))

write.csv(test_3, "test_4.csv")
