# AI Information Retrieval Dashboard

## Project Description

This project is an AI-powered information retrieval dashboard that allows users to upload a CSV file and extract relevant information from the web based on user-defined search queries. The application utilizes **ScraperAPI** for web scraping and **Groq LLM** for parsing and extracting specific data such as email addresses from the scraped content.

The dashboard is built using **Streamlit** and provides an interactive interface for querying and extracting data from the web in real-time.

## Setup Instructions

To run this application, follow these steps:

### 1. Clone the Repository

```bash 
git clone <repository-url>
cd <repository-folder>
```
### 2. Install Dependencies
Make sure you have Python installed. Then, use the following command to install the required Python dependencies:
```bash 
pip install -r requirements.txt
```
### Alternatively, you can manually install the necessary dependencies:
```bash 
pip install streamlit pandas requests python-dotenv groq
pip install gspread oauth2client google-auth google-auth-oauthlib google-auth-httplib2 langchain pydantic

```
### You’ll also need  to install npm to install the localtunnel:
```bash 
npm install localtunnel

```
### 3. Set Up Environment Variables
Create a .env file in the root directory and include your ScraperAPI key:
```bash 
SCRAPERAPI_KEY=your_scraper_api_key
GROQ_API_KEY=your_groq_api_key
```
### Make sure to replace your_scraper_api_key  and your_groq_api_key with your actual API key.
### 4. Running the Application
Run the application using the following command:
```bash 
streamlit run app.py

```
### The dashboard will be hosted locally, and a localtunnel will be used to provide an external URL for remote access:
```bash 
npx localtunnel --port 8501
```
### This will output a URL that you can access externally.

## Usage Guide
### 1. Uploading a CSV File
Once the app is running, you will be prompted to upload a CSV file. The file should contain a column with entities (such as names or IDs) for which you want to retrieve information. The app will display a preview of the data and allow you to select the primary column for entity extraction.

### 2. Setting Up the Search Query
Enter a custom query in the input field, using {entity} as a placeholder for the values from the selected column. For example, to retrieve email addresses, you can enter the following:
```bash
Retrieve email address of {entity}
```
### 3. Running the Search
Once the query is defined, press the "Run Search" button. The app will use ScraperAPI to scrape the web based on the defined query and extract data. If the data retrieval is successful, it will be parsed using Groq LLM to extract specific information like email addresses.

### 4. Viewing Results
The app will display two tables:

Raw Web Data: The data scraped from the web.
Extracted Information: The parsed and extracted information (e.g., email addresses).
You can also download the extracted data as a CSV file using the download button.

### API Keys and Environment Variables
SCRAPERAPI_KEY: This is required to interact with the ScraperAPI service. You can get your API key by signing up on ScraperAPI. Make sure to enter the key in the .env file as shown above.
No additional environment variables are required to run the application.
GROQ_API_KEY: This is required to interact with the Groq API. You can get your API key by signing up on Groq. Make sure to enter the key in the .env file as shown above.
Both API keys should be stored in your .env file for secure access.
