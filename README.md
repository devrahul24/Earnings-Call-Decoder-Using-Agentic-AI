# Earnings Call Decoder Using Agentic AI

Automate the detection of nonanswers in earnings call transcripts using Agentic AI. This project classifies responses as "nonanswer" (vague or evasive) or "answer" (direct and substantive) and provides explanations for each classification, streamlining financial analysis.

## Table of Contents
- [Introduction](#introduction)
- [How It Works](#how-it-works)
- [Key Features](#key-features)
- [Technologies Used](#technologies-used)
- [Setup and Usage](#setup-and-usage)
- [Example](#example)
  
## Introduction
Earnings call transcripts are a critical resource for financial analysts and investors, but they often contain vague or evasive responses—known as "nonanswers." Manually identifying these nonanswers is time-consuming and inefficient. This project automates the process by using **Agentic AI** to classify responses and explain the reasoning behind each classification, making financial analysis faster and more reliable.

## How It Works
1. **Input**: An earnings call transcript is provided as input.
2. **Processing**: The transcript is split into individual responses, and each response is classified using the **Gemini API** as either a "nonanswer" or an "answer."
3. **Output**: The results are exported to a CSV file, including the original response, its classification, and an explanation for the classification.

## Key Features
- **Automated Classification**: Quickly identifies nonanswers and answers in earnings call transcripts.
- **Explanations**: Provides clear reasoning for each classification, adding transparency to the analysis.
- **Scalable**: Handles large datasets efficiently, making it suitable for processing multiple transcripts.
- **Customizable**: Easily adaptable to different transcript formats or classification criteria.

## Technologies Used
- **n8n**: A low-code automation tool that orchestrates the workflow.
- **Gemini API**: Powers the classification and explanation generation.
- **JavaScript**: Used for custom logic within the workflow to process and format data.

## Install Dependencies:
-- Ensure you have n8n installed. You can run it locally or use the cloud version.

## Configure API Keys:
-- Obtain a Gemini API key from Google AI Studio.
-- Add your API key to the n8n workflow in the HTTP Request node.

## Run the Workflow:
-- Open n8n and import the workflow JSON file from this repository.
-- Update the transcript input in the Set node.
-- Click "Test workflow" to run the process and generate the CSV output.

## Example
-- Input (Transcript Snippet):
It is all baked into the guidance for 2015.
We are talking about 89, 90 reps by the end of the year.
I can't answer that. It seems so hypothetical.

-- Output (CSV):
text, label, explanation
"It is all baked into guidance for 2015.",0, "The response is evasive and doesn't directly address the underlying question."
"We are talking about 89, 90 reps by the end of the year.",1, "Direct, provides concrete numbers."
"I can't answer that. It seems so hypothetical.",0, "Explicit refusal to answer."
