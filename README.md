# ChefMate - Chat Bot

**Welcome to ChefMate!** 👨‍🍳

ChefMate is your friendly culinary assistant designed to help you find recipes, suggest meal plans, and provide cooking tips based on your dietary preferences and calorie needs. This README file provides instructions on how to run the chatbot locally using Ollama, how to interact with it through the UI built on Streamlit, and details the unique features of the application.

## Table of Contents

- [ChefMate - Chat Bot](#chefmate---chat-bot)
  - [Table of Contents](#table-of-contents)
  - [How to Run Locally](#how-to-run-locally)
    - [Prerequisites](#prerequisites)
  - [Steps:](#steps)
  - [Interacting with ChefMate](#interacting-with-chefmate)
      - [Suggested Prompts](#suggested-prompts)
      - [Target Users](#target-users)
      - [Unique Features](#unique-features)
    - [Modelfile Details](#modelfile-details)

## How to Run Locally

### Prerequisites

1. **Ollama:** Ensure that you have Ollama installed. Follow the installation instructions from the [Ollama GitHub repository](https://github.com/ollama/ollama).
2. **Streamlit:** Install Streamlit by running the following command:
   ```sh
   pip install streamlit
   ```

## Steps:

1. Clone the repository
2. Copy Modelfile from repo:

```
ollama create chat_bot -f ./Modelfile
ollama run chat_bot

```

3. Run Streamlit Applicaiton:

```
   streamlit run app.py
```

## Interacting with ChefMate

The user interface (UI) is built using Streamlit, which allows users to interact with ChefMate seamlessly. Once the Streamlit application is running, you can access the chatbot through your web browser.

#### Suggested Prompts

```
To make it easier for users to get started, the UI includes buttons with suggested prompts:

"I want a recipe for dinner."
"I'm looking for a meal plan."
"Can you give me some cooking tips?"
Clicking on these buttons will automatically enter the corresponding prompt into the chat input, making interaction smooth and intuitive.
```

Chat Input
Users can also type their own queries into the chat input box to receive personalized assistance.

#### Target Users

**ChefMate is designed for:**

Home cooks looking for new recipes
Individuals seeking meal plans based on their dietary preferences and calorie needs
Anyone in need of cooking tips and advice

#### Unique Features

**Personalized Recipe Suggestions:**
ChefMate provides recipe recommendations based on the ingredients you have and your calorie goals.
**Custom Meal Plans:**
The chatbot can suggest meal plans tailored to your dietary restrictions, taste preferences, and daily calorie requirements.

**Focused Assistance:**
ChefMate is programmed to only respond to food-related queries, ensuring it provides relevant and useful information. It does not answer unrelated questions or provide personal opinions.

### Modelfile Details

The Modelfile used to create ChefMate includes specific instructions to ensure the chatbot remains focused on food-related topics. This prevents it from answering unrelated questions or providing opinions, ensuring users receive consistent and relevant responses.
