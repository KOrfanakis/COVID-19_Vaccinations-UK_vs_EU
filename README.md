# COVID-19 Vaccination Progress: How do Countries in the EU Compare with the UK?

On the 31st of December, at 11 p.m. GMT, the United Kingdom (UK) completed its separation from the European Union (EU) with the ending of the agreed transition period. Unsurprisingly, the next controversy in the often-rocky relationship between the two entities came only a month later and concerned the availability of vaccination jabs against COVID-19 ([Source](https://news.sky.com/story/covid-19-how-does-the-uk-compare-in-europes-race-for-vaccines-amid-shortage-warning-12199325)). Moreover, the EU has also faced severe criticism regarding its vaccination efficiency, owing to burdensome paperwork, a lack of nurses, and supply shortages
([Source](https://www.nytimes.com/2021/01/05/world/europe/europe-covid-vaccinations.html)). On the other hand, the UK has been praised for its management of the vaccination rollout programme ([Source](https://uk.news.yahoo.com/german-newspaper-bild-we-envy-you-british-covid-vaccine-rollout-104131274.html)).

<br>

As the need for mass-inoculation by countries gathers pace, this notebook looks at how the **UK is faring against other countries in the EU**. I have summarised the visualisations in a PowerPoint presentation, which you can find in this repository.

<br>

## Outline

This notebook focuses on only the [27 current member states of the EU](https://en.wikipedia.org/wiki/Member_state_of_the_European_Union) plus the UK (abbreviated as '**EU/UK**' in this notebook). The comparison between countries will be based on four aspects of the vaccination process:

- The total number of vaccinations,
- The number of people vaccinated (1st dose),
- The number of people fully vaccinated (2nd dose), and
- The daily number of new vaccinations.

Apart from comparing the absolute numbers, we also need to factor in the population of each country. Therefore, each of the above features will be normalised per hundred people (for the first three features) or million people (for the daily number of vaccinations). Our analysis will also factor in parameters such as GDP per capita. Lastly, we will visualise how vaccinations progressed since the day of the first vaccination instead of actual dates (Year-Month-Day) because immunisations started at different dates for different countries.

<br>

## How to View

Since the notebook is rendered as a static HTML file in the repository, its interactive features (Plotly plots) will not be displayed. 
To view the notebook with interactive content, you can use [nbviewer](), [Kaggle](https://www.kaggle.com/korfanakis/covid-19-vaccination-progress-uk-eu-comparison) or run it locally.

**Note**: Interactive maps can not be displayed with the nbviewer. Consequently, maps will be displayed as static images using the `svg` renderer. 
To access the interactive version, please visit the notebook on [Kaggle]() or run the notebook locally after removing the `svg` rendered from the `fig.show()` command.

<br>

## Data

Our analysis requires four datasets. 

- **Geospatial Dataset** (**ne_10m_admin_0_countries.geojson**): a GeoJSON file containing geospatial data for all world countries. The dataset is extracted using Pandas' `read_csv()` method directly from [Nathaniel V. Kelso](https://github.com/nvkelso)'s [GitHub repository](https://github.com/nvkelso/natural-earth-vector).

- **Vaccination Dataset** (**country_vaccinations.csv**): a CSV file that stores information about how vaccinations progress in many countries. Data were collected from [Our World in Data](https://ourworldindata.org/)'s GitHub [repository](https://github.com/owid/covid-19-data) for COVID-19, merged and uploaded on [Kaggle](https://www.kaggle.com/gpreda/covid-world-vaccination-progress) by [Gabriel Preda](https://www.kaggle.com/gpreda).

- **GDP Dataset** (**eucountrydatawb_csv.csv**): a CSV file containing information about a country's population and GDP. The dataset is extracted using Pandas' `read_csv()` method directly from [DataHub](https://datahub.io/opendatafortaxjustice/eucountrydatawb)'s website.

- **Flags Dataset** (**countries_continents_codes_flags_url.csv**): The final CSV file contains a URL for the flag of most countries. The dataset is created by [AndresHG](https://www.kaggle.com/andreshg) and is retrieved from [Kaggle](https://www.kaggle.com/andreshg/countries-iso-codes-continent-flags-url).

<br>

## Resources Used

Python Version: 3.7 <br>
Jupyter Notebook Version: 5.7.8 <br>
Packages: pandas, geopandas, plotly, seaborn, matplotlib, pywaffle, and numpy
