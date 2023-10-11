# UCSD Crime Log Twitter (X) Bot

Using the Twitter API to tweet summaries of the UCSD Crime Logs that are posted every day.

To view the tweets, follow [@ucsdpd](https://twitter.com/ucsdpd) on Twitter. 

# Introduction 

Every day, there are people that call the UC San Diego police, and whether what they are calling about is an emergency or not, most of it gets logged and posted online for people to see. Let's take a moment to thank The Clery Act for this. 

> The Clery Act requires institutions of higher education to comply with certain campus safety- and security-related requirements as a condition of their participation in the title IV, HEA programs 

I first found out about these crime logs through the r/UCSD subreddit because of this [post](https://www.reddit.com/r/UCSD/comments/mr8q4b/so_i_was_going_through_the_uc_police_log_and_i/) right here. When I finished reading that post, I immediately started looking through the logs. Some were mundane, others more serious, but others were absolutely **hilarious**. 

Stuff ranging from injured hamsters and [angry squirrels](https://x.com/ucsdpd/status/1579058101675663360?s=20) to [people licking merchandise](https://x.com/ucsdpd/status/1637608483704156160?s=20) and refusing to leave the store. 

After reading the logs, I decided it would be a good idea to bring them to the attention of a broader audience. For this, I picked Twitter since it is mostly a text based app. 

# Major Road Blocks

##### Number 1 

The first major roadblock I encountered was converting the crime log PDF files to text. 

I first tried using a Python library called PyPDF2 to extract the text but I kept getting a lot of text interpolation and random space mistakes.  

After a long search, I finally stumbled upon this amazing library called [pdfplumber](https://github.com/jsvine/pdfplumber). Basically, it copied the format and content of the PDF into text absolutely perfectly. This meant I would not have to go back and review the converted text files and fix formatting issues at all. 

##### Number 2
The API changes resulting from the Twitter buyout.

Basically, before the Twitter takeover, my bot could tweet as much as it wanted as long as the post requests had a buffer of about 30s in between each other. 

Now, the Twitter API limits my posting to only 50 tweets a day with the free tier. The next tier up costs $100/month and only allows you to post 100 tweets per day.  

Even though this might sound like a lot, it becomes nothing when trying to tweet reports from months ago. The crime log cases really add up. 
# Future Improvements

##### Number 1 
At this point of the project, it only takes me a few clicks to grab dates and start tweeting the content out. So its fairly easy to run on my local machine once I put that short amount of time in. 

Even then, I still want to make this process completely automated. I'm hoping to have a cron job run a script every day so I don't even have to think about it at all. 

##### Number 2

At this moment, the content that gets posted does not go through much filtering at all. Almost every case that is contained in the crime log gets tweeted. 

I want to implement a more thorough filtering process that removes the mundane crime log cases and only allows bizarre or more serious cases to be posted. Something like sentiment analysis. 


# Conclusion 

I hope you enjoyed reading! If you want to keep up with the process, just make sure to give the account a follow. 




