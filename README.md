
from openai import OpenAI
import os

client = OpenAI(
    api_key=os.getenv("GROQ_API_KEY"),
    
    base_url="https://api.groq.com/openai/v1"
)

prompt = "Create JSON for 2 books with title, author and year and place."

response = client.chat.completions.create(
    model="openai/gpt-oss-120b",
    messages=[
        {"role": "user", "content": prompt}
    ]
)

print(response.choices[0].message.content.strip())












$env:GROQ_API_KEY=
