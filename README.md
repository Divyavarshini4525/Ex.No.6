# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date:30-09-2025

# Register no.212222050012

# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

#AI Tools Required:

**Requirements**

**Hardware Requirements**

Processor: Intel i3/i5 or higher

RAM: 4 GB minimum (8 GB recommended)

Storage: 500 MB free space

Internet connectivity for API calls

Software Requirements

Python 3.8 or above

**Installed libraries:**

openai

transformers (Hugging Face)

torch (for model backend)

Valid API key for OpenAI / Cohere (or any other tool)

Jupyter Notebook / VS Code for execution

Algorithm / Steps

Import Dependencies: Load the required Python libraries such as openai and transformers.

**Connect to APIs:**

Set up the OpenAI API key and function for response retrieval.

Load a Hugging Face text generation pipeline.

Input Prompt: Define a domain-specific query (example: importance of renewable energy in the power grid).

**Generate Outputs:**

Collect the response from OpenAI GPT model.

Collect the response from Hugging Face GPT-2 model.

Compare Results: Analyze outputs based on:

Length and detail of response

Fluency and grammar

Domain relevance

Generate Insights: Provide a simple metric or interpretation (e.g., “OpenAI gave structured content, Hugging Face gave creative text”).

Display Results: Print the outputs side by side for evaluation.

**Python Code Implementation**

import openai

from transformers import pipeline

# -----------------------
# OpenAI GPT Integration
# -----------------------
openai.api_key = "your-openai-api-key"

def get_openai_response(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",  
        messages=[{"role": "user", "content": prompt}]
    )
    return response["choices"][0]["message"]["content"]

# -----------------------
# Hugging Face Integration
# -----------------------
def get_hf_response(prompt):
    generator = pipeline("text-generation", model="gpt2")
    response = generator(prompt, max_length=60, num_return_sequences=1)
    return response[0]["generated_text"]

# -----------------------
# Comparison Function
# -----------------------
def compare_outputs(prompt):
    print("\n>>> Prompt:", prompt)
    
    openai_output = get_openai_response(prompt)
    hf_output = get_hf_response(prompt)

    print("\n--- OpenAI Output ---\n", openai_output)
    print("\n--- HuggingFace Output ---\n", hf_output)

    # Simple comparative insight
    if len(openai_output) > len(hf_output):
        print("\n[Insight] OpenAI provided a more detailed response.")
    else:
        print("\n[Insight] HuggingFace provided a more concise response.")

# -----------------------
# Main Program
# -----------------------
if __name__ == "__main__":
    user_prompt = "Explain the importance of renewable energy in the power grid."
    compare_outputs(user_prompt)
    
**Sample Output (Illustrative)**

>>> Prompt: Explain the importance of renewable energy in the power grid.

**--- OpenAI Output ---**
Renewable energy plays a crucial role in modern power grids as it reduces dependency 
on fossil fuels, enhances sustainability, and decreases greenhouse gas emissions. 
Integration of solar, wind, and hydropower improves energy security, lowers 
operational costs, and supports a cleaner environment.

**--- HuggingFace Output ---**
Explain the importance of renewable energy in the power grid. The renewable energy 
is important for the grid as it helps balance demand, but it is not always stable 
and requires additional planning. Renewable energy plays an...

[Insight] OpenAI provided a more detailed response.

<img width="1018" height="875" alt="image" src="https://github.com/user-attachments/assets/800baa3c-8a9d-4700-a822-962049bc1df1" />


# Explanation:

**Discussion / Explanation**

**Persona pattern as a programmer:** 

i) The code is written as if a programmer is building a framework to benchmark multiple AI tools.

**Multiple AI Tool Integration:**

i) OpenAI GPT is better at generating structured, domain-relevant answers.

ii) Hugging Face GPT-2 produces more creative, free-flowing text but less accurate content.

**Application Relevance:**

i) In Electrical Engineering, such a system can be used to collect technical summaries on topics like load forecasting, smart grids, and renewable integration.

ii) In Education, it can compare tools for tutoring systems.

iii) In Industry, it can automate reporting by selecting the most suitable AI output.

**Actionable Insights:**

i) This multi-tool approach allows developers to:

ii) Select the right AI depending on task requirements.

iii) Cross-verify answers for accuracy.

iv) Build hybrid systems that combine strengths of different tools. 

<img width="901" height="898" alt="image" src="https://github.com/user-attachments/assets/f55e8e15-e233-42f6-932d-2087fee63a30" />

# Conclusion:

The experiment successfully demonstrated the development of Python code that interacts with multiple AI tools (OpenAI and Hugging Face). The responses were compared based on content quality, and actionable insights were generated. This proves that integrating diverse AI tools enhances reliability and helps programmers build robust applications.

# Result: The corresponding Prompt is executed successfully.
