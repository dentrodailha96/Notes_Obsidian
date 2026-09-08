- .gitignore : file that specifies intentionally untracked files that Git should ignore. It is useful listing secret files etc.
- .venv/ — The Python virtual environment. It's a folder containing an isolated Python installation and all installed **packages** (Flask, psycopg2, etc). You need it to run the app without
  polluting your system Python. You create it once with python3 -m venv venv, activate it, and then pip install goes there.
- .env — A plain text file with secret configuration values (DATABASE_URL, SECRET_KEY, etc.). Your Python code reads it at runtime via python-dotenv. This is how the app knows which database to connect to without hardcoding credentials in source code.
- requirements.txt: is the file that list all the python libraries to run the app. 