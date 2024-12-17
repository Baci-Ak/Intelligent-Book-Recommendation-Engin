# Intelligent Recommendation System

![License](https://img.shields.io/github/license/Baci-Ak/Intelligent-Book-Recommendation-System)
![GitHub stars](https://img.shields.io/github/stars/Baci-Ak/Intelligent-Recommendation-System?style=social)
![GitHub forks](https://img.shields.io/github/forks/Baci-Ak/Intelligent-Book-Recommendation-System?style=social)

## Table of Contents
- [Overview](#overview)
- [Business Context and Problem](#business-context-and-problem)
- [Features](#features)
- [Similarity Metrics](#similarity-metrics)
- [Datasets](#datasets)
- [Modules](#modules)
- [Getting Started](#getting-started)
- [Usage](#usage)
  - [Loading Data](#loading-data)
  - [Computing Similarity](#computing-similarity)
  - [Running the Test Module](#running-the-test-module)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Overview

In the era of information overload, selecting relevant content from the vast expanse of online data has become increasingly challenging. This repository offers a collection of seven robust similarity metrics designed for intelligent recommendation engines. While originally developed for a book recommendation system, these metrics are versatile and can be adapted for various recommendation applications across different domains.

By leveraging these similarity metrics, developers and data scientists can enhance their recommendation systems, improving user satisfaction and engagement by delivering more personalized and accurate content suggestions.

## Business Context and Problem

With the ever-growing online content and the ubiquity of Internet-enabled devices, users are facing information overload. This overload leads to difficulties in making decisions on what content or products to consume or purchase. The project focuses on helping an online book selling company that has been experiencing declining sales due to the overwhelming choices and challenges customers face when selecting books to buy.

The company's management recognizes the need for an intelligent recommendation engine to assist users in finding books aligned with their interests. This engine will not only enhance sales by providing personalized recommendations but also improve customer satisfaction by simplifying the decision-making process.

## Features

- **Seven Similarity Metrics**: Includes Squared Euclidean Distance, Minkowski Distance, Spearman Correlation, Chebyshev Distance, Hamming Distance, Cosine Similarity, and Pearson Correlation.
- **Modular Design**: Organized into three primary modules for data loading, similarity computation, and testing.
- **Easy Integration**: Clone and integrate the metrics into your existing projects with minimal setup.
- **Flexible Usage**: Applicable to user-user, item-item, and user-item similarity computations.
- **Comprehensive Documentation**: Detailed explanations and usage guidelines to facilitate seamless implementation.

## Similarity Metrics

1. **Squared Euclidean Distance**
2. **Minkowski Distance**
3. **Spearman Correlation**
4. **Chebyshev Distance**
5. **Hamming Distance**
6. **Cosine Similarity**
7. **Pearson Correlation**

Each metric is implemented as a separate function within the `similarity_module`, allowing for easy selection and customization based on your specific recommendation needs.

## Datasets

Ensure you have the following datasets in the designated folders:

1. **Users.csv**: Contains user information including User-ID, Location, and Age.
2. **Books.csv**: Contains book details such as ISBN, Title, Author, Year of Publication, Publisher, and cover image URLs.
3. **Book-Ratings.csv**: Contains user ratings for books with columns UserId, ISBN, and Rating.

*Example of Book-Ratings.csv:*

![image](https://github.com/user-attachments/assets/d95beaf3-d1fa-4155-ac32-19ed47108eef)


## Modules

### 1. `load_dataset_module`
This module retrieves user, book, and rating information from CSV files. It populates a dictionary with user preferences, including user IDs, ISBNs, book titles, authors, publication years, and ratings.

### 2. `similarity_module`
This module implements seven similarity functions, calculating similarity scores between users and between books using different metrics. These functions help identify commonly rated books and compute similarity based on shared ratings. The seven implemented similarity matrices are:

- Squared Euclidean Distance
- Minkowski Distance
- Pearson Correlation
- Spearman Correlation
- Chebyshev Distance
- Hamming Distance
- Cosine Similarity

Each function accepts three parameters: the `user_preference` dictionary and two user IDs or book ISBNs. The functions first look up books commonly rated by both users and, based on these commonly rated books, return a similarity score between the two users or books.

### 3. `test_module`
This module provides an interactive interface for users to query and display similarity scores. Users can input user IDs or book ISBNs to explore the recommendation engine's functionality.

## Getting Started

### Prerequisites

- Python 3.6 or higher
- Git

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/Baci-Ak/Intelligent-Recommendation-System.git
   cd Intelligent-Recommendation-System
   ```

2. **Set Up a Virtual Environment (Optional but Recommended)**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

   *Note: If `requirements.txt` is not provided, ensure you have the necessary libraries such as `numpy`, `pandas`, and `scipy` installed.*

4. **Populate the Required CSV Files**

   Ensure you have the following CSV files in your working directory:
   - `Users.csv`
   - `Books.csv`
   - `Book-Ratings.csv`

## Usage

### Loading Data

```python
from load_dataset_module import load_user_preferences

user_preferences = load_user_preferences('path/to/Users.csv', 'path/to/Books.csv', 'path/to/Book-Ratings.csv')
```

### Computing Similarity

```python
from similarity_module import cosine_similarity

user1 = 'UserID_1'
user2 = 'UserID_2'

similarity_score = cosine_similarity(user_preferences, user1, user2)
print(f"Cosine Similarity between {user1} and {user2}: {similarity_score}")
```

### Running the Test Module

```bash
python test_module.py
```

This will launch an interactive prompt where you can:

- Query similarity between users.
- Query similarity between books.
- Exit the application.

### Using the Jupyter Notebook

Alternatively, you can interact with the system using the provided Jupyter Notebook:

1. Open the notebook:

   ```bash
   jupyter notebook using_the_system.ipynb
   ```

2. Follow the instructions within the notebook to load data, compute similarities, and explore the recommendation engine's functionality.

## Contributing

Contributions are welcome! Whether it's improving documentation, adding new similarity metrics, or enhancing existing functionalities, your input is valuable. Here's how you can contribute:

1. **Fork the Repository**
   
   Click the **Fork** button at the top right of this page to create a personal copy of this repository on your GitHub account.

2. **Clone Your Fork**
   
   ```bash
   git clone https://github.com/Baci-Ak/Intelligent-Recommendation-System.git
   cd Intelligent-Recommendation-System
   ```

3. **Create a New Branch**
   
   Create a branch for your feature or bug fix. Replace `YourFeature` with a descriptive name related to your work.
   
   ```bash
   git checkout -b feature/add-jaccard-similarity
   ```

4. **Make Your Changes**
   
   Implement your feature or fix in the codebase. Ensure your code follows the project's coding standards and includes relevant tests.

5. **Commit Your Changes**
   
   Commit your changes with a clear and descriptive message.
   
   ```bash
   git commit -m "Add Jaccard Similarity metric to similarity_module"
   ```

6. **Push to Your Fork**
   
   Push your branch to your forked repository on GitHub.
   
   ```bash
   git push origin feature/add-jaccard-similarity
   ```

7. **Open a Pull Request**
   
   Navigate to the original repository on GitHub. You should see a prompt to open a pull request from your recently pushed branch. Click **Compare & pull request**, provide a detailed description of your changes, and submit the PR.

### Example

If you’re adding a new similarity metric called **Jaccard Similarity**, your steps would look like this:

```bash
git checkout -b feature/add-jaccard-similarity
# Implement the Jaccard Similarity metric in similarity_module.py
git commit -m "Add Jaccard Similarity metric to similarity_module"
git push origin feature/add-jaccard-similarity
```

Then, open a pull request titled "Add Jaccard Similarity Metric" with a description of what you've added and why.

### Tips for Naming Branches

- **Be Descriptive**: Use clear and specific names that describe the purpose of the branch.
  - **Good Examples**:
    - `feature/add-cosine-similarity`
    - `bugfix/fix-data-loading`
    - `enhancement/improve-documentation`
- **Use Prefixes**: Prefixes like `feature/`, `bugfix/`, `enhancement/` help categorize the type of work being done.
- **Avoid Spaces and Special Characters**: Use hyphens (`-`) or underscores (`_`) to separate words.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions, suggestions, or feedback, please reach out to:

- **Name**: Bassey Akom
- **LinkedIn**: [linkedin.com/in/basseyakom](https://www.linkedin.com/in/basseyakom)
