import re

def respond_to_input(user_input):
    
    user_input = user_input.lower()
    
    if re.search(r'\bhello\b|\bhi\b', user_input):
        return "Hello! How can I help you today?"
    
    if re.search(r'\bhow are you\b', user_input):
        return "I'm just a bot, but I'm doing well! How can I assist you?"
    
    if re.search(r'\bwhat is your name\b', user_input):
        return "I am a simple chatbot. I don't have a name, but you can call me Chatbot."
    
    if re.search(r'\bhelp\b', user_input):
        return "Sure! I can help you with basic questions. Just ask me something."
    
    if re.search(r'\bbye\b|\bgoodbye\b', user_input):
        return "Goodbye! Have a great day!"
    
    
    return "I'm sorry, I didn't understand that. Can you please rephrase?"

def chat():
    print("Chatbot: Hi there! Type 'bye' to end the chat.")
    
    while True:
        user_input = input("You: ")
        if re.search(r'\bbye\b|\bgoodbye\b', user_input.lower()):
            print("Chatbot: Goodbye! Have a great day!")
            break
        
        response = respond_to_input(user_input)
        print(f"Chatbot: {response}")

if _name_ == "_main_":
    chat()
