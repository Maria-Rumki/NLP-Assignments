## Code Autocompletion

We utilized Flask to construct an online automatic code generator that produces code given a set of initial keywords. To use this program, the user must input a few code keywords in the beginning, and the software will then automatically anticipate the subsequent words of the code based on a fixed sequence length.

To achieve this Language Modeling assignment, we employed an LSTM model to forecast the next words in a series. Subsequently, we designed the essential frontend utilizing HTML to present the process on a web application. To apply Flask and pass the necessary function in the application, we utilized the "requirements.txt" file, which contains all the required libraries, and generated "app.py."

Below are some screenshots of the web application:

### Homepage of the Code Generator
![Home Page](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Language%20Model/images/Homepage.PNG)

### Entering a Few Words of Codes
![Entering Few Words Codes](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Language%20Model/images/Input.PNG)

### Prediction Based on Given Input Codes
![Prediction Based Given Input Codes](https://raw.githubusercontent.com/Maria-Rumki/NLP-Assignments/main/Language%20Model/images/Output.PNG)
