# Final Report

Emma Tarcson \| egt12@pitt.edu

## Table of Contents:
* [Background](#Background)
* [Data Collection](#Data-Collection)
  * [Background for data](#Background-for-data)
  * [Collecting data](#Collecting-data)
  * [Issues with Licensing](#Issues-with-Licensing)
  * [Cleaning the data](#Cleaning-the-data)
* [Analysis](#Analysis)
  * [Speech Analysis](#Speech-Analysis)
  * [Debate Analysis](#Debate-Analysis)
  * [Platform Analysis](#Platform-Analysis)
  * [Extra Analysis](#Extra-Analysis)
* [Results](#Results)
* [Conclusion](#Conclusion)

## Background
Initially, while trying to come up with an idea for this project, I did not know much about the world of data science. I did have a little bit of linguistics knowledge, though, so I decided to choose a topic that I had learned about the previous semester: Rhetorical Analysis.

I had this idea that I would use all of python's wonderful language analysis tools (love you, nltk) to determine the "effectiveness" of the kinds of persuasive language features in text. This kind of left me with no where to start, though, as I, thanks to Na Rae and Joey, could not figure out how the heck I would prove "effectiveness". The project was also pretty two-dimensional, as well: only focusing on the frequency of persuasive devices.

So, on the final night that I was able to switch project ideas, I tweaked the concept a bit.

I was already using RNC and DNC speeches as the data as it would be polarizing and I thought that the conventions would be great sources for analysis persuasion, but then I also started thinking about how those conventions would be super polarizing and I wanted to take that further. So, I focused on politics, instead of just focusing on the vague "persuasive" text thing I had going before. This allowed me to play with future analysis ideas, as well as, play with an idea that I was already curious about: if Democratic and Republican text/speech is actually all that different or do they use similar ways of getting people to their side (rhetoric). This also allowed me to go even further and start thinking about if the mode or place of persuasion (speech, debate, platform) had any effect on that.

## Data Collection
#### Background for data
2020 was a big year for politics. There was the presidential election, after all. This fact gave me a good bit of recent text I'd be able to use that all occurred within the past couple months of the year.

#### Collecting data
First are the RNC and DNC speeches. I got these off of a pretty Kaggle folder that had all speech transcripts in clean text files. The links to these can be found [here](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/data_sample/data_link.md), and the [README](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/README.md) markdown file.

Second is the debate transcripts. Links to the website URLs can be found on the [README](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/README.md) markdown file. I scraped these using scrapy, and cleaned them up a bit during that process with regex and xpath. I won't lie, this was a bit strenuous, but satisfying nonetheless. After scraping, I converted both transcripts into csv files, which can be found [here](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/tree/main/data), which just the text, speaker, and time stamps.

Third is the platforms. Links to the website URLs can be found on the [README](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/README.md) markdown file. These were easily downloadable, though I suppose I could have scraped them as well and received even better results as I did have to work with the platform data a little bit in jupyter notebook.

#### Issues with Licensing
Luckily, the data I was using was mainly in the public domain, being political text and whatnot. That being said, there were some cases where I wasn't fully able to present the data. Because the RNC and DNC speeches were from someone else, I decided to provide a link and a sample set of the data rather than pushing it all onto github. With the debates, I was worried that I wouldn't be able to use it either, but after receiving feedback from Na Rae and discussing it with reputable sources at Pitt's library, I decided to present the scraped csv files in the [data](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/tree/main/data) folder. For the platforms, once again, I was able to use them freely, but after checking the website and other information online, I found that it'd be best to keep these in a git ignored folder rather than showing them on this repository.

Licensing of my own project came after that. I decided to use [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) because it included freedom to use my project, but requires disclosing the source so that others can find and use my work. I found this important as I added information to the original data collection (political affiliation).

#### Cleaning the data
Cleaning the data took place in [this](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/dataplan.ipynb) jupyter notebook. (At the time of completing this project, nbviewer had an unhealthy backend error)

First, I took care of the RNC and DNC speeches and made a dataframe with both conventions. This included the .txt file names and transcripts, and I added political affiliations. Some people noted that there was a couple instances where some speakers couldn't be techincally considered a Republican or Democrat, but since I was more focusing on the speeches as representations of the convention that they were from, I kept them as the affiliation from the convention they attended (though I could have used this information in the analysis portion where I needed more neutral stances: see [Speech Analysis](#Speech-Analysis)). I also ended up getting rid of the .txt filenames, as well, because the affiliation was what was important not the actual person speaking. Then, I saved this dataframe to conv_speeches.csv.

Second, I worked with the debates. I striped the last few html leftovers that I couldn't fully remove during the scraping process. I then added affiliations according to the speaker, with "None" for the moderator. I was going to actually completely get rid of the moderator here, but keeping them in ended up coming in handy: see [Debate Analysis](#Debate-Analysis). I saved the affiliation column and transcript column of the two debates with both Speaker and No-Speaker rows to csv files.

Third, I imported the platforms and made a dataframe, which ended up just being two rows with ALL the text, and that made me laugh when it happened because I was for some reason not expecting it to do that, but I quickly realized I should tokenize the platforms by sentences. I probably could have done paragraphs, which makes me wonder if the results would be different, but since I mainly just used words as features for this analysis, I figured that it didn't matter. But, so I added the affiliations just like the two others and voila.

During this entire notebook, you'll noticed that I am adding full texts of the platforms, debates, and speeches to this thing called main.csv. This was entirely so that I'd have all the text in one place.

## Analysis
#### Speech Analysis
#### Debate Analysis
#### Platform Analysis
#### Extra Analysis

## Results
## Conclusion
