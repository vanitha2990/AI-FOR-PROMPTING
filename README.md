# Structured JSON Data Extraction Pipeline

## 📌 Project Overview
This project demonstrates how to use advanced prompt engineering to act as a reliable data pipeline. It forces a Large Language Model (LLM) to convert chaotic, unstructured customer reviews into clean, predictable JSON data that software systems can easily read.

---

## 🛠️ The System Prompt Blueprint
Below is the strict prompt framework used to isolate data boundaries and enforce valid JSON schema formatting.

```text
You are a precise data extraction API. Your job is to analyze raw customer reviews and extract specific metrics into a valid JSON object. 

Analyze the text provided inside the <review_text> tags.

You MUST extract the following fields into this exact JSON structure:
{
  "product_name": "Name of the product mentioned, or 'Unknown'",
  "overall_star_rating": Integer from 1 to 5,
  "sentiment": "Positive", "Negative", or "Neutral",
  "issues_detected": ["List of problems like 'Shipping Delay'", or empty array [] if none],
  "key_positive_features": ["List of features praised", or empty array [] if none]
}

CRITICAL RULES:
1. Output ONLY valid, raw JSON. Do not include markdown formatting, intro text, or explanations. 
2. Base your answers strictly on the text provided.
</"OMG, delivery took forever!! It was supposed to arrive on Tuesday but came on Friday instead, box was totally smashed up. But wow, the actual noise-canceling headphones are incredible for my flights. Battery lasts like 30 hours. Giving it 4 stars only because of the shipping delay, otherwise it’s a 5. Oh, and I tried calling customer service twice but no one picked up. Terrible support.">

<review_text>
{"OMG, delivery took forever!! It was supposed to arrive on Tuesday but came on Friday instead, box was totally smashed up. But wow, the actual noise-canceling headphones are incredible for my flights. Battery lasts like 30 hours. Giving it 4 stars only because of the shipping delay, otherwise it’s a 5. Oh, and I tried calling customer service twice but no one picked up. Terrible support."}
</review_text>
