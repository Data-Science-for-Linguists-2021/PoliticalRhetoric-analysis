#### Progress Report

> **First Entry** 02/18/21
- created the term project repository
- found more sources for possible datasets, also considered new topic choices
- worked on and cleaned up my project plan

> **First Project Report** 03/04/2021
- To start this report, I changed my project plan slightly to focus less on the effectiveness because I was getting stuck there, and instead went ahead and decided to focus on groups using rhetoric.
- Downloaded two datasets on kaggle.com that had transcripts of [RNC](https://www.kaggle.com/christianlillelund/2020-republican-convention-speeches) and [DNC](https://www.kaggle.com/christianlillelund/2020-democratic-convention-speeches) speeches. They were in public domain.
- Next I found recent debate transcripts on rev.com and scraped the contents. (I put the scraper into .gitignore for right now, but might take it out once I clean up my project space more) The first was the [VP debate with Page](https://www.rev.com/blog/transcripts/kamala-harris-mike-pence-2020-vice-presidential-debate-transcript) and [Presidential debate with Welker](https://www.rev.com/blog/transcripts/donald-trump-joe-biden-final-presidential-debate-transcript-2020). For these, I used regular expressions to extract the content and wrote each to a csv file with speaker info, time_stamps, and the text.
- I created a [jupyter notebook](https://github.com/Data-Science-for-Linguists-2021/RhetoricalFactor-analysis/blob/main/dataplan.ipynb) to clean the data (stripped and removed some stuff) and marked the speakers with their affiliations. Then created a csv of the RNC and DNC files.
- Did the same with the debates where I marked with affiliations, but then I also created one string of all the text under one speaker to add to the RNC and DNC dataframe to use as the maincsv for word analysis.
- I added sample RNC and DNC speeches to the [data_sample](https://github.com/Data-Science-for-Linguists-2021/RhetoricalFactor-analysis/tree/main/data_sample) as well as the convention speakers csv. A good sample of the other data can be seen in the dataplan notebook.
- Ideas about sharing
  - The data I gathered was mostly within the public domain, but I am a bit worried about the scraped data, which I'm still not sure whether I can share that or not. I have added political affiliation tags onto the dataframe csv, so I think it would be useful to share at least the csv files. I'm not sure about displaying the raw data that I collected, so I will provide links to those, instead.

> **Second Project Report** 03/21/2021
- First off, I figured out a possibility for how I was going to go about my analysis, which became:
>
>>> **3 models of persuasive documents**
- speeches (written with persuasive intent)
    - audience: furthering the stance of one side
- debate (spontaneous persuasion)
    - audience: people looking to vote. people who probably have already chosen sides.
- platform (informative persuasion)
    - audience: people who want to know more about party
>>
- Then I started to hypothesis about the ability of a classifier to be able to predict D or R based on the 3 models: highest accuracy with Republican or Democrat from speeches, then next the debate, then the platform.
- After, I cleaned up my data to support this analysis and found the [Democratic](https://www.presidency.ucsb.edu/documents/2020-democratic-party-platform) and [Republican](https://www.presidency.ucsb.edu/documents/2016-republican-party-platform) Party Platforms online, but while they were citable and able to be used, they're license page stated "[...]you are hereby granted a limited, nonexclusive, nontransferable, non-sublicensable, revocable license to access and use our Services for your own personal, informational, and noncommercial use", so I kept these in a ignored folder, but cleaned them up and made a csv of sentences with political affiliations.
- I then added the scraped [debate data](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/tree/main/data) to the published repository, as these were public domain documents. Additionally, I added csv files of the political affiliation dataframe I created in my [dataplan](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/dataplan.ipynb), which includes one with the moderator and one without the moderator.
- Also added link to kaggle.com to the [data_samples](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/tree/main/data_sample)
- Created a [separate folder](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/tree/main/analysis_notebooks) for the analysis portion and read the files into there.
- All together, there are 4 csv files I created that I plan to use for analysis: convspeeches (hidden), pageVPdebate, welkerPRESdebate, and platformsents (hidden)
- License Portion:
  - Because I have data coming from multiple different sources, I kept the ones that have limitations for sharing/ones that were downloaded from a data sharing site in ignored folders. For the debate data, I am publically sharing the csv files as they are political speeches and are in the public domain.
  - In terms of my own license, I ended up chosing the [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) because it included freedom to use my project, but requires disclosing the source so that others can find and use my work, as I added information to the original data collection (political affiliation).

> **Third Project Report** 04/13/2021
- For this progress report, I mostly worked on the analysis portion and trying to extract the information I wanted from the data. Since my project idea is based off the idea of being able to determine whether text is democratic or republican based on different mediums, I made word feature classifiers in the hopes of finding if a classifier would be able to predict in the lineup of accuracy that I think it would be able to bc of the place the text comes from (speech, debate, platform), and it mostly did, but I quickly realized that the feature extractor did not work on binary targets (D and R). I spent way more time than I was hoping on trying to find a way for it to work, but everything I looked up ended up with a result that I wasn't exactly going for, so I ended up having to flush out a probably pretty wrong way to cheat my way into the features and added a neutral affiliation for the [speech](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/analysis_notebooks/speech_analysis.ipynb) and [debate](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/analysis_notebooks/debate_analysis.ipynb) analysis. I also did a logistic regression model for the speech and debate, but I'll have to work with that more to see how I can get it to make more sense with my hypothesis
  - Speaking of my hypothesis, I'm starting to see some differences that I need to analyze further within the three forms of persuasion that I've got going on. I think a good portion of analysis might happen off of jupyter notebook, and I'll have to work on plots some more. I also initially wanted to try sentiment analysis and seeing whether the use of "fancy" words (bascially just adjectives) meant anything, but this was definitely a helpful headway into the analysis because I'm starting to see more ways to go about this.
- I've left the [extra analysis notebook](https://github.com/Data-Science-for-Linguists-2021/PoliticalRhetoric-analysis/blob/main/analysis_notebooks/extra_analysis.ipynb) blank as I'll play with that a little more when I'm done with the heftier chunk.
- My data was in it's final from from last progress report, so that should be good.
- The license was also decided last progress report, so that should be fully addressed as well!
- I think that analysis might be coming down to the 3 mediums rather than the rhetorical differences between Republican and Democrat, so I need to work on the latter some more.
- Added my guestbook to my README file
