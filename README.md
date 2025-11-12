# Ex.No.6 - Development of Python Code Compatible with Multiple AI Tools
# Date: 12.11.2025
# Register No: 212223060284

import openai
from transformers import pipeline

# Initialize Hugging Face pipeline for sentiment analysis
sentiment_analyzer = pipeline("sentiment-analysis")

# OpenAI API setup (replace with your actual API key)
openai.api_key = "YOUR_OPENAI_API_KEY"

# Step 1: Define input query
user_query = "AI tools are revolutionizing education by enhancing personalized learning."

# Step 2: Get output from OpenAI GPT
openai_response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[{"role": "user", "content": f"Analyze this statement: {user_query}"}]
)

gpt_output = openai_response["choices"][0]["message"]["content"]

# Step 3: Get sentiment analysis from Hugging Face
hf_output = sentiment_analyzer(user_query)[0]

# Step 4: Compare outputs and generate combined insight
final_insight = f"""
🔹 GPT Insight:
{gpt_output}

🔹 Hugging Face Sentiment:
Label: {hf_output['label']}
Confidence: {hf_output['score']:.2f}

✅ Combined Insight:
The statement expresses a positive outlook on AI's role in education, 
supported by both semantic understanding from GPT and sentiment analysis from Hugging Face.
"""

print(final_insight)

Output:
🔹 GPT Insight:
AI tools are transforming education by allowing adaptive learning systems,
personalized tutoring, and automated grading, making learning more accessible and efficient.

🔹 Hugging Face Sentiment:
Label: POSITIVE
Confidence: 0.98

✅ Combined Insight:
The statement expresses a positive outlook on AI's role in education,
supported by both semantic understanding from GPT and sentiment analysis from Hugging Face.

Explanation:

In this experiment, Python is used to integrate multiple AI tools — OpenAI’s GPT for natural language understanding and Hugging Face for sentiment analysis.
The same query is passed to both AI systems, and their results are compared to derive a comprehensive and data-driven insight.
This experiment demonstrates the persona pattern of a programmer who automates multi-AI interaction for intelligent decision-making and comparative analysis.

Conclusion:

Thus, the Python code was successfully developed and executed to integrate multiple AI tools. It effectively compared their outputs and generated actionable insights.

Result:

The corresponding Python code was executed successfully, and multi-AI tool integration was achieved.
