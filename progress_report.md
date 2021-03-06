#### Progress Report

> **First Entry** 02/18/21
- created the term project repository
- found more sources for possible datasets, also considered new topic choices
- worked on and cleaned up my project plan

> **First Project Report** 03/04/2021
- Downloaded two datasets on kaggle.com that had transcripts of [RNC](https://www.kaggle.com/christianlillelund/2020-republican-convention-speeches) and [DNC](https://www.kaggle.com/christianlillelund/2020-democratic-convention-speeches) speeches. They were in public domain.
- Next I found recent debate transcripts on rev.com and scraped the contents. (I put the scraper into .gitignore for right now, but might take it out once I clean up my project space more) The first was the [VP debate with Page](https://www.rev.com/blog/transcripts/kamala-harris-mike-pence-2020-vice-presidential-debate-transcript) and [Presidential debate with Welker](https://www.rev.com/blog/transcripts/donald-trump-joe-biden-final-presidential-debate-transcript-2020). For these, I used regular expressions to extract the content and wrote each to a csv file with speaker info, time_stamps, and the text. 
- I created a [jupyter notebook](https://github.com/Data-Science-for-Linguists-2021/RhetoricalFactor-analysis/blob/main/dataplan.ipynb) to clean the data (stripped and removed some stuff) and marked the speakers with their affiliations. Then created a csv of the RNC and DNC files.
- Did the same with the debates where I marked with affiliations, but then I also created one string of all the text under one speaker to add to the RNC and DNC dataframe to use as the maincsv for word analysis.
- I added sample RNC and DNC speeches to the [data_sample](https://github.com/Data-Science-for-Linguists-2021/RhetoricalFactor-analysis/tree/main/data_sample) as well as the convention speakers csv. A good sample of the other data can be seen in the dataplan notebook.
- Ideas about sharing
  - The data I gathered was mostly within the public domain, but I am a bit worried about the scraped data, which I'm still not sure whether I can share that or not. I have added political affiliation tags onto the dataframe csv, so I think it would be useful to share at least the csv files. I'm not sure about displaying the raw data that I collected, so I will provide links to those, instead.
