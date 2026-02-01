# my-seventh-repo
just testing my repo
from flask import Flask, request, jsonify

app = Flask(__name__)
notes = []

@app.route("/notes", methods=["GET", "POST"])
def manag_notes():
    if request.method == "POST":
        note = request.json.get("note")
        notes.append(note)
        return jsonify({"message": "Note added!"}), 201
    return jsonify(notes)

if __name__ == "__main__":
    app.run(debug=True)
