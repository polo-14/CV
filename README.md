
# Resume Extractor

A lightweight Flask-based application to extract and parse resume content from PDF and Word documents using modern NLP tools.

## Getting Started

Follow these steps to set up and run the project locally.

### Create and Activate Conda Environment

```bash
conda create -n resumeExtract python=3.10 -y
conda activate resumeExtract
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run the Flask App

```bash
python app.py
```

---

## Features

* ✅ Upload resumes in **PDF** or **DOCX** format
* ✅ Automatically extracts and parses key resume information
* ✅ Clean and modular code with **Blueprints** support
* ✅ In-memory file processing (no disk write)


## Project Structure

```bash
RESUME EXTRACTION/
│
├── app.py                          
├── route_resume.py                 
├── requirements.txt                
├── readme.md                       
│
├── function_common/                
│   ├── extractPDF.py               
│   └── extractDOCS.py             
│
├── helper/                         
│   └── prompt.py                   
│
├── logs/                          
│   └── app.log                     
│
├── research/                       
│   └── resumeExtraction.ipynb      
│
├── SRINAATH DATASCIENTIST.docx     # Sample resume (Word format)
└── SRINATH CV (1).pdf              # Sample resume (PDF format)
```


## API Endpoints

### `GET /app/status`

* **Description**: Check if the main app is running.
* **Request Parameters**: None
* **Success Response**:

  ```json
  {
    "message": "App is running"
  }
  ```
* **Error Response**: None

---

### `GET /resume-ai/status`

* **Description**: Check if the resume extraction service is live.
* **Request Parameters**: None
* **Success Response**:

  ```json
  {
    "message": "Resume extraction service is running."
  }
  ```
* **Error Response**: None

---

### `POST /resume-ai/extract`

* **Description**: Extract information from an uploaded resume (PDF or DOCX).

* **Request Parameters**:

  * `api_key` (string): Your API key for authentication.
  * `model` (string): Name of the LLM model to use.
  * `file` (file): Resume file in PDF or DOCX format.

* **Success Response**:

  ```json
  {
    "parsed_resume": {
      "firstName": "Srinaath",
      "lastName": "R",
      "email": "srinaath1419@gmail.com",
      ...
    }
  }
  ```

* **Error Response**:

  ```json
  {
    "error": "Description of the error"
  }
  ```







