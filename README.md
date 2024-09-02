# Simple ChatBot

## Overview

The **Simple ChatBot** is a customizable chatbot designed for various support-related tasks, such as reporting users, bots, bugs, and more. The chatbot's behavior is entirely driven by a JSON configuration file, allowing easy customization of the questions it asks and the flow of the conversation based on user input.

## Features

- **Customizable Question Flow**: Define questions, possible answers, and the subsequent questions based on user responses.
- **Dropdown and Input Fields**: The bot supports both dropdown menus for predefined options and text input fields for free-text responses.
- **Keyword-based Navigation**: User responses can trigger different questions based on the keywords or phrases they contain.
- **Default Next Question**: When no keywords are matched, the bot can proceed to a default next question.

## JSON Configuration

The bot's behavior is defined by a JSON configuration file. Below is an example of the structure and elements used in the configuration.

### Example JSON Configuration

```json
{
    "questions": [
        {
            "id": 1,
            "question": "What would you like to report?",
            "dropdown": ["user", "bot", "bug"],
            "keywords": {
                "user": 2
            }
        },
        {
            "id": 2,
            "question": "Which person would you like to report? Please give me the user ID.",
            "defaultNextQuestion": 4,
            "keywords": {}
        },
        {
            "id": 3,
            "question": "Why do you want to report this user? (Short answer)",
            "dropdown": ["insult", "threats", "spamming", "cyberbullying", "other"],
            "keywords": {
                "insult": 4,
                "threats": 5,
                "spamming": 6,
                "cyberbullying": 5,
                "other": 7
            }
        },
        {
            "id": 4,
            "question": "Have you had previous conflicts with this user?",
            "dropdown": ["yes", "no"],
            "keywords": {
                "yes": 8,
                "no": 9
            }
        },
        {
            "id": 5,
            "question": "Do you need psychological support? If your answer is yes, one of our team will contact you as soon as possible to support you during this time.",
            "dropdown": ["yes", "no"],
            "keywords": {
                "yes": 4,
                "no": 4
            }
        },
        {
            "id": 6,
            "question": "How often have you been spammed by this person at the current time?",
            "defaultNextQuestion": 4,
            "keywords": {}
        },
        {
            "id": 7,
            "question": "Could you please describe in keywords what the person does / has done?",
            "defaultNextQuestion": 4,
            "keywords": {}
        },
        {
            "id": 8,
            "question": "Please briefly describe the previous conflicts with the person.",
            "defaultNextQuestion": 4,
            "keywords": {}
        },
        {
            "id": 9,
            "question": "Can you share any screenshots, videos, or links to the relevant messages/channels?",
            "dropdown": ["yes", "no"],
            "keywords": {
                "yes": 10,
                "no": 11
            }
        }
    ]
}
