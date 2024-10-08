# Simple ChatBot

## Overview

The **Simple ChatBot** is a customizable chatbot designed for various support-related tasks, such as reporting users, bots, bugs, and more. The chatbot's behavior is entirely driven by a JSON configuration file, allowing easy customization of the questions it asks and the flow of the conversation based on user input.

## Features

- **Customizable Question Flow**: Define questions, possible answers, and the subsequent questions based on user responses.
- **Dropdown and Input Fields**: The bot supports both dropdown menus for predefined options and text input fields for free-text responses.
- **Keyword-based Navigation**: User responses can trigger different questions based on the keywords or phrases they contain.
- **Default Next Question**: When no keywords are matched, the bot can proceed to a default next question.
- **End Key in json**: When end key is in json, the Conversation will end and the json data will be prepared to be sended to the backend.

## JSON Configuration

The bot's behavior is defined by a JSON configuration file. Below is an example of the structure and elements used in the configuration.
### Example JSON the Bot will send when end is activated
```json
[
  {
    "questionId": 1,
    "answer": "Technical Support"
  },
  {
    "questionId": 2,
    "answer": "Error Reporting"
  },
  {
    "questionId": 6,
    "answer": "my PC didnt fixed itself after restart"
  },
  {
    "questionId": 17,
    "answer": "no i dont need more"
  }
]
```
### Example JSON Configuration

```json
{
    "questions": [
        {
            "id": 1,
            "question": "Welcome! How can I assist you today?",
            "dropdown": ["Technical Support", "Account Maintenance", "General Questions", "Feedback"],
            "keywords": {
                "Technical Support": 2,
                "Account Maintenance": 3,
                "General Questions": 4,
                "Feedback": 5
            }
        },
        {
            "id": 2,
            "question": "What type of technical support do you need?",
            "dropdown": ["Error Reporting", "Installation", "Update", "Other"],
            "keywords": {
                "Error Reporting": 6,
                "Installation": 7,
                "Update": 8,
                "Other": 9
            }
        },
        {
            "id": 3,
            "question": "What type of account maintenance do you need?",
            "dropdown": ["Reset Password", "Change Account Information", "Delete Account", "Other"],
            "keywords": {
                "Reset Password": 10,
                "Change Account Information": 11,
                "Delete Account": 12,
                "Other": 13
            }
        },
        {
            "id": 4,
            "question": "Please specify your general inquiry:",
            "defaultNextQuestion": 14,
            "keywords": {}
        },
        {
            "id": 5,
            "question": "Thank you for your feedback! Would you like to add anything else?",
            "dropdown": ["Yes", "No"],
            "keywords": {
                "Yes": 15,
                "No": 16
            }
        },
        {
            "id": 6,
            "question": "Please describe the issue you are experiencing with error reporting:",
            "defaultNextQuestion": 17,
            "keywords": {}
        },
        {
            "id": 7,
            "question": "What type of installation assistance do you need?",
            "dropdown": ["Software", "Hardware", "Network", "Other"],
            "keywords": {
                "Software": 18,
                "Hardware": 19,
                "Network": 20,
                "Other": 21
            }
        },
        {
            "id": 8,
            "question": "Which update is related to your issue?",
            "dropdown": ["System", "Application", "Security", "Other"],
            "keywords": {
                "System": 22,
                "Application": 23,
                "Security": 24,
                "Other": 25
            }
        },
        {
            "id": 9,
            "question": "Please describe the other technical issue you are facing:",
            "defaultNextQuestion": 17,
            "keywords": {}
        },
        {
            "id": 10,
            "question": "Please provide your email address for password reset:",
            "defaultNextQuestion": 17,
            "keywords": {}
        },
        {
            "id": 11,
            "question": "What account information would you like to change?",
            "defaultNextQuestion": 17,
            "keywords": {}
        },
        {
            "id": 12,
            "question": "Please confirm the deletion of your account:",
            "dropdown": ["Confirm", "Cancel"],
            "keywords": {
                "Confirm": 17,
                "Cancel": 17
            }
        },
        {
            "id": 13,
            "question": "Please describe your other account maintenance concern:",
            "defaultNextQuestion": 17,
            "keywords": {}
        },
        {
            "id": 14,
            "question": "Do you have any other questions?",
            "dropdown": ["Yes", "No"],
            "keywords": {
                "Yes": 1,
                "No": 17
            }
        },
        {
            "id": 15,
            "question": "Please provide any additional information or comments you have:",
            "defaultNextQuestion": 17,
            "keywords": {}
        },
        {
            "id": 16,
            "question": "Thank you for your feedback! If you have any further questions, feel free to ask.",
            "defaultNextQuestion": 17,
            "keywords": {}
        },
        {
            "id": 17,
            "question": "Thank you for your inquiry! If you need further assistance, please let me know.",
            "end": true,
            "keywords": {}
        }
    ]
}


