## Sentiment Analyzer

We utilized Flask to generate a web-based sentiment analysis tool that can collect information from Reddit about a particular product based on user input. The tool displays both positive and negative sentiment counts for the product, as well as the top 5 positive and negative words extracted from the collected Reddit posts.

To accomplish this task, we utilized praw to instantiate Reddit objects, and designed the frontend of the application using html and css. Additionally, we compiled a "requirements.txt" file with all the necessary libraries and wrote an "app.py" file to incorporate Flask and its requisite functions into the application.

Included below are a few screenshots of the web application.

### Homepage of the Sentiment Analyzer
![Home Page](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Sentiment/images/Homepage.PNG)

### Entering a Product Name
![Entering Product Name](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Sentiment/images/Input.PNG)

### Obtaining Reddit Posts 
![Obtaining Reddit Posts](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Sentiment/images/posts.PNG)

### Analysis of Positive and Negative Posts
![Analysis of Positive and Negative Posts](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Sentiment/images/Counting.PNG)

### Top 5 Positive and Negative Words
![Top 5 Positive and Negative Words](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Sentiment/images/Topwords.PNG)
