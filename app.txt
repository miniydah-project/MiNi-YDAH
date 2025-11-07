from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

@app.route('/alumni')
def alumni():
    alumni_list = [
        {"name": "Riya Sharma", "year": 2020, "dept": "Computer Science"},
        {"name": "Arjun Mehta", "year": 2019, "dept": "Mechanical"},
        {"name": "Sneha Kapoor", "year": 2021, "dept": "Electrical"}
    ]
    return render_template('alumni.html', alumni=alumni_list)

@app.route('/contact')
def contact():
    return render_template('contact.html')

if __name__ == '__main__':
    app.run(debug=True)
