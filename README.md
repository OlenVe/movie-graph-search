# 🎬 Degrees of Separation

This project finds the shortest path between two actors or actresses based on the movies they’ve appeared in together, using **graph search algorithms**.

Inspired by the concept of ["Six Degrees of Kevin Bacon"](https://en.wikipedia.org/wiki/Six_Degrees_of_Kevin_Bacon), the program computes how closely two people in the film industry are connected by shared movies.

---

## 📁 Project Structure
```
├── degrees.py # Main program logic
├── util.py # Definitions of Node, StackFrontier, QueueFrontier
├── small/ # Small dataset (for testing)
│ ├── people.csv
│ ├── movies.csv
│ └── stars.csv
├── large/ # Full dataset (for full runs)
│ ├── people.csv
│ ├── movies.csv
│ └── stars.csv
```


---

## 🚀 Features

- Uses **Breadth-First Search (BFS)** to find the shortest path between two people
- Resolves name ambiguities (e.g., multiple people with the same name)
- Loads and processes data from `.csv` files (IMDb-like format)
- Outputs the list of actors and the movies they co-starred in along the shortest path

---

## 📦 Datasets

Each dataset contains three CSV files:

- `people.csv`: Actor ID, name, and birth year
- `movies.csv`: Movie ID, title, and release year
- `stars.csv`: Relationship between people and movies (many-to-many)

---

## 💻 Usage

### Run the program:

```bash
python degrees.py
```

Example interaction:
$ python degrees.py small
Loading data...
Data loaded.
Source Name: Emma Watson
Target Name: Tom Hanks
3 degrees of separation.
1: Emma Watson and Brendan Gleeson starred in Harry Potter and the Order of the Phoenix
2: Brendan Gleeson and Kevin Bacon starred in Movie XYZ
3: Kevin Bacon and Tom Hanks starred in Apollo 13
Time elapsed: 0.423 seconds


🔍 How It Works
Graph Representation
Nodes: Actors
Edges: Movies in which they co-starred
Search Algorithm
Breadth-First Search (BFS) via QueueFrontier
Tracks visited nodes to avoid cycles
Constructs the shortest path back from the target to the source using parent pointers
Ambiguity Resolution
If multiple people match the input name, the program lists all matches and prompts the user to choose the intended one by ID.

🧠 Dependencies
Python 3.6+
Standard libraries only (csv, sys, time)

📚 Credit
Based on the CS50 AI Project 0: Degrees
