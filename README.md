# my-first-blog
Create a local virtual environment with `virtualenv` and install the dependencies with `pip`.

### Ensure you are using Python version 3
python3 --version  
 I have running in venv Python 3.8.2
### Once you're in that virtualenv run 
pip install -r requirements.txt
### Migrate database by running
python manage.py migrate
### Run the server by running
python manage.py runserver
  #### Starting development server:
   http://127.0.0.1:8000/
