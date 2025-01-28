README.md

# Smart Content Processor with RAG for Safe Learning

This application is tailored to meet the demands of the modern learner by transforming multimedia content into text, enabling efficient summarization and question-answering capabilities. Leveraging technologies like Retrieval Augmented Generation (RAG), it offers a comprehensive solution for educational institutions. With the ability to summarize multi part video series and answer context-specific queries, this application empowers students and teachers alike. Robust guardrails ensure a safe learning environment by filtering out obscene or irrelevant content. Harnessing the power of Amazon Bedrock's knowledge base and open search, this industry-focused solution showcases the potential of Generative AI in the educational domain.

## Current challenges in Industry

* Information Overload: Students and educators struggle with vast amounts of multimedia

content.

* Accessibility Barriers: Difficulty in transforming video lectures into easily digestible text
  formats.
* Lack of Personalization: One-size-fits-all approaches fail to meet individual learning needs.
* Time Constraints: Inefficient content summarization leads to suboptimal use of study time.
* Context Loss: Difficulty in finding specific information within lengthy educational content.
* Safety Concerns: Potential exposure to inappropriate content in open learning environments.
* Language Limitations: Multilingual learners face challenges with content in non-native languages.

## AWS services used

* Amazon S3
* Amazon Sagemaker
* Amazon Transcribe
* Amazon OpenSearch Service
* Amazon Bedrock

## Architecture

![Edify_APJC_Tech_Summit_2024_arx](https://github.com/user-attachments/assets/feb79c22-2b6a-4884-a38d-0c4d2f149be1)


## Solution Overview

1. **Content Ingestion**: Multimedia content is fetched via SageMaker Notebook and stored in Amazon S3 bucket.
2. **Speech-to-Text Conversion**: The content is processed using Amazon Transcribe to convert audio into text format.
3. **Translation**: For multi-language content, Amazon Translate is utilized to process the text.
4. **Storage**: The final output in text format from both transcription and translation steps is saved to an S3 bucket.
5. **Knowledge Base Creation**: Amazon Bedrock is used to create a knowledge base, which is then stored in Amazon OpenSearch Service.
6. **Query Processing**: The knowledge base is queried through an LLM via Bedrock, and the responses are displayed.
7. **Result Analysis**: Users can check the corresponding chunks from which the response was derived and view relevancy scores.

## Key Features

* **Content Filtering**: As this project is designed for the EdTech domain, relevant filters are implemented to restrict content input/output.
* **Bedrock Guardrails**: Used for content moderation and filtering.
* **Content Categories**: Filters are applied for hate speech, violence, insults, and sexual content. The strength of these filters can be tuned.
* **Denied Topics**: Functionality to prevent answering questions on certain topics.
* **Grounding Check**: Enabled in Bedrock to validate model responses.
* **Relevancy Check**: Used to ensure model responses are relevant to user queries and block irrelevant messages.

## Demo

The functionality of this system is demonstrated in two parts:

Part 1: Showcases the knowledge base querying and result analysis.

https://github.com/user-attachments/assets/db70b324-60a4-4b12-ac2d-45ab556f6f23

Part 2: Demonstrates the content filtering and guardrails features.

https://github.com/user-attachments/assets/66d1afc7-d1da-4328-81f5-4fc4328fde96



## Security

See [CONTRIBUTING](https://github.com/aws-samples/rag-with-amazon-bedrock-and-memorydb/blob/main/CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.
