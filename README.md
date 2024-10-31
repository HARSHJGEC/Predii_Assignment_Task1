
# Assignment - Automotive Data Processing, Summarization, and Chatbot Interaction

This project is designed to process automotive data from raw text format, filter and structure the data into JSON files, and generate detailed summaries using the LLaMA 3.1 (8B) model. The project also includes an interactive chatbot interface that enables users to query the database, retrieve relevant information, and view concise summaries based on filtered results.

---

## Project Overview

This project workflow includes:
1. **Data Filtering**: Reading, filtering, and structuring automotive data from a raw text file.
2. **Chatbot-Compatible Database Creation**: Generating summaries for each record using LLaMA 3.1 (8B), with fields optimized for chatbot responses.
3. **Interactive Chatbot Interface**: Allowing users to interact with data through queries and obtain summarized responses.

## Files Included

- **FLAT_RCL.txt**: Raw input file containing the automotive data.
- **dataset.ipynb**: Notebook that reads and filters `FLAT_RCL.txt` to create a structured JSON file (`dataset.json`).
- **dataset.json**: Filtered and structured JSON file with vehicle records.
- **chatbox_database creator.ipynb**: Notebook to generate `database_chatbox.json` with LLaMA 3.1 summaries.
- **database_chatbox.json**: JSON file structured for chatbot interactions, containing detailed summaries.
- **chatbox.ipynb**: Notebook for the chatbot interface, which filters data and provides responses based on user queries.
- **output.file**: Log file that saves each user interaction and chatbot response summary for reference.

---

## Data Processing Workflow

1. **Reading the Data**: The process begins by reading `FLAT_RCL.txt`, extracting each record’s fields line by line.
  
2. **Filtering Criteria**: Only records where the `make` is "FORD" or "TOYOTA" are retained.

3. **Data Structure in `dataset.json`**:
   - **Make**: Manufacturer of the vehicle (filtered for FORD and TOYOTA only).
   - **Model**: Vehicle model.
   - **Year**: Manufacturing year.
   - **Other Info**: Additional details concatenated from the remaining fields of each record.

4. **Saving as JSON**: The filtered and structured data is saved as `dataset.json` for streamlined access and further processing.

---

### Chatbot Database Creation

Using `chatbox_database creator.ipynb`, the project generates `database_chatbox.json` by:
1. **Applying LLaMA 3.1 Model (8B)**: Summaries are generated for each record based on structured prompts that guide LLaMA to extract relevant details, such as defect information, possible consequences, and recommended corrective actions.

2. **Database Structure in `database_chatbox.json`**:
   - **Make**: Manufacturer of the vehicle.
   - **Model**: Vehicle model.
   - **Year**: Manufacturing year.
   - **Defect Summary**: Brief description of the defect.
   - **Consequence Summary**: Potential consequences linked to the defect.
   - **Corrective Summary**: Suggested corrective actions or remedies.
   - **Merged Summary**: Combined summary for concise chatbot responses.

3. **Prompt Design for LLaMA 3.1 (8B Model)**:
   - Structured prompts are used to direct the model to focus on defect, consequence, and corrective summaries, merging these into a single summary that facilitates chatbot interactions. This prompt ensures responses are accurate, concise, and user-friendly.

---

## Chatbot Interaction

The `chatbox.ipynb` notebook provides a user-friendly interface that enables users to query data and view relevant summaries. Here’s how the chatbot process works:

1. **User Query Input**: Users input queries about a specific make, model, or year of a vehicle.
2. **Data Filtering**: The chatbot filters entries in `database_chatbox.json` based on the user’s input.
3. **Response Summarization**: The filtered data is summarized using LLaMA 3.1, generating a clear and concise response.
4. **Interaction Logging**: Each query and its summarized response are saved in `output.file` for reference and analysis.

---

## Requirements

- Python 3.x
- Jupyter Notebook
- LLaMA 3.1 (8B model)

## Usage

1. **Data Preparation**:
   - Run `dataset.ipynb` to generate `dataset.json` from `FLAT_RCL.txt`.
   - Run `chatbox_database creator.ipynb` to create `database_chatbox.json` with detailed summaries.

2. **Running the Chatbot**:
   - Open `chatbox.ipynb` in Jupyter Notebook.
   - Enter a query in the input cell to initiate a search. The chatbot will:
     - Filter relevant records from `database_chatbox.json`.
     - Summarize the results based on the user’s query.
     - Display the response.
   - Each interaction is recorded in `output.file` for future reference.

This setup enables streamlined data filtering, real-time chatbot interaction, and summary generation based on automotive records. 

---
Assignment result : database_chatbox.json
