## LLMInstallation Guide

# Introduction to setting up llama3
Llama3 is an advanced AI language model designed for diverse natural language processing tasks. This guide will walk you through the installation process to get Llama3 up and running on your local machine.

## System Requirements
Before starting the installation, ensure your system meets the follow system requirements,

Operating System: Linux, macOS, or Windowsv<br/>
Python Version: 3.8 or above<br/>
Memory: At least 8GB of RAM<br/>
Disk Space: Minimum 10GB of free space<br/>

## Installation
Clone the Repository
Clone the Llama3 repository from GitHub to your local machine using the following command:
```
git clone https://github.com/ollama/ollama.git
cd llama3
```
OR 
Download it from: https://ollama.com/download/OllamaSetup.exe

![image](https://github.com/YagneshBrahmbhatt/LocalLLMAssignment/assets/113946217/0915f5e4-468e-42b1-9d47-ae2bb2210f3c)

Run Initial Setup
Run the initial setup script to configure the application:
```
python setup.py
```
Verification
To verify the installation, run the application and check if it starts without any errors:
```
ollama
```
Screenshot Below,

![image](https://github.com/YagneshBrahmbhatt/LocalLLMAssignment/assets/113946217/bb9174c4-f649-43fa-a72b-d8a35f9d50c9)

To get started with the LLM,
Enter the command
```
ollama run llama3
```
And ask a question- Screenshot below,

![image](https://github.com/YagneshBrahmbhatt/LocalLLMAssignment/assets/113946217/7b4b3558-dfd5-47af-b0f9-332277f771d6)

To Verify it that ir runs properly on local machine just write the code.
```
curl http://127.0.0.1:11434/
```
Screenshot below<br/>
![image](https://github.com/YagneshBrahmbhatt/LocalLLMAssignment/assets/113946217/c5263ec1-ada5-4576-8426-67a681bbb960)


# Introduction to setting up GPT-Neo

GPT-Neo is an open-source implementation of EleutherAI's GPT-3 model, designed for natural language processing tasks such as textgeneration, completion, and more. This guide will walk you through the installation process to get GPT-Neo up and running on your local machine.

## System Requirements
Before starting the installation, ensure your system meets the following requirements:

Operating System: Linux, macOS, or Windows,<br/>
Python Version: 3.8 or above<br/>
Memory: At least 16GB of RAM<br/>
Disk Space: Minimum 20GB of free space<br/>
GPU: (Recommended) NVIDIA GPU with CUDA support for faster processing<br/>

## Installation
Clone the Repository
Clone the GPT-Neo repository from GitHub to your local machine using the following command:
```
git clone https://github.com/EleutherAI/gpt-neo.git
cd gpt-neo
```
Screenshot below

![image](https://github.com/YagneshBrahmbhatt/LocalLLMAssignment/assets/113946217/77310395-bb41-490a-9311-5b99269bc691)

Now create a python file, and write your desired script. 
For example,
```
from transformers import GPT2LMHeadModel, GPT2Tokenizer

model_name = "gpt2"  # Model name remains the same

tokenizer = GPT2Tokenizer.from_pretrained(model_name)
model = GPT2LMHeadModel.from_pretrained(model_name)

def generate_conversation(prompt):
    inputs = tokenizer(prompt, return_tensors="pt")
    outputs = model.generate(inputs.input_ids, max_length=200, num_return_sequences=1, no_repeat_ngram_size=2, early_stopping=True)
    text = tokenizer.decode(outputs[0], skip_special_tokens=True)
    return text

prompt = "Alice: How have you been lately?\nBob:"
conversation = generate_conversation(prompt)
print(conversation)
```

Now Run the code given below to execute this python file.
```
python run_gpt2
```
This should give you an output type:

![image](https://github.com/YagneshBrahmbhatt/LocalLLMAssignment/assets/113946217/9b777e9f-eba2-41e7-9551-56762275899a)

## Notes

Ensure you have a stable internet connection when running the scripts for the first time, as the models and tokenizers need to be downloaded. The scripts are set to generate text based on simple prompts. You can modify the prompts and other parameters (like max_length and num_return_sequences) to suit your requirements.

# Conclusion
This repository provides a simple and effective way to interact with local language models for generating text. Feel free to explore and modify the scripts to create more complex and interesting outputs.<br/>

If you encounter any issues or have suggestions for improvements, please feel free to create an issue or submit a pull request.<br/>

Happy coding!
