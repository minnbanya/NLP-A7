# NLP A5
 AIT NLP Assignment 7

- [Student Information](#student-information)
- [Installation and Setup](#installation-and-setup)
- [Usage](#usage)
- [Data sourcing (Webcrawler)](#data-sourcing-webcrawler)
- [Prompt template design](#prompt-template-design)
- [Model evaluation](#model-evaluation)


## Student Information
Name - Minn Banya  
ID - st124145

## Installation and Setup
Webapp at localhost:8000

## Usage
Run the AIT_Chatbot (GPT2) notebook to download the model and create the vector store and chatbot.  
cd into app folder and run 'python3 app.py'  

## Data sourcing (Webcrawler)
The data and documents related to AIT are obtained by using a webcrawler. The webcrawler starts the crawl from `https://ait.ac.th`. The text of the webpage html is cleaned and appended to the document list. Links in the html are added to the links-to-crawl list only if the link has not be crawled before and it contains the word `ait`. Webpage contents that are popups for cookies, images, irrelevant links, foreign languages, etc are excluded from being appended to the documents. Both of these are done by using regular expression. Attachments in the webpages are downloaded as PDFs. The webcrawling is limited to 100 links for the sake of time and computational resources. The crawled data from each link is saved as PDFs with the links also included.

## Prompt template design
This is the designed prompt template for the AIT Chatbot:  

prompt_template = """
Welcome to AITBot, your virtual assistant for all things related to the Asian Institute of Technology (AIT).
Whether you're a student, faculty member, or simply curious about AIT, I'm here to provide you with information and assistance.
Feel free to ask me anything about AIT, including its programs, research areas, campus facilities, and more.
I'll do my best to provide you with accurate and helpful answers to your inquiries.
So go ahead, ask me anything you'd like to know about AIT, and let's explore together!
{context}
Question: {question}
Answer:
"""

The template just slightly modifies the professor's design template to match the application's intended use. The format of including context and question remains the same for this application.

## Model evaluation
