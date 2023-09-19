# Resume-JD-Matcher
It is a PDF extractor to pull relevant details from CVs in PDF format, and matching them against the job descriptions from the Hugging Face dataset.

## Resume Dataset: (Using PDFs for data extraction)
https://www.kaggle.com/datasets/snehaanbhawal/resume-dataset

## JD Dataset: 
https://huggingface.co/datasets/jacob-hugging-face/job-descriptions/viewer/default/train?row=0

## 1. PDF Data Extraction
I am using the PyPDF2 library to extract text from PDF resumes.
After that browse to the particular folder with resume PDFs.
The PDF Extractor collects information like job category, skills, and education.
The Resume dataset is mounted on google drive and then it is fetched from there.

  Type the following command:
  
  ![image](https://github.com/PoojaPatkar21/Resume-JD-Matcher/assets/68493624/57a92de4-a130-4b6e-87b4-1b30d714a589)

  
  To check the current directory tye the following command:
  
  ![image](https://github.com/PoojaPatkar21/Resume-JD-Matcher/assets/68493624/befc1b96-f889-413c-8dc7-707f9e7ebda2)

  Current directory: /content
  
  For the pdf_directory path:
  pdf_directory= 'drive/My Drive/path to the folder containing pdfs/'
  
  For now, resumes from Information Technology folder are used. 
  pdf_directory= 'drive/My Drive/DATA/data/data/INFORMATION-TECHNOLOGY/'

For other domains simply changing the path to the respective folders will do.

## 2. Job Description Data Understanding
I have used the datasets library to fetch job descriptions from the Hugging Face dataset. Here a batch of job descriptions (around 10-15) is selected from the given dataset.

Understanding Job Descriptions:
To comprehend these job descriptions, print them.
   

## 3. Candidate-Job Matching 

Prepare a txt file of the extracted data as follows:
JD.txt for JD data
Resume.txt for extracted resume data

For matching candidates to jobs, NLP is used. The job description and a CV (that's the extracted resume data) from text files is read here.
Tokenization: These textual data is converted into tokens to give it a meaningful insight.
A pre-trained model, called DistilBERT model is used here to convert tokenized text into embeddings
Then the CVs and Job descriptions are finally compared to find the best match.
The top 5 candidates which fit the job description are found.






