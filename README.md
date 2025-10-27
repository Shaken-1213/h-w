# h-w
from flask import Flask, render_template
import random

app = Flask(__name__)

facts_list = [
    'Один из способов борьбы с технологической зависимостью - это поиск занятий, которые приносят удовольствие и улучшают настроение.',
    'Илон Маск утверждает, что социальные сети созданы для того, чтобы удерживать нас внутри платформы, чтобы мы тратили как можно больше времени на просмотр контента.',
    'Социальные сети имеют как позитивные, так и негативные стороны, и мы должны быть более осознанными в использовании этих платформ.'
]
coin = ['Орёл', 'Решка']


@app.route("/")
def hello_world():
    return render_template("index.html")

@app.route("/random_fact")
def func1():
    return f'<p>{random.choice(facts_list)}</p>'

@app.route("/new")
def new_page():
    return render_template("new.html")

@app.route("/secret")
def secret_page():
    return f'<h1>Секретная страница</h1><p>{random.choice(coin)}</p>'



app.run(debug=True)
