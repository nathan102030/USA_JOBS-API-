Overview
This project provides a Python script that extracts job information from the USAJOBS API, searches for job listings based on a provided job description and location, and saves the results into a CSV file. The job data includes the title, URL, and a summary of the qualifications for each job listing.
Prerequisites
Before running this script, ensure you have the following installed:
Python 3.x
Required Python packages:
requests
csv
json
Installation
Install the required Python packages:
bash
Copy code
pip install requests

API Authorization
To access job data from the USAJOBS API, this script uses an Authorization-Key and a User-Agent. Make sure you replace the placeholder values with your own:
python
Copy code
headers = {
    "Host": "data.usajobs.gov",
    "User-Agent": "your-email@example.com",
    "Authorization-Key": "your-authorization-key"
}

Script Usage
The script searches for job listings on USAJOBS based on the following parameters:
Job Description: A keyword for the type of job you want to search for (e.g., "energy").
Location: The location of the jobs you want to search for. Leave it empty for a nationwide search.
By default, the script searches for jobs with the description "energy" and no specific location.
How to Run
Modify the description and location values in the main() function as needed.
Run the script by executing the following command in your terminal:
bash
Copy code
python job_scraper.py

Example
To search for jobs related to "energy" in all locations, you would run the script as is.
Output
The script outputs a CSV file named jobs_results.csv containing the following columns:
Title: The job title.
URL: The link to the job listing.
Description: A brief qualification summary of the job.
The CSV file will be appended if it already exists, and a new file will be created if it doesn't.
Sample CSV Output
arduino
Copy code
Title,URL,Description
Energy Analyst,https://example.com/job/123456,Requires a bachelor's degree in energy studies...
Energy Policy Advisor,https://example.com/job/654321,Must have experience in energy policy and analysis...

Error Handling
The script checks for HTTP errors using response.raise_for_status() and prints an appropriate message if no jobs are found.
Notes
The script is currently set to search for "energy"-related jobs with an empty location, but this can be customized to your needs.
Make sure that your API key is valid and the email used in User-Agent is registered with the USAJOBS API.
