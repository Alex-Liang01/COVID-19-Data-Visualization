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

In this book, there is four plots. There is a plot of monthly new COVID-19 cases worldwide. A plot of the number of deaths and number pf cases per day where the user can selecct the Countries that they want to compare, an animated race chart of the top 15 Countries with the most COVID-19 cases cumulated over time, and a world map plot where the user can see the amount of total COVID-19 cases for a Country on a specific day per million by hovering over the Country. https://public.tableau.com/app/profile/alex6894/viz/COVID-19DataVisualization_16438789802450/Sheet1 

There is an animation plot of monthly new COVID-19 cases worldwide.
![New COVID-19 Cases](https://user-images.githubusercontent.com/95319198/148664590-3143a16a-668c-4fad-8e82-21f72ca7a442.gif)


This is a plot of log10 of number of deaths and number of cases per day where the user can select the Countries that they want to compare.
![image](https://user-images.githubusercontent.com/95319198/144782576-5239868e-f532-464b-b870-33e753c296cf.png)  

This is the race chart gif of the top 15 countries with the most COVID-19 cases each month.
![Top 15 Countries with most COVID-19 cases](https://user-images.githubusercontent.com/95319198/148664595-f3b7d6d2-b653-46e4-af7a-2c173e602a05.gif)

This is the world map gif that shows the amount of total COVID-10 cases for a Country per million each month.
![Worldwide COVID-19 Cases per million Monthly](https://user-images.githubusercontent.com/95319198/148664846-0060b123-8790-482f-a265-53222be096d6.gif)

