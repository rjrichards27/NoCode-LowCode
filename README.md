## Introduction and Set Up
This repository is a text analysis of the book The Bell Jar by Sylvia Plath. I started by creating a CoLab file to first create a txt file that contained all of the words in the book, as well as, created a string of all the words. I then created a new string that consisted of all of the words in the book except for the stop words, using the below code. This allowed me to evaluate the specific words that describe the tone of the story and dismayed the filler generic words. 
```
tbj_blob = TextBlob(Path('TheBellJar.txt').read_text())
tbj_count = tbj_blob.word_counts.items()
no_stop_words = remove_stop(tbj_count)
```
## Analysis
I used that string to develop a word cloud to show the most used words in the book, using the code below. The word cloud showed that the word that was used the most was “coloured”. I found it very interesting that a lot of the words that were used the most were specific colors. “Red”, “Green”, “Blue, “Black”, “Pink”, “White”, and “Grey” were all included within the word cloud and were some of the largest words. I read this book several years ago so I do not remember exactly why these words were included so often. My only guess is that Plath would provide in depth descriptions of the surroundings or that the colors are used as symbolism. It would be interesting to do more analysis to see why these colors are used so often.
```
word_cloud_text = str1 = ' '.join(no_stop_words)
wordCloud = WordCloud().generate(word_cloud_text)
```
![Word Cloud](/Images/Word_Cloud.png)

I then created a csv file, with the code shown below, that included all of the words in the book along with the frequency of each specific word, which included stop words. I used this csv in QuickStart to create a bar chart of the most used words in the book. The chart showed that the most used word was “and” followed by “of”. All of the words on this graph were stop words, which was not surprising. These words are used the most often in order to create sentence structure, which is why I did not include them in the word cloud.

```
df.to_csv("The Bell Jar Words.txt", index=False)
```
![Word Count Bar Graph](/Images/Word_Count_Graph.png)

The last part of my text analysis was a sentiment analysis, using AWS Comphrend, of the first part of the first chapter. The sentiment analysis showed that the overall sentiment was negative, with 78.5% of the words being negative. This outcome does not surprise me because the book describes the struggle of living with  a mental illness.

## Conclusion
Overall the text analysis showed that The Bell Jar by Sylvia Plath uses colors to often describe the world of the main character. It would be interesting to do further analysis to determine what the colors are used to describe. The colors could be used to describe the setting or be symbolism for something else. The sentiment analysis shows that most of the first chapter includes negative words. The tone of the book is realtively negative, so I would be curious to see if this would change throughout the book. It would be beneficial to do further sentiment analysis on more of the book to determine its overall sentiment. 

