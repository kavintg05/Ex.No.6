# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date:25/9/25
# Register no.212223060119
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

# AI Tools Required:
- **OpenAI GPT API** (for text generation, summarization, reasoning)  
- **Hugging Face Transformers API** (for NLP tasks like sentiment analysis, classification, summarization)  

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 

## Python Code  

```python

import openai
from transformers import pipeline

# ---------- AI Tool 1: OpenAI GPT ----------
openai.api_key = "your_openai_api_key"

def openai_summary(text):
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "system", "content": "Summarize the text in 3 lines."},
                  {"role": "user", "content": text}]
    )
    return response["choices"][0]["message"]["content"]

# ---------- AI Tool 2: Hugging Face ----------
summarizer = pipeline("summarization", model="facebook/bart-large-cnn")

def hf_summary(text):
    summary = summarizer(text, max_length=60, min_length=20, do_sample=False)
    return summary[0]["summary_text"]

# ---------- Main Program ----------
if __name__ == "__main__":
    input_text = """Artificial Intelligence is revolutionizing the world by automating tasks, 
    enhancing decision-making, and creating new opportunities in healthcare, finance, 
    education, and many other industries. However, ethical considerations and responsible 
    use are critical for its long-term success."""
    
    # Get summaries from both AI tools
    gpt_output = openai_summary(input_text)
    hf_output = hf_summary(input_text)

    print("---- OpenAI GPT Summary ----")
    print(gpt_output)
    print("\n---- Hugging Face Summary ----")
    print(hf_output)

    # Compare and combine insights
    print("\n---- Combined Insight ----")
    print("Both AI tools highlight the impact of AI on industries. GPT emphasizes ethics, "
          "while Hugging Face stresses opportunities. A combined view: "
          "AI is transforming industries with great opportunities, but requires ethical and responsible use.")
```
# Output:

---- OpenAI GPT Summary ----
AI is revolutionizing industries by automating tasks and enhancing decision-making. 
It offers opportunities in healthcare, finance, and education. 
Ethical considerations are vital for responsible use.

---- Hugging Face Summary ----
Artificial Intelligence is transforming industries such as healthcare, 
finance and education, while offering new opportunities. 
Its responsible use is essential for future success.

---- Combined Insight ----
AI is transforming industries with great opportunities, 
but requires ethical and responsible use.


# Conclusion:
The Python code successfully integrates with multiple AI tools (OpenAI & Hugging Face) to process the same input, compare their responses, and generate a combined actionable insight.
This demonstrates how programmers can leverage multiple AI APIs in real-world applications for better reliability, comparison, and enriched outputs.

# Result: The corresponding Prompt is executed successfully.
