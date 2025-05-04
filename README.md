# Appoinment_bot
this is an appoinment Booking bot created with rasa framework

# Recommended Versions:

Python: 3.10.x (You are already using 3.10.13, which is suitable)
Rasa: 3.6.18 (A recent stable version from the 3.x series)
spaCy: 3.4.4 (Known to be compatible with Rasa 3.6.x)
spaCy Model: en_core_web_md (A medium-sized English model, adjust if you need a different language or size)

# Setting Up a Compatible Rasa and spaCy Environment

python3 -m venv venv //python 3.10.x 

    # macOS / Linux:

      source venv/bin/activate

    # Windows (Command Prompt):

      .\venv\Scripts\activate

pip install --upgrade pip
pip install rasa==3.6.18
pip install spacy==3.4.4

# if error while installing try:
  install this first 
        1)brew install libpq
        2)pip install psycopg2-binary
    # Download the spaCy Language Model:

python -m spacy download en_core_web_md

# Verify Installation:
# Check that the correct versions are installed and the model is linked.

pip list | grep -E 'rasa|spacy' # macOS/Linux
pip list | findstr "rasa spacy" # Windows

(This should show rasa 3.6.18 and spacy 3.4.4)

python -m spacy validate

# Train Your Rasa Model:

rasa train

Run the Rasa server:

bash# In terminal 1, start the Rasa server
rasa run --enable-api --cors "*" --debug

Run the action server:

bash# In terminal 2, start the action server
rasa run actions

Serve the web interface:

bash# In terminal 3, if you have Python installed
cd webchat
python -m http.server 8000
