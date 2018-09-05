library("tidyverse")
str(surveys)
#select columns
select(surveys,species_id,weight)
#select rows
filter(surveys, year==1995)
# PIPES: %>% 

surveys %>% 
  filter(year==1995) %>% 
  select(species_id,weight) 
  
  
  #select only the rows that have species weight less
  #than 5, then select only the species id, sex
  #weight
filter(weight<5) %>% 
  select(species_id)
#create new column 
  #mutate()
  
surveys %>% 
  filter(weight < 5) %>% 
  select()
  
surveys %>% 
  filter(!is.na(weight)) %>% 
  mutate(weight_kg=weight/1000,weight_kg2=weight_kg*2) %>% 
  head()




surveys %>% 
  group_by(sex) %>% 
  summarise(mean_weight=mean(weight,na.rm=TRUE))


summarise_two <- surveys %>% 
  filter(!sex=="") %>% 
  filter(!is.na(weight)) %>% 
  group_by(sex,species_id) %>% 
  summarise(mean_weight=mean(weight))

#using the previous command
#remove the missing values first (using filter), and re-run

summarise_two <- surveys %>% 
  filter(!sex=="") %>% 
  filter(!is.na(weight)) %>% 
  group_by(sex,species_id) %>% 
  summarise(mean_weight=mean(weight),min_weight=min(weight),max_weight=max(weight))

#counting
surveys %>% 
  filter(!sex=="") %>% 
  count(sex,species) 

surveys %>% 
  filter(!sex=="") %>% 
  count(sex,species) %>% 
  arrange(species,desc(n))

surveys %>% 
  filter(!sex=="F") %>% 
  count(sex,species) %>% 
  arrange(species,desc(n)) 
