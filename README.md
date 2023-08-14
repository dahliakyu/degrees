# Degrees

## Project brief

A programme that determines how many "degrees of separation" apart two actors are.

Data in `small` folder is a smaller subset of data in `large` folder that can be used for testing. Only the small folder is included in this repository.

### Raw data files

In each folder there are three `csv` files.

In `people.csv`, each person has a unique `id`, correspoding with their id in IMDb's data base. They also have a `name` and `birth` year.

In `movies.csv`, each movie has a unique `id`, in addition to a `title` and the `year` in which the movie was released.

In `stars.csv`, each row is a pair of a `person_id` value and `movie_id` value that represents a relationship between the people in `people.csv` and the movies in `movies.csv`.

### Data structures

In `degrees.py`, several data structures are defined to store the information from the CSV files. The `names` dictionary is a way to look up a person by their name: maps names to set of corresponding ids to avoid same name problem. The people dictionary maps each person's id to another dictionary with values for person's `name`, `birth` year and the set of all the `movies` that they starred in. And the `movies` dictionary maps each movie's id to another dictionary with values for that movie's `title`, release `year`, and the set of all the movies `starts`.

### Functions

The `load_data` function loads data into memory (the directory, either small or large, from which the data is loaded can be specified by a command-line argument, large directory is selected by default). Then, the function prompts the user to type in two names.

The `person_id_for_name` function retrieves the id for any person (and handles prompting the user to clarify, in the event that multiple people have the same name). The function then calls the `shortest_path` function to compute the shortest path between the two people, and prints out the path.
