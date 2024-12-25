# text2speech


!pip install gtts
from gtts import gTTS
import os

def text_to_speech(text, lang='en', filename='output.mp3'):
    try:
        # Initialize gTTS with text and language
        tts = gTTS(text=text, lang=lang, slow=False)
        tts.save(filename)
        print(f"Audio saved to {filename}")
        if os.name == 'nt':  # Windows
            os.system(f'start {filename}')
        elif os.name == 'posix':  # macOS or Linux
            os.system(f'open {filename}')
        else:
            print("Audio playback is not supported on this platform.")
    except Exception as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    
  print("Supported languages: Kannada (kn), Hindi (hi), English (en), etc.")
    user_text = input("Enter the text to convert to speech: ")
    user_lang = input("Enter the language code (e.g., kn for Kannada): ")
# Call the function
  text_to_speech(user_text, lang=user_lang)
