# MCQ Generator

## Table of Content

  * [Demo](#demo)
  * [Overview](#overview)
  * [Motivation](#motivation)
  * [Technical Aspect](#technical-aspect)
  * [Pipeline](#pipeline)
  * [Installation](#installation)
  * [Run](#run)
  * [Directory Tree](#directory-tree)
  * [To Do](#to-do)
  * [Technologies Used](#technologies-used)
  * [License](#license)
 


## Demo
Link: [http://35.224.236.92:5000/](http://35.224.236.92:5000/)
#### Image

![Screenshot from 2020-09-23 16-41-37](https://user-images.githubusercontent.com/17935364/94005755-5d58c880-fdbc-11ea-8c8e-a7fceac2dba3.png)




## Overview
This is the Web App that is being developed by using Flask, Machine Learning, Docker, hosted on GCP instance and focus on providing teachers with automatic mcq generationing system for the given article or passage.   

## Motivation
I wanted to develop something that can utilize all of my learnings and also has little bit of uniqueness as well. So, after randomly looking at my younger brother's(5th standard) assignment regarding answering MCQ of given passage, I decided to automate the generation of MCQ in order to make the task of teachers little easy. 

## Technical Aspect
This project is divided into four part:
1. Building the core of the app using __Natural Language Processing__, __Wordnet__ and __ConceptNet__.
2. Desiging the frontend with the help of __HTML__, __CSS__, __JavaScript__(Done By __Shubhankar__).
3. Building __Flask API__ and Containerizing with the help of __Docker__.
4. Deploying the whole Web App on __Google Cloud Platform__.
    - Used e2-medium VM instance with 2 vcpus and 4 gb ram.
    - will use domain for static ip in future.
## Pipeline 
How MCQ queations along with wrong answer choice are generated?
1. Firstly the user provide text and choose to generate MCQ from Full Text or Summary.
2. Proper Noun words are extracted as keywords from text.
3. If user selects Summary then we use __Transformer__ model to generate summary and select respective keywords.
4. Respective Sentences are selected of gien keywords.
5. Word sense is calculated with __pwysd__ library for WordNet.
6. Related options (From same parent class) are extracted and if not found in Wordnet then ConceptNet(PartOf) is used.
7. Keyword is replaced with ______ and data is return as response.

## Installation
The Code is written in Python 3.8. If you don't have Python installed you can find it [here](https://www.python.org/downloads/). If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after [cloning](https://www.howtogeek.com/451360/how-to-clone-a-github-repository/) the repository:
```bash
pip install -r requirements.txt
```

## Run
To run the app in a local machine, shoot this command in the project directory:
```bash
python Flask_api.py
```
__Note:-__ It may download some of the required data on first run.



## Directory Tree 
```
MCQ_Generator/
├── Dockerfile
├── extract_keywords.py
├── find_sentances.py
├── Flask_api.py
├── generate_summary.py
├── gen_mcq.py
├── KeyNotes.txt
├── README.md
├── requirements.txt
├── response.json
├── static
│   ├── ai.svg
│   ├── arrow.svg
│   ├── get mcq group.svg
│   ├── input_data.svg
│   ├── script.js
│   └── style.css
├── summary_notebook.ipynb
├── templates
│   └── index.html
└── test_articles
    ├── article.txt
    ├── Egypt.txt
    └── The Indus River Valley Civilizations.txt

```

## To Do
Using Abstract Summarization in order to produce difficullt multiple choice questions.




## Technologies Used

![](https://forthebadge.com/images/badges/made-with-python.svg)

[<img target="_blank" src="https://www.gstatic.com/devrel-devsite/prod/vc0bb6d163e24d3b3e0961a17422a4975b4069aa6cfc1baff269f5aa415a63d55/tensorflow/images/lockup.svg" width=200>](https://tensorflow.io/) [<img target="_blank" src="https://flask.palletsprojects.com/en/1.1.x/_images/flask-logo.png" width=170>](https://flask.palletsprojects.com/en/1.1.x/) [<img target="_blank" src="https://d1q6f0aelx0por.cloudfront.net/product-logos/library-docker-logo.png" width=180>](https://www.docker.com/) 

[<img target="_blank" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/1200px-HTML5_logo_and_wordmark.svg.png" width=200 height=200>](https://html.com/) [<img target="_blank" src="https://miro.medium.com/proxy/1*urMF0EgCJ7YbtK090Rdikw.png" width=200>](https://cloud.google.com/)

## Team
[Kunal Verma](https://www.linkedin.com/in/kunal-verma3836/)



## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM,
DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE
OR OTHER DEALINGS IN THE SOFTWARE.
