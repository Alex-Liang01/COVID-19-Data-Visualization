# COVID-19-Data-Visualization

The COVID-19 dataset I am using is from Our World in Data. https://github.com/owid/covid-19-data/tree/master/public/data 

## Tidying data

I tidied the data in R by removing any columns that have only NA values and renamed the locations variable into Country so that Tableau would recoginize the variable as a Country. I then saved the dataframe to the output file Covid-Clean.csv so that I could use it in Tableau.  

```
w<- read_csv("https://covid.ourworldindata.org/data/owid-covid-data.csv")%>%filter(!is.na(new_cases_smoothed))
w=w[,colSums(is.na(w))!=nrow(w)]
w=w%>%rename(Country=location)
write.csv(w,"CovidCleanW.csv",row.names = FALSE)
```
Using Tableau, I created these visualizations of the COVID-19 data up to date to December 1, 2021.

This is an animation plot of monthly new COVID-19 cases worldwide. https://public.tableau.com/app/profile/alex6894/viz/Book1_16384946591580/Sheet1?publish=yes

![image](https://user-images.githubusercontent.com/95319198/144780955-cfdd70c2-9cbc-4ab7-8539-1933d2ff49da.png)

In this next book, there is three plots. A plot of the number of deaths and number pf cases per day where the user can selecct the Countries that they want to compare, an animated race chart of the top 15 countries with the most COVID-19 cases cumulated over time, and a world map plot where the user can see the amount of total COVID-19 cases for a Country on a specific day per million by hovering over the Country. https://public.tableau.com/app/profile/alex6894/viz/Book2_16385022616680/Sheet3

This is a plot of log10 of number of deaths and number of cases per day where the user can select the Countries that they want to compare.
![image](https://user-images.githubusercontent.com/95319198/144781866-2d024689-fc4f-4372-8178-6630dff941d2.png)

This is the race chart of the top 15 countries with the most COVID-19 cases on September 17, 2021.
![image](https://user-images.githubusercontent.com/95319198/144782407-ea87e69b-179f-4443-8844-781c26b953ec.png)


This is the world map plot that shows the amount of total COVID-10 cases for a Country per million
![image](https://user-images.githubusercontent.com/95319198/144782357-1ab6181a-dfae-40fb-9a1a-e5cc0b3c08bf.png)

