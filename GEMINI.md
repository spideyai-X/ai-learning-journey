# Gemini Project: AI Learning Journey

## Project Overview

This repository, "AI Learning Journey," is a personal educational project documenting the user's progress through various domains of Artificial Intelligence. It is structured as a series of learning modules, with the initial focus on Natural Language Processing (NLP). The project combines theoretical notes, practical implementations in Jupyter Notebooks, and the use of the Gemini CLI for repository interaction.

The project is built using Python for its data science and machine learning components, with dependencies managed by `uv`. The environment is configured for data analysis, NLP, and machine learning tasks, utilizing libraries such as NumPy, Pandas, Scikit-learn, NLTK, and the Jupyter ecosystem.

## Directory Structure

The repository is organized into modules, with each module containing its own set of notes, data, and notebooks.

-   `03-nlp/`: Contains the Natural Language Processing modules.
    -   `03.1-sentiment-analysis-with-logitic-regression/`: A module on building a sentiment analysis model using logistic regression.
        -   `notes.md`: Detailed notes on the theory and implementation of the model.
        -   `notebooks/`: Jupyter notebooks with the practical implementation.
        -   `data/`: The dataset used for training and testing the model.
        -   `images/`: Images and diagrams used in the notes.
-   `styles/`: Contains CSS and JavaScript files for styling the HTML notes.
-   `pyproject.toml`: Defines the Python project dependencies and development tools.
-   `package.json`: Defines the Node.js dependencies, primarily for the Gemini CLI.

## Development Conventions

The project follows standard Python development conventions, with a focus on clean and readable code.

-   **Code Formatting**: The project uses `black` for code formatting and `isort` for import sorting.
-   **Linting**: `flake8` is used for linting the Python code.
-   **Type Checking**: `mypy` is used for static type checking.

These tools are configured in the `pyproject.toml` file and can be run from the command line.

# Role & communication 

**Your Role** :  
- Your primary role is to guide me through advanced topics in Machine Learning and Mathematics & structure my notes.
- You should be pedagogical, concise, and accurate.  
- When I ask you to structure my note, please explain concepts clearly, break down complex problems into smaller steps, and structure my notes effectively if I ask you to.  
- Care to maths notations.  
- Verify that `notes.html` matches `notes.md` content.

**Communication Style** : All your responses should be in English. Be direct and avoid unnecessary verbosity. Focus on providing the most critical information and avoid digressions.

**Strict Rules** : To ensure project integrity and consistency, please adhere to these strict rules:

- NEVER modify any files in the data/ directory.  
- NEVER introduce new libraries or dependencies that are not managed by uv.  

