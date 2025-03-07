# Tax Document Processing System

This project is an automated tax document processing system built using [N8N](https://n8n.io/) for workflow automation, Open AI, AWS, and [Supabase](https://supabase.com/) with Postgres for backend and database management. It integrates various technologies and APIs to process and analyze documents, audio, and text data related to tax processing.

<img width="1424" alt="Screenshot 2025-03-07 at 10 44 43" src="https://github.com/user-attachments/assets/65994784-2bff-4ef5-b966-bf2e0f849af5" />

## Overview

The system consists of three main workflows:

1. **Document Processing Workflow**
   - **Purpose:** Monitors an email inbox or cloud storage for incoming tax documents such as W-2s, 1099s, and invoices.
   - **Key Features:**
     - Extraction of attachments and processing of images and PDFs.
     - Use of AWS Textract for OCR to extract text from scanned images.
     - Classification of document types using AI (via OpenAI’s GPT-3.5-turbo).
     - Storing document metadata and extracted data in Supabase.
     - Similarity search using document embeddings to flag inconsistencies.

2. **Audio Processing Workflow**
   - **Purpose:** Processes audio files uploaded to cloud storage that contain recorded tax consultation conversations.
   - **Key Features:**
     - Triggers on new audio files (MP3, WAV) using Google Drive triggers.
     - Transcription of audio using Whisper AI or OpenAI Speech-to-Text.
     - Extraction of financial entities (SSNs, tax IDs, income figures) from transcriptions via AI.
     - Storage of transcribed text and extracted financial data in Supabase.

3. **Text Processing Workflow**
   - **Purpose:** Monitors incoming emails for both structured and unstructured text-based tax information.
   - **Key Features:**
     - Extraction of text from email bodies and attachments.
     - Analysis of text using NLP to extract relevant financial data.
     - Storage of extracted tax data in Supabase.

## Technologies and Skills Applied

- **N8N (Workflow Automation):** Automated multi-step workflows that integrate different data sources and services.
- **Supabase:** PostgreSQL backend with REST API endpoints and edge functions for data validation and storage.
- **AWS Textract:** OCR technology to extract text from scanned documents.
- **OpenAI / Whisper AI:** Utilized for both text classification and audio transcription, as well as for extracting key financial entities.
- **Environment Variables:** Used to securely manage credentials and configuration details across the workflows.
- **Error Handling:** Implements retry mechanisms, error logging, and alerts to ensure robustness.
- **Modularity and Documentation:** The workflow is modular and documented to facilitate maintenance and further development.

## Setup Instructions

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd <repository-directory>
