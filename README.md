\\# chat-bot.-ai
import openai

def chatbot():
    openai.api_key = 'your-api-key-here'  # Replace with your OpenAI API key
    print("AI Chatbot: Type 'exit' to end the chat.")
    
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'exit':
            print("Chatbot: Goodbye!")
            break
        
        response = openai.ChatCompletion.create(
            model="gpt-3.5-turbo",
            messages=[{"role": "user", "content": user_input}]
        )
        
        print("Chatbot:", response['choices'][0]['message']['content'])

if __name__ == "__main__":
    chatbot()
