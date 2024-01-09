from chatterbot import ChatBot
from chatterbot.trainers import ChatterBotCorpusTrainer

# Create a new chatbot instance
chatbot = ChatBot('MyChatBot')

# Create a new trainer for the chatbot
trainer = ChatterBotCorpusTrainer(chatbot)

# Train the chatbot on English language data
trainer.train('chatterbot.corpus.english')

# Main loop for chatting
while True:
    user_input = input("You: ")
    
    # Exit the loop if the user types "exit"
    if user_input.lower() == 'exit':
        break

    # Get the chatbot's response
    response = chatbot.get_response(user_input)
    
    print("Bot:", response)from chatterbot import ChatBot
from chatterbot.trainers import ChatterBotCorpusTrainer, ListTrainer

# Create a new chatbot instance
chatbot = ChatBot('MyChatBot')

# Create a new trainer for the chatbot
trainer = ChatterBotCorpusTrainer(chatbot)

# Train the chatbot on English language data
trainer.train('chatterbot.corpus.english')

# Create a new trainer for custom responses
list_trainer = ListTrainer(chatbot)

# Train the chatbot on a list of custom responses
custom_responses = [
    "Hello!",
    "How are you?",
    "What is your name?",
    "Tell me a joke.",
    # Add more custom responses as needed
]

list_trainer.train(custom_responses)

# Main loop for chatting
while True:
    user_input = input("You: ")
    
    # Exit the loop if the user types "exit"
    if user_input.lower() == 'exit':
        break

    # Get the chatbot's response
    response = chatbot.get_response(user_input)
    
    # If the confidence is low, provide a default response
    if response.confidence < 0.7:
        print("Bot: I'm not sure how to respond to that.")
    else:
        print("Bot:", response)from chatterbot import ChatBot
from chatterbot.trainers import ChatterBotCorpusTrainer, ListTrainer

# Create a new chatbot instance
chatbot = ChatBot('MyChatBot')

# Create a new trainer for the chatbot
trainer = ChatterBotCorpusTrainer(chatbot)

# Train the chatbot on English language data
trainer.train('chatterbot.corpus.english')

# Create a new trainer for custom responses
list_trainer = ListTrainer(chatbot)

# Train the chatbot on a list of custom responses
custom_responses = [
    "Hello!",
    "How are you?",
    "What is your name?",
    "Tell me a joke.",
    # Add more custom responses as needed
]

list_trainer.train(custom_responses)

# Main loop for chatting
while True:
    user_input = input("You: ")
    
    # Exit the loop if the user types "exit"
    if user_input.lower() == 'exit':
        break

    # Get the chatbot's response
    response = chatbot.get_response(user_input)
    
    # If the confidence is low, ask the user for a new response
    if response.confidence < 0.7:
        print("Bot: I'm not sure how to respond to that.")
        print("Bot: Can you help me with a response? (Type 'exit' to end)")
        new_response = input("You: ")
        
        # Exit the loop if the user types "exit"
        if new_response.lower() == 'exit':
            break

        # Add the new response to the training data
        list_trainer.train([new_response])
        print("Bot: Thanks for teaching me!")

    else:
        print("Bot:", responsespython chatbot.py
