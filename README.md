# COVID-19-Data-Visualization

The COVID-19 dataset I am using is from Our World in Data. https://ourworldindata.org/coronavirus  

Hannah Ritchie, Edouard Mathieu, Lucas Rodés-Guirao, Cameron Appel, Charlie Giattino, Esteban Ortiz-Ospina, Joe Hasell, Bobbie Macdonald, Diana Beltekian and Max Roser (2020) - "Coronavirus Pandemic (COVID-19)". Published online at OurWorldInData.org. Retrieved from: 'https://ourworldindata.org/coronavirus' [Online Resource]

## Tidying data

I tidied the data in R by removing any columns that have only NA values and renamed the locations variable into Country so that Tableau would recoginize the variable as a Country. I then saved the dataframe to the output file Covid-Clean.csv so that I could use it in Tableau.  

```
w= read_csv("https://covid.ourworldindata.org/data/owid-covid-data.csv")%>%filter(!is.na(new_cases_smoothed))
w=w[,colSums(is.na(w))!=nrow(w)]
w=w%>%rename(Country=location)
write.csv(w,"CovidCleanW.csv",row.names = FALSE)
```
## Plots
Using Tableau, I created these visualizations of the COVID-19 data up to date to December 1, 2021.

This is an animation plot of monthly new COVID-19 cases worldwide. https://public.tableau.com/app/profile/alex6894/viz/Book1_16384946591580/Sheet1?publish=yes
![image](https://user-images.githubusercontent.com/95319198/144782655-04fd9532-b0a3-4499-9cb5-2c70bda3449a.png)  


In this next book, there is three plots. A plot of the number of deaths and number pf cases per day where the user can selecct the Countries that they want to compare, an animated race chart of the top 15 Countries with the most COVID-19 cases cumulated over time, and a world map plot where the user can see the amount of total COVID-19 cases for a Country on a specific day per million by hovering over the Country. https://public.tableau.com/app/profile/alex6894/viz/Book2_16385022616680/Sheet3

This is a plot of log10 of number of deaths and number of cases per day where the user can select the Countries that they want to compare.
![image](https://user-images.githubusercontent.com/95319198/144782576-5239868e-f532-464b-b870-33e753c296cf.png)  

This is the race chart of the top 15 countries with the most COVID-19 cases on September 17, 2021.
![image](https://user-images.githubusercontent.com/95319198/144782407-ea87e69b-179f-4443-8844-781c26b953ec.png)  

This is the world map plot that shows the amount of total COVID-10 cases for a Country per million
![image](https://user-images.githubusercontent.com/95319198/144782357-1ab6181a-dfae-40fb-9a1a-e5cc0b3c08bf.png)

