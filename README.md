import re

def chatbot():
    print("Hi! I'm ChatBuddy. How can I help you today?")
    
    while True:
        user_input = input("You: ").lower()

        # Exit condition
        if user_input in ["exit", "bye", "quit"]:
            print("ChatBuddy: Goodbye! Have a great day!")
            break

        # Greetings
        elif re.search(r'\b(hi|hello|hey)\b', user_input):
            print("ChatBuddy: Hello! How can I assist you?")

        # Asking about chatbot
        elif "your name" in user_input:
            print("ChatBuddy: I'm ChatBuddy, your friendly assistant!")

        # Time-related question
        elif "time" in user_input:
            from datetime import datetime
            now = datetime.now()
            print("ChatBuddy: The current time is", now.strftime("%H:%M:%S"))

        # Weather query (dummy response)
        elif "weather" in user_input:
            print("ChatBuddy: I'm not connected to the internet, but I hope the weather is nice!")

        # Default response
        else:
            print("ChatBuddy: I'm not sure how to respond to that. Can you rephrase?")

# Run the chatbot
chatbot()
