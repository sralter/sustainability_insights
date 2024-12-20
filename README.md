# sustainability_insights
A project consisting of an executive summary with figures and a [Tableau Public Story](https://public.tableau.com/app/profile/samuel.alter/viz/sustainability_analysis/EmissionsAnalysis). This project centered on deriving insights from a detailed emissions dataset sourced from [Climate TRACE](https://climatetrace.org/).

## Summary
* This project used the following frameworks – <mark>Pandas</mark>, <mark>NumPy</mark>, <mark>Matplotlib</mark>, <mark>DuckDB’s</mark> <mark>SQL</mark> functionality within Python, and <mark>Tableau</mark> – to produce the following:
  * Performed EDA on greenhouse gas emissions dataset from [Climate TRACE](https://climatetrace.org/).
    * Created 15 figures:
      * 5 bar graphs
      * 1 pie chart
      * 4 global heatmaps
      * 5 correlation matrices
  * Created a [Tableau Public Story](https://public.tableau.com/app/profile/samuel.alter/viz/sustainability_analysis/EmissionsAnalysis) consisting of two dashboards
  * Wrote a three-page executive summary of the work, which you can read below.

## Introduction
This project explores datasets from Climate TRACE containing greenhouse gas (GHG) emissions from coal mining, and gleans insights from them. Climate TRACE is an organization that uses independently-verified data, sourced and derived from advanced technologies like satellite imagery, enhanced with machine learning. Climate TRACE and the values and needs of any sustainability-minded person or company are closely aligned; the work described here will show the promise of using Climate TRACE’s data to help everyone make informed, sustainable decisions.

## Methods
There were three main tables that were used for this project found [here](https://climatetrace.org/data) and are listed below:
1. GHG emissions sourced from coal mining operations, grouped by year (2015-2022) and country
2. A table highlighting individual sources for emissions (i.e., individual mines) with other relevant data like country included, and
3. A table listing the corporate owners of those mines along with their revenue.

An extensive exploratory data analysis (EDA) was performed using Python and Tableau to understand the relationships of the data. Figures created from the EDA can be found in the Appendix section below. I used <mark>Pandas</mark>, <mark>NumPy</mark>, and <mark>Matplotlib</mark> to manipulate and plot the data, and used <mark>DuckDB’s</mark> <mark>SQL</mark> functionality within Python to manipulate the tables further before being plotted. The Python notebook shows the steps taken to create the figures.

## Insights
### Broader Context
Before we focus on the companies operating the mines, we should take a moment to learn about the global trends in coal mine emissions. Global emissions of methane due to coal mining were on a steady increasing trajectory, going from about 42.2 million metric tons in 2015 to 51.5 million metric tons in 2022, an increase of about 20% ([**Figure 1**](https://github.com/user-attachments/files/16899994/due20240829_ch4.pdf)):

![Figure 1](https://github.com/user-attachments/assets/33fae6dd-6247-42b7-922f-ab904de55941)

In terms of the biggest emitters globally, for all the years in the dataset, China, USA, Australia, and Russia claim the top four spots respectively ([**Figure 2**](https://github.com/user-attachments/files/16900017/due20240829_total_country_emission_sources_log.pdf)). China, the first on this list, emits about ten times as much methane emissions compared to the number two, USA:

![Figure 2](https://github.com/user-attachments/assets/3a1b9016-c10a-42cc-82fd-256c35ae82ba)

China and USA are also number one and two, respectively, on total emissions sources ([**Figure 3**](https://github.com/user-attachments/files/16900009/due20240829_country_emission_sources_log.pdf)):

![Figure 3](https://github.com/user-attachments/assets/e2be1258-130a-4a03-ac1c-943c9c0acdeb)

We are starting to see a pattern emerge of which countries emit the most, which is validated in the news stories we read on what seems to be on a near-daily basis.

The countries that have little to no mines include Argentina, Bangladesh, Spain, Nepal, and Egypt. In terms of emissions sources, solely underground- and solely surface-based emissions make up almost 98% of all emissions sources, with the other few percentage points going to mines with both underground and surface areas, and refuse ([**Figure 4**](https://github.com/user-attachments/files/16900029/due20240829_emission_sources_pie.pdf)):

![Figure 4](https://github.com/user-attachments/assets/df5c8386-4221-41b9-bd0e-6677b0879c0c)

A global overview of the countries included in the dataset with measurable emissions is found in [**Figure 5**](https://github.com/user-attachments/files/16900037/due20240829_global_ch4_emissions.pdf):

![Figure 5](https://github.com/user-attachments/assets/8bdab84c-832a-4de7-a46c-6dcf7b1ac7a9)

An analysis of correlations (categorical and continuous data respectively) in the emissions sources dataset yields some minor insights, like a mild positive correlation (0.44) between source type and country ([**Figures 6**](https://github.com/user-attachments/files/16900040/due20240829_emissions_sources_categorical_correlation.pdf) and [**7**](https://github.com/user-attachments/files/16900045/due20240829_emissions_sources_numerical_correlation.pdf)):

![Figure 6](https://github.com/user-attachments/assets/b18ecf34-a706-4017-84a7-8f814005885f)
![Figure 7](https://github.com/user-attachments/assets/7b2dcee0-9858-450d-8865-b9a29949cc60)

The distribution of coal mines’ emissions roughly follows the broader lithological distribution of major global coal beds, so we can expect to see coal mines in the eastern half of the US, in parts of central and eastern Asia, South Africa, and eastern Australia, for example ([**Figure 8**](https://github.com/user-attachments/files/16900062/due20240829_density_map.pdf)):

![Figure 8](https://github.com/user-attachments/assets/e08b27c4-2d7c-470f-9bc5-c1c4b5cbb90e)

The correlations in the ownership dataset show nothing too revealing beyond the expected correlation between capacity and activity ([**Figures 9**](https://github.com/user-attachments/files/16900068/due20240829_ownership_categorical_correlation.pdf) and [**10**](https://github.com/user-attachments/files/16900065/due20240829_ownership_numerical_correlation.pdf)).):

![Figure 9](https://github.com/user-attachments/assets/af0c81cc-c2e5-402d-9889-91ce7036dafb)
![Figure 10](https://github.com/user-attachments/assets/143a4ccc-954b-4b55-bd0d-3de0d72020e6)

### Parent Company-Focused Insights
<mark>Note: the following refers to the Tableau Public Story which can be found [here](https://public.tableau.com/app/profile/samuel.alter/viz/sustainability_analysis/EmissionsAnalysis)</mark>

With the overall coal mine emissions picture understood, let us turn our attention towards the main focus of this project: the companies that own these mines. If we want to promote sustainable business practices, it is important that we look at the companies running their mining operations. As stated, this section of the analysis was completed in Tableau. I created two dashboards to focus on two categories: 1) the top twenty companies whose holdings are the most polluting, and 2) the bottom twenty companies whose holdings are the least polluting. 

The patterns observed in the global context are largely replicated here, with Chinese and Australian companies being the most emissive. I found it interesting to look at revenue for these heavy emitters, and found that there was a diversity of countries represented — though Chinese companies were still the most common heaviest polluters found within the top twenty revenue group.

Analyzing the bottom twenty companies involved more legwork as I opted to filter out the companies who did not have any emissions. It is not practical to have a measured emission of zero, this instead must represent a lack of data for those companies. In this group, we see various countries here, with Myanmar-based companies holding six of the twenty slots. The revenue for these lower-emitting companies was not always readily available, though we see an extreme outlier of Norway in the form of the Ministry of Trade and Industry being very profitable compared to the others. The mines that comprise the bottom twenty group include those from Indonesia, India, New Zealand, and the Philippines.

### Additional Data Source: Iron Mining Emissions Data
Using the mineral extraction data downloaded from the Climate TRACE website, I opted to focus on iron mining emissions. Although it is not a perfect correlation, I thought that iron deposits could be found in places that are rich in coal. The other minerals included in the download package from Climate TRACE included copper and bauxite. From my geology background, I know that copper and bauxite are not usually found in places with coal beds. I did explore other data sources, like forest clearing, but the constraints that I put this project under necessitated me using data that was more readily manipulatable.
Similar figures to the ones created for the broader context section above can be found in **Figures 11** through **15** below. We can see that contrary to methane emissions, CO2 emissions dropped by about 30% in 2022 compared to the highest year in the dataset, 2019. The usual big emitters are represented in the iron mining emission data as well, though the order of the top five most emitting is India, China, Brazil, Russia, and Australia. USA is sixth.

[**Figure 11:**](https://github.com/user-attachments/files/16919975/due20240829_iron_co2.pdf)

![Figure 11](https://github.com/user-attachments/assets/ea34dae0-c021-47a0-876c-5386e9adc6da)

[**Figure 12:**](https://github.com/user-attachments/files/16919995/due20240829_total_country_emission_sources_log_iron.pdf)

![Figure 12](https://github.com/user-attachments/assets/03b4ba45-734b-492f-928b-694888639567)

[**Figure 13:**](https://github.com/user-attachments/files/16919996/due20240829_global_co2_emissions_iron.pdf)

![Figure 13](https://github.com/user-attachments/assets/25b2608b-cd0d-4f48-8b0f-7199fa30a08b)

[**Figure 14:**](https://github.com/user-attachments/files/16920001/due20240829_density_map_iron.pdf)

![Figure 14](https://github.com/user-attachments/assets/30823831-cd3e-4b3f-8a47-d0174ae376cd)

[**Figure 15:**](https://github.com/user-attachments/files/16919999/due20240829_ownership_numerical_correlation_iron.pdf)

![Figure 15](https://github.com/user-attachments/assets/f1a64900-540e-4f5f-9093-6310f46db27b)

Was my hypothesis correct? Did iron ore deposits correlate with coal deposits? Although **Figure 14** suggests that it is correct, the true picture may have another explanation: We may be observing a quirk in how minerals are distributed in the earth’s crust. There are [numerous](https://www.reuters.com/markets/commodities/chinas-rare-earths-dominance-focus-after-mineral-export-curbs-2023-07-05/) [articles](https://www.jstor.org/stable/resrep00311?searchText=Chinese+rare+earth+geology&searchUri=/action/doBasicSearch?Query=Chinese+rare+earth+geology&so=rel&ab_segments=0/basic_search_gsv2/control&refreqid=fastly-default:bb962a346827d9e1fc6b6a94dea225ef&seq=1) [discussing](https://www.jstor.org/stable/resrep23660?searchText=Chinese+rare+earth+geology&searchUri=/action/doBasicSearch?Query=Chinese+rare+earth+geology&so=rel&ab_segments=0/basic_search_gsv2/control&refreqid=fastly-default:bb962a346827d9e1fc6b6a94dea225ef) the geopolitics of rare earth minerals’ distribution, for example, and China is blessed with rich deposits of many of these. We might also be able to witness the difference in sustainable priorities among nations, and therefore their companies. While the USA is a big emitter of GHGs, some recent administrations have taken steps to reduce the USA’s contribution. The same level of effort may not be there in other countries. Norway, for example, seems to have struck a better balance than most with their revenue and emissions.

## Discussion
It goes without saying that this project should in no way be used for investing advice, nor should it be used to inform a company’s — let alone a country’s — GHG emission reduction plan. What this exercise does show is that ClimateTRACE is able to highlight companies that are at the forefront — or lagging behind their peers — of sustainability. I demonstrated here that no mining company can eliminate all of their GHG emissions, but some appear to do it better than others. The home country where the company is based looks like it has a large influence on the emissions behavior of the company. 

Just as with the organic food movement, the finance industry should adopt these same principles to create an [“organic finance”](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2696448) system, to allow for transparency and real-economy-based products. As part of that, especially in a warming world, people want to try and make a difference in any way that they can. Investing in sustainable companies, or entities that are better than their peers, are good steps that people and entities should take.

### Questions and Potential Future Work
This project brought up many questions and showed the way towards future projects:
* What are the largest-emitting companies doing that causes them to pollute so much?
  * Additionally, what are the companies doing that have lower emissions?
  * Is it simply a measure of scale? Future work could help disentangle this question.
* If there was more time, I would look into the entities on the top twenty list and bottom twenty list.
  * What are the companies doing in terms of their communities that they operate in?
  * Are there other metrics beyond emissions that we can tie to the companies?
* Using more data sources.
  * I have a personal interest in geospatial information. If there was more time, I would attempt a deeper geospatial analysis of the mining companies and their relationship to their surroundings, not just for their community but also for the natural environment, like investigating the case of [mountaintop removal mining practices](https://www.jstor.org/stable/41263246).
* A [recent article](https://www.nytimes.com/2024/08/28/climate/canada-wildfires-emissions-carbon.html) from the New York Times described a study that showed that the 2023 Canadian wildfires, if they were a country, would be fourth on the list of biggest emitters that year. I have a [previous project](https://github.com/sralter/brainstation_2023_ds_capstone) where I trained a model to predict whether a location will burn based on its satellite image and topographic information (aspect, elevation, and slope). I imagine that for Climate TRACE it can be difficult to figure out where the emissions are coming from, and so a future project could be focused on increasing the accuracy of where one attributes the source of emissions.
