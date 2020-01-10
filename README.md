# my-first-blog

## Set up development environment

### Python backend

Create a local virtual environment with `virtualenv` and install the dependencies with `pip`.
```sh
pip install virtualenv
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
# Initialize the database
python manage.py migrate

# run server
python manage.py runserver
```
