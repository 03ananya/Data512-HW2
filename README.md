# Data512-HW2

This repository contains the Homework 2 for DATA 512 Human Centered Data Science

Goal : Considering Bias in Data
The goal of this assignment is to explore the concept of bias in data using Wikipedia articles. This assignment will consider articles on political figures from different countries. 

Data Source
The input data files given in this repository are:
 - [politicians_by_country.SEPT.2022.csv](https://docs.google.com/spreadsheets/u/0/d/1Y4vSTYENgNE5KltqKZqnRQQBQZN5c8uKbSM4QTt8QGg/edit)
 - [population_by_country_2022.csv](https://docs.google.com/spreadsheets/u/0/d/1POuZDfA1sRooBq9e1RNukxyzHZZ-nQ2r6H5NcXhsMPU/edit)

In addition to these, web scraping has been performed to wikipedia pages -politicians wikipedia pages and population) web pages
The datasource endpoints are licensed under the [CC-BY-SA 3.0]( CC-BY-SA 3.0 and GFDL licenses) and [GFDL licenses](CC-BY-SA 3.0 and GFDL licenses). ORES is a machine learning tool that can provide estimates of Wikipedia article quality. Data description for the article quality variable is as given below:
 - FA - Featured article
 - GA - Good article
 - B - B-class article
 - C - C-class article
 - Start - Start-class article
 - Stub - Stub-class article
 
 API links:
 - [ORES API](https://www.mediawiki.org/wiki/ORES)
 - [Wikiedia REST API](https://www.mediawiki.org/wiki/Wikimedia_REST_API)


Repository Structure:
```bash
.
├── DATA-512-HW2.ipynb
├── README.md
├── LICENSE
├── politicians_2022.xlsx
├── population_2022.xlsx
├── Output files
│   ├── wp_countries-no_match.txt
│   ├── wp_politicians_by_country.csv
├── requirements.txt

```
## Output Files
wp_countries-no_match.txt - Text file that contains countries where population dataset does not have an entry for the equivalent Wikipedia country, or vice-versa.
wp_politicians_by_country.csv - CSV file containing infromation for contries containing population and politician details for which a response was found.

## Issues and Special Considerations
1. There are duplicate records in the politicians csv file given. As a part of pre-processing, the duplicate records have been removed.
2. Because the population is given in millions, we see that the population of some countries shows as zero because of being rounded off. 
3. The regions with populations given as the sum of populations of the countries in that region are removed and the data is brought at a country level, while being mapped to the region with the lowest hierarchy.

## Issues and Special Considerations
There are duplicate records in the politicians csv file given. As a part of pre-processing, the duplicate records have been removed.
Because the population is given in millions, we see that the population of some countries shows as zero because of being rounded off. 
The regions with populations given as the sum of populations of the countries in that region are removed and the data is brought at a country level, while being mapped to the region with the lowest hierarchy.

## Research Implications
The main point that the research analysis is trying to drive is that of the implicit bias in data or analysis that can get included in any stage of the process - data, collection, model design, variable representation to name a few. And the source of these biases could be demographic, gender, cultural prejudices, literacy rates etc.  
Here, we calculate the articles per capita of all countries based on the given population data and articles scores as scraped on the wikipedia pages corresponding to these articles. The point of contention now is whether this is a reliable metric given the inherent bosses in the data. By definition, the per capita number of articles is dependent on the country’s population. The countries with higher population tend to have lower per capita articles, because the number of articles would not increase in accordance to the increase in population when we compare a lesser populated country with a more populated country.
Also, one would expect that the article quality might be better in native English speaking countries, pointing to a linguistic bias. These biases and inconsistencies lead us to be wary of using these results in our analysis going forward. One thing I found really surprising was that some of the biggest English speaking countries were in the list of countries for which we did not find a response when we tried to find an ores score for them.
 
 - One of the obvious things here is that these are all Wikipedia articles in one language - English. This is one possible source of bias because some local politicians would have pages in their native language instead of English. 
 - In addition to linguistic bias, I also found bias introduced due to some mathematical computation happening while collecting data. Or pre-processing the data. One such example is the rounding down of the populations of certain countries to 0.
There was also some issue with certain names because they had characters not supported by Wikipedia or Python very well. There was manual intervention necessary to ensure this does not increase the bias in our base data.
 - While Wikipedia is a great source of information in most scenarios, one should be wary of using the final analysis in an inappropriate context. It is not representative of the world as a whole, and you need to make certain assumptions and take care of the considerations mentioned above.
Can you think of a realistic data science research situation where using this data (to train a model, perform a hypothesis-driven research, or make business decisions)  = As mentioned in the text above, this data and the analysis performed here should only be used while keeping in mind the inherent limitations. If this data is used to predict the popularity of the politicians in their respective countries, it might lead to erroneous predictions because of linguistic bias. 
 


## Research Implications
The main point that the research analysis is trying to drive is that of the implicit bias in data or analysis that can get included in any stage of the process - data, collection, model design, variable representation to name a few. And the source of these biases could be demographic, gender, cultural prejudices, literacy rates etc. 
Here, we calculate the articles per capita of all countries based on the given population data and articles scores as scraped on the wikipedia pages corresponding to these articles. The point of contention now is whether this is a reliable metric given the inherent bosses in the data. By definition, the per capita number of articles is dependent on the country’s population. The countries with higher population tend to have lower per capita articles, because the number of articles would not increase in accordance to the increase in population when we compare a lesser populated country with a more populated country.
Also, one would expect that the article quality might be better in native English speaking countries, pointing to a linguistic bias. These biases and inconsistencies lead us to be wary of using these results in our analysis going forward.


