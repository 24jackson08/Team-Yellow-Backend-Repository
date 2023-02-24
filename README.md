# Team-Yellow-Backend-Repository

from flask import Flask, request, jsonify
from flask_sqlalchemy import SQLAlchemy
from flask_marshmallow import Marshmallow
from flask_cors import CORS
import os

# import requests
# from bs4 import BeautifulSoup

app = Flask(__name__)
CORS(app)

basedir = os.path.join(os.path.dirname(__file__))
app.config['SQLAlchemy_DATABASE_URI'] = 'sqlite:///' + \
    os.path.join(basedir, 'app.sqlite')

db = SQLAlchemy(app)
ma = Marshmallow(app)


class Movie(db.Model):
    id = db.Column(db.Integer, primary_key=True, nullable=False)
    title = db.Column(db.String, nullable=False, unique=True)
    rating = db.Column(db.Integer)
    genre = db.Column(db.String, nullable=False, unique=True)
    img = db.Column(db.String, nullable=False, unique=True)


# @app.route('/')
def add_movie():
    # url= 'https://www.imbd.com/chart/top/'
    response = requests.get(url)
    title = input("Enter title of the film: ")
    rating = input("Enter rating of the film: ")
    year = input("Enter year of the film: ")
    genre = input("Enter genre of the film: ")
    movies.append(Movie(title=title, rating=rating, year=year, genre=genre))

    def __init__(self, title, rating, year, genre):
        self.title = title
        self.rating = rating
        self.year = year
        self.genre = genre

    def list_movies():
        quantity = one(movies)
        titles = [movie['title'] for movie in movies]
        titles = ' , '.join(titles)

        if quantity > 0:
            print("You have the following movies in your collection: (titles)")
        print("There are no movies in your collection")


#print("Movie list:")

# print(f"{movie['title']} ({movie['year']})")


title = post_data.get('title')
