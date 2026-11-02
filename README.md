## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:
To design and implement a LangChain Expression Language (LCEL) expression using at least two prompt parameters and three key components: PromptTemplate, ChatOpenAI Model, and StrOutputParser. The system should accept user inputs, generate a meaningful response using the language model, and convert the model output into readable text. The functionality is evaluated using different real-world examples.
### DESIGN STEPS:
1.Import Libraries: Import the required LangChain modules.
2.Load API Key: Load the OpenAI API key using the .env file.
3.Create Prompt Template: Define a prompt with two parameters: {topic} and {style}.
4.Initialize Model: Create a ChatOpenAI model with temperature set to 0.7.
5.Create Output Parser: Use StrOutputParser() to convert the model response into a string.
6.Build LCEL Chain: Connect the prompt, model, and output parser using the pipe (|) operator.
7.Provide Inputs: Pass two user inputs to the chain.
8.Execute and Test: Use invoke() to generate responses for different real-world scenarios.
### PROGRAM:
```
import os
from dotenv import load_dotenv
```
```
from langchain_core.prompts import ChatPromptTemplate
from langchain_openai import ChatOpenAI
from langchain_core.output_parsers import StrOutputParser
```
```
load_dotenv()
```
```
model = ChatOpenAI(
    model="gpt-4o-mini",
    temperature=0.7
)
```
```
prompt = ChatPromptTemplate.from_template(
    "Suggest {number} interesting {topic} ideas "
    "with a short explanation for each."
)
```
```
output_parser = StrOutputParser()
```
```
chain = prompt | model | output_parser
```
```
response = chain.invoke({
    "number": 3,
    "topic": "artificial intelligence project"
})
```
```
print("Generated Response:")
print(response)
```
### OUTPUT:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5ce5594b-2a02-4ba3-82bd-96cc2eedfa7d" />

### RESULT:
Thus, the LCEL expression was successfully implemented using two prompt parameters and three key components. The chain generated meaningful responses and demonstrated its applications in real-world scenarios.
