# ATS  Processing System

## Overview
This repository contains the Resume Processing System, which automates resume matching against job descriptions (JD) using AI agents, Google Drive integration, and a vector database (Pinecone Index).

## Architecture Flow
The system consists of the following key components:
- **User**: Submits a job description (JD) for processing.
- **Flask App**: Handles user interaction and authentication.
- **Google Drive**: Stores resumes in PDF/TXT formats.
- **LangFlow Agent 1**: Identifies relevant resumes based on JD.
- **Pinecone Index**: Performs similarity searches.
- **LangFlow Agent 2**: Conducts refinement scoring and additional entity extraction.

## Workflow
The process is divided into two major flows: **Authentication & Authorization Flow** and **Resume Processing Flow**.

### Authentication & Authorization Flow
1. User submits a job description (JD) via the Flask App.
2. The system redirects the user to Google Authentication.

### Resume Processing Flow
1. Flask App sends the JD to LangFlow Agent 1.
2. LangFlow Agent 1 identifies relevant folder names.
3. Flask App requests folder contents from Google Drive.
4. Google Drive returns PDF/TXT resume files.
5. Flask App queries Pinecone Index with the JD.
6. Pinecone Index returns the top matching resumes.
7. The matched resumes are sent to LangFlow Agent 2 for further processing.
8. LangFlow Agent 2 performs **Refinement Scoring & Extra Entity Extraction**.
9. Final ranked results are returned and displayed to the user.

## Technologies Used
- **Flask**: Web framework for handling API requests.
- **Google Drive API**: For accessing and retrieving resumes.
- **LangFlow Agents**: AI-driven agents for resume matching and refinement.
- **Pinecone**: Vector database for similarity search.
- **OAuth 2.0**: For Google authentication.
##Recommendtaion
Use Google Colab for execution 
we can process architecture very fast
## Expected Output
- The system provides a ranked list of resumes that match the job description.
- The ranking is refined based on entity extraction and additional scoring.

## Future Enhancements

- Introduce real-time resume updates and notifications.



For any issues or improvements, please open an issue in the repository.

