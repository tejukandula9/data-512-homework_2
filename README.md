# DATA 512 Homework 2
## Project Goal
The goal of this project is to explore bias in data by examining and critiquing a machine learning tool that provides article quality scores for different Wikipedia articles.  

## Project Description
For this project we look at the Wikipedia article quality scores for political figures around the world. We will be using a machine learning service called ORES to determine the quality of each article. After we recieve this data we will perform analysis of how the coverage and quality of politicians on Wikipedia vary accross the world. 

## Project Methodology
For this project we have two input files. The first has a list of politicians, their country and a link to the wikipedia article. The second has a list of countries listed by region with their total population.
First we use the MediaWiki API to get the current page revision id for each of the politicians. We then use this page revision id to pass into ORES to get the article quality score for each politician. The article quality scores are described below:

FA - Featured article

GA - Good article

B - B-class article

C - C-class article

Start - Start-class article

Stub - Stub-class article

We then do further analysis with this information which can be seen in the jupyter notebook

## Project Files
### Input Files
- politicians_by_country_SEPT.2022.csv - politicians_international_SEPT.2022.csv
  - CSV downloaded from homework instructions with a list of politicians, their country and a link to the wikipedia article
- population_by_country_2022.csv - population_by_country_2022.csv
  - CSV downloaded from homework instructions with a list of countries listed by region with their total population in millions
  - **Note:** This file has regions listed in all capital letters. All countries listed below a region are part of that region.
### Output Files
- wp_politicians_by_country.csv
  - Contains data for each politician including country, region, population, revision id and article quality score
  - **Note:** Articles that could not have an article quality score are still included in this file. The value for article quality score are just Null.
- wp_countries-no_match.txt
  - A list of countries with no match between the politicians and the populations file
  
  ## Research Implications
    Before starting to work with this data, we had a breif introduction to it in our DATA512 class. We were able to see that a political figure that became president of a country and actually made global news had a fairly low article quality score compared to a US Senator who ran for president and lost. From this breif exploratory analysis the biases I expected to find in this data is racial and even economical. I guessed that richer, more well-developed countries would have a higher proportion of high quality articles. Another expectation I had is that maybe countries with more native english speakers or higher literacy rates would have higher proportions of high quality articles on English Wikipedia
    
    From this project I was able to learn a lot about bias in data and AI. It was interesting to see how human bias can be projected and amplified in machine learning models. It was no surprise to see that european countries have a higher number of both total and high quality articles per capita. These are typically more well developed countries that meet the worlds cultural and linguistic norms. One region that was surpising to see near the top was the Carribean. 
    
    My theory on the potential bias in the ORES model is economic, cultural and linguistic. Countries that have higher economic status might have more money going into research and political development, with more time and effort being put into reviewing the articles of their political figures, thus resulting in higher scores. Culturally, the style articles are written can differ from country to country. The quality scores could be based off the norms for one type of country discounting the writing for other countries. Similarly linguistics may affect the score. Common sayings, acronyms, idioms, slang and grammar for english can be different for each country which may in turn affect the quality score. Another potential issue with the data is we look per capita, so countries with higher population are already at a disadvantage for having high per capita total articles and high quality articles.
    
    I believe the best way to supplement this dataset to continue research is by adding more political figures from more countries. For example North America is not included at all in this data set. This addition could help us further explore the theories I stated above. There were also some countries with a population of 0, if we can get the true population of these countries it will help us examine the article qualities for smaller countries. Along with that I believe examing the data going into the ORES scores would be useful. 
    
## Project Sources and Licenses
[Politicians by Nationality Wikipedia Page](https://en.wikipedia.org/wiki/Category:Politicians_by_nationality)
[World Population Data Sheet] (https://www.prb.org/international/indicator/population/table)
[ORES] (https://www.mediawiki.org/wiki/ORES)
[Wikipedia Content Assessment] (https://en.wikipedia.org/wiki/Wikipedia:Content_assessment)
[Wikipedia Info API] (https://en.wikipedia.org/wiki/Wikipedia:Content_assessment)
[Page Info Request Example] (https://drive.google.com/file/d/1Z8DqXpHmNUJ3RD7e-OOwx2WYJPIYjUPp/view?usp=sharing)
[ORES Request Example] (https://drive.google.com/file/d/1rZdBrtCe9XO4IkDWqm0A2RA-HfZCsqHh/view?usp=sharing)
