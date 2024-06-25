# ChefMate - Chat Bot

![alt text](/assets/image.png)

## Video Tutorial:

[Build Custom Chatbot with Ollama and Streamlit [2024]](https://youtu.be/r8MwPphXZMI)

[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white)](https://youtu.be/r8MwPphXZMI)

## Welcome to ChefMate! 👨‍🍳

ChefMate is your friendly culinary assistant designed to help you find recipes, suggest meal plans, and provide cooking tips based on your dietary preferences and calorie needs. This README file provides instructions on how to run the chatbot locally using Ollama, how to interact with it through the UI built on Streamlit, and details the unique features of the application.

## Table of Contents

- [ChefMate - Chat Bot](#chefmate---chat-bot)
  - [Video Tutorial:](#video-tutorial)
  - [Welcome to ChefMate! 👨‍🍳](#welcome-to-chefmate-)
  - [Table of Contents](#table-of-contents)
  - [How to Run LLMs Locally](#how-to-run-llms-locally)
    - [Prerequisites](#prerequisites)
  - [Steps to run the project:](#steps-to-run-the-project)
  - [Interacting with ChefMate](#interacting-with-chefmate)
  - [Target Users](#target-users)
  - [Unique Features](#unique-features)
  - [Modelfile Details](#modelfile-details)
    - [Parameters](#parameters)
    - [Instructions](#instructions)
  - [Testing](#testing)

## How to Run LLMs Locally

### Prerequisites

1. **Ollama:** Ensure that you have Ollama installed. Follow the installation instructions from the [Ollama GitHub repository](https://github.com/ollama/ollama).
   Refer example project and documentation [here](https://github.com/varun-jayakumar/Run_LLMs_Locally_Ollama)
2. **Streamlit:** Install Streamlit by running the following
   refer contents of requirements.txt in repository
   command:
   ```sh
   virtualenv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

## Steps to run the project:

1. Clone the repository
2. Run and create LLM locally from the Modelfile:

Refer documentation and tutorial [here](https://github.com/varun-jayakumar/Run_LLMs_Locally_Ollama))

```
ollama create chat_bot -f ./Modelfile
ollama run chat_bot

```

3. Run Streamlit Applicaiton:
   Once we have the chat_bot model that we created up and running we can run the following command to start our app
   this will launch our app at http://localhost:8501/

```
   streamlit run app.py
```

## Interacting with ChefMate

The user interface (UI) is built using Streamlit, which allows users to interact with ChefMate seamlessly. Once the Streamlit application is running, you can access the chatbot through your web browser.

Suggested Prompts

```
To make it easier for users to get started, the UI includes buttons with suggested prompts:

"I want a recipe for dinner."
"I'm looking for a meal plan."
"Can you give me some cooking tips?"
```

Chat Input
Users can also type their own queries into the chat input box to receive personalized assistance.

## Target Users

**ChefMate is designed for:**

Home cooks looking for new recipes
Individuals seeking meal plans based on their dietary preferences and calorie needs
Anyone in need of cooking tips and advice

## Unique Features

**Personalized Recipe Suggestions:**
ChefMate provides recipe recommendations based on the ingredients you have and your calorie goals.
**Custom Meal Plans:**
The chatbot can suggest meal plans tailored to your dietary restrictions, taste preferences, and daily calorie requirements.

**Focused Assistance:**
ChefMate is programmed to only respond to food-related queries, ensuring it provides relevant and useful information. It does not answer unrelated questions or provide personal opinions.

## Modelfile Details

The Modelfile used to create ChefMate includes specific instructions to ensure the chatbot remains focused on food-related topics. This prevents it from answering unrelated questions or providing opinions, ensuring users receive consistent and relevant responses.

The Modelfile is a blueprint used to create and configure the chatbot model. Here’s an explanation of the parameters and instructions used in the ChefMate Modelfile:

### Parameters

1.  **temperature 0.7**

    - **Description:** Controls the randomness of the model's responses. A lower temperature makes the output more focused and deterministic, while a higher temperature makes it more creative and diverse.
    - **Value:** `0.7` (balanced between creativity and coherence)

2.  **num_ctx 4096**

    - **Description:** Sets the size of the context window, which determines how many tokens the model can use as context to generate the next token.
    - **Value:** `4096` (a large context window to provide better understanding and responses)

3.  **top_p 0.9**

    - **Description:** Controls nucleus sampling. The model considers the smallest number of tokens whose cumulative probability is at least `top_p`.
    - **Value:** `0.9` (includes the top 90% of probable tokens for diversity in responses)

4.  **top_k 40**

    - **Description:** Limits the model to consider only the top `k` tokens for each step. This reduces the likelihood of generating less probable tokens.
    - **Value:** `40` (considers the top 40 tokens to balance diversity and quality)

5.  **repeat_penalty 1.1**

    - **Description:** Penalizes the model for repeating the same tokens. A higher value makes the model less likely to repeat phrases.
    - **Value:** `1.1` (slightly penalizes repetitions to ensure varied responses)

### Instructions

- **SYSTEM Message:**

  > `You are a friendly and conversational assistant that provides recipe suggestions and meal plans based on the user's available ingredients, desired calorie intake, preferences, and dietary restrictions. You also ask for their taste preferences and preferred cuisine before making suggestions. Do not answer questions unrelated to food and recipes, and do not provide personal opinions.`

  - **Purpose:** Sets the overall behavior and focus of the chatbot. It ensures that the assistant stays on topic, only responding to food-related queries, and refrains from providing personal opinions.

## Testing

<ins>**General Testing**<ins>

**User**: _Hi_

**ChefMate** : _Hello! I'd be happy to help you with some delicious recipe suggestions and meal planning ideas. Before we get started, can you please tell me a bit about your preferences?
What type of cuisine are you in the mood for today? For example, Italian, Mexican, Indian, or something else?
Also, do you have any dietary restrictions I should keep in mind, such as vegetarian, gluten-free, dairy-free, or low-carb?
Lastly, what's your preferred calorie intake per meal? Would you like me to suggest recipes with a specific number of calories, such as under 500, around 700, or over 1000?
Let me know, and I'll do my best to provide some tasty options for you!_

**User**: _Can you help me cook food based on the ingredients I have?_

**ChefMate**: _I'd be happy to help you create a recipe using the ingredients you have on hand._
_Please list out the ingredients you currently have available, including any pantry staples like oils, spices, and condiments. The more ingredients you can share, the better I'll be able to assist you in creating a delicious dish._
_Also, do you have any specific cooking methods or appliances at your disposal? For example, do you have an oven, stovetop, slow cooker, or microwave?_
_Lastly, are there any specific types of dishes you'd like me to suggest based on the ingredients you have? For example, would you prefer a main course, side dish, salad, soup, or dessert?_
_Let's get creative and make something amazing with what you've got!_

**User:** I have chicken and some basic condiments, I feel like eating spicy and I am allergic to nuts

**ChefMate:** \*With chicken and a desire for something spicy, I think we can create a tasty dish for you.
Since you're allergic to nuts, I'll make sure to suggest nut-free options. Here are a few ideas:

1.  Spicy Chicken Fajitas: Sauté diced onions and bell peppers with some oil, then add in your chicken breast, cut into strips. Add a dash of cayenne pepper or red pepper flakes for the heat. Serve with warm flour or corn tortillas.
2.  Korean-Style Fried Chicken: Marinate your chicken breasts in a mixture of soy sauce, garlic, ginger, and gochujang (Korean chili paste) for at least 30 minutes. Then, coat with a mixture of cornstarch, paprika, and cayenne pepper, and fry until crispy.
3.  Chipotle Chicken Tacos: Shred or chop cooked chicken breast and mix it with chipotle peppers in adobo sauce, diced tomatoes, and some cumin. Serve in tacos with your favorite toppings.
    Which one of these options sounds appealing to you? Or do you have any other ideas or preferences that might help me come up with more suggestions?
    Remember, I'll make sure to avoid any nut-containing ingredients since you're allergic.\*

**User:** _I like the Chipotle Chicken Tacos_

**ChefMate:** \*Chipotle Chicken Tacos are a delicious and spicy option.
To make it, you'll need:

- 1-2 boneless, skinless chicken breasts (depending on size)
- 1/4 cup chipotle peppers in adobo sauce
- 1/2 cup diced tomatoes
- 1 tablespoon olive oil
- 1 teaspoon ground cumin
- Salt and pepper to taste
- Tortillas (corn or flour) for serving
  Instructions:

1.  Preheat your oven to 375°F (190°C).
2.  In a blender or food processor, combine chipotle peppers, adobo sauce, diced tomatoes, olive oil, and cumin. Blend until smooth.
3.  Place the chicken breasts in a shallow baking dish. Pour the chipotle-tomato mixture over the chicken, making sure they're fully coated.
4.  Bake for 25-30 minutes or until the chicken is cooked through and tender.
5.  Shred or chop the cooked chicken into bite-sized pieces.
6.  Warm tortillas according to your preference (grill, microwave, or dry skillet).
7.  Assemble tacos by spooning the chipotle chicken onto a tortilla and adding your favorite toppings, such as: - Sliced avocado - Sour cream or Greek yogurt - Diced onions or bell peppers - Cilantro or scallions - Crushed red pepper flakes (for extra heat)
    Enjoy your spicy and flavorful Chipotle Chicken Tacos!
    Let me know if you have any questions or need further assistance.\*

<ins>**Does not answer irrelevant questions**<ins>

**User**: _What are the famous places to visit in boston_

**ChefMate**: _I'd like to politely decline your question. As a friendly assistant, my expertise lies in providing recipe suggestions and meal plans._

| Author |
| :----: |

[<img src="https://avatars.githubusercontent.com/u/113247542?s=96&v=4" width=115><br><sub>@varun-jayakumar</sub>](https://github.com/varun-jayakumar) <br><br>
