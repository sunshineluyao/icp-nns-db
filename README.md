# Internet Computer Protocol NNS Governance System Database

## Summary Description

The **Internet Computer Protocol NNS Governance System Database** repository provides an organized structure for setting up and managing a development environment, primarily centered around database systems. The repository guides the user through the process of setting up the development environment with `pipenv`, details various database options such as SQLite, MySQL, and PostgreSQL, and their respective local and cloud management tools. Additionally, there's a thorough guide on leveraging Git Large File Storage (LFS) to track and handle larger files, ensuring that repositories remain lightweight and efficient. Lastly, a notable inclusion is the section dedicated to Kaggle's Data Explorer for the Internet Computer Protocol NNS Proposals dataset, detailing the formats available and a link to a demo notebook to kick-start data analysis endeavors.

## Table of Contents
1. **[Environment Setup](#Environment-Setup)**
    - [Prerequisites](#Prerequisites)
    - [Installation and Setup](#Installation-and-Setup)

2. **[Database Options](#Database-Options)**
    - [SQLite](#SQLite)
        - Description
        - Use Cases
        - Local Management Tools
        - Cloud Hosting Options
    - [MySQL](#MySQL)
        - Description
        - Use Cases
        - Local Management Tools
        - Cloud Hosting Options
    - [PostgreSQL](#PostgreSQL)
        - Description
        - Use Cases
        - Local Management Tools
        - Cloud Hosting Options
        - Advanced Options

3. **[Use Git LFS to track and add large files](#Use-Git-LFS-to-track-and-add-large-files)**
    - [Initialize Git LFS](#Initialize-Git-LFS)
    - [Track Files](#Track-Files)
    - [Add the Files](#Add-the-Files)
    - [Commit and Push](#Commit-and-Push)

4. **[Data Explorer on Kaggle](#Data-Explorer-on-Kaggle)**
    - [Overview](#Overview)
    - [File Formats](#File-Formats)
    - [Exploring the Data](#Exploring-the-Data)

### Prerequisites

This project utilizes [`pipenv`](https://pipenv.pypa.io/en/latest/) for package management. Ensure you have it installed and set up correctly by following the steps below. 

> **Tip**: We recommend using the [ChatGPT code interpreter](https://www.openai.com/chatgpt) for debugging purposes.

### Installation and Setup

1. **Install Pipenv**:

   Install the package and confirm its version with:
   
   ```shell
   pip install pipenv 
   pipenv --version
   ```

2. **Add Pipenv to the System Path**:

   To make `pipenv` accessible from any terminal window, you might need to add it to your system's PATH. First, find the installation location:
   
   ```shell 
   pip show pipenv | grep Location
   ```

   Then, add it to the PATH. Replace `path_to_site-packages` with the actual path you got from the above command:
   
   ```shell 
   export PATH="$PATH:/path_to_site-packages/pipenv"
   ```

3. **Create the Virtual Environment**:

   Activate the virtual environment using:
   
   ```shell 
   pipenv shell
   ```

## Database Options

The project can be configured to use various database management systems. For each option, we've detailed the primary local management tools and notable cloud hosting services available:

1. **SQLite**:
    - **Description**: SQLite is a C-language library that provides a lightweight, serverless, self-contained SQL database engine. 
    - **Use Cases**: Ideal for small to medium-sized applications, prototypes, or when a minimal setup with no configuration is preferred.
    - **Local Management Tools**:
        - **DB Browser for SQLite**: A high-quality, visual tool to create, design, and edit SQLite database files. [Website](https://sqlitebrowser.org/)
        - **SQLiteStudio**: A SQLite database manager with an intuitive interface, all tools and features bundled together. [Website](https://sqlitestudio.pl/)
    - **Cloud Hosting Options**: Given SQLite's serverless and embedded nature, it is less common to see dedicated cloud-hosting solutions. Instead, SQLite databases are typically embedded within applications hosted on cloud platforms like [AWS](https://aws.amazon.com/), [Azure](https://azure.microsoft.com/), or [Google Cloud](https://cloud.google.com/).

2. **MySQL**:
    - **Description**: MySQL is an open-source relational database system known for its speed and reliability.
    - **Use Cases**: Suitable for a wide range of applications, especially web applications.
    - **Local Management Tools**:
        - **MySQL Workbench**: A unified visual tool for database architects, developers, and DBAs. [Website](https://www.mysql.com/products/workbench/)
        - **phpMyAdmin**: A free software tool written in PHP, offering a web interface for MySQL administration. [Website](https://www.phpmyadmin.net/)
    - **Cloud Hosting Options**:
        - **Amazon RDS (MySQL)**: Managed relational database service by AWS that supports MySQL. [Website](https://aws.amazon.com/rds/mysql/)
        - **Google Cloud SQL for MySQL**: Fully-managed MySQL service by Google Cloud. [Website](https://cloud.google.com/sql/docs/mysql)
        - **Azure Database for MySQL**: Managed MySQL services provided by Microsoft Azure. [Website](https://azure.microsoft.com/services/mysql/)

3. **PostgreSQL**:
    - **Description**: PostgreSQL is an open-source relational database that focuses on extensibility and compliance with SQL standards.
    - **Use Cases**: Ideal for complex applications requiring advanced data types or geospatial support.
    - **Local Management Tools**:
        - **pgAdmin**: The most popular administration and management tool for the PostgreSQL database. [Website](https://www.pgadmin.org/)
        - **DBeaver**: Free multi-platform database tool for developers and database administrators that supports PostgreSQL. [Website](https://dbeaver.io/)
    - **Cloud Hosting Options**:
        - **Amazon RDS (PostgreSQL)**: AWS's managed service that makes it easy to set up, operate, and scale PostgreSQL deployments. [Website](https://aws.amazon.com/rds/postgresql/)
        - **Google Cloud SQL for PostgreSQL**: Managed PostgreSQL service offered by Google Cloud. [Website](https://cloud.google.com/sql/docs/postgres)
        - **Azure Database for PostgreSQL**: Fully managed, enterprise-ready PostgreSQL database service provided by Azure. [Website](https://azure.microsoft.com/services/postgresql/)
    - **Advanced Options**:
        - **GraphQL Integration**:
            - **Description**: Transform your PostgreSQL database into a GraphQL API without manually defining all resolvers.
            - **Tools**:
                - **Hasura**: Automatically generates a GraphQL API based on your PostgreSQL schema. Allows for real-time data, remote schemas, and role-based data access. [Website](https://hasura.io/)


                - **PostGraphile**: Instant, highly-performant GraphQL API for your PostgreSQL database. Supports plugins and can handle complex schemas. [Website](https://www.graphile.org/postgraphile/)

## Use Git LFS to track and add large files:

1. **Initialize Git LFS**:
   
   Before you can use Git LFS, you must initialize it for your repository. This only needs to be done once per repository.
   
   ```bash
   git lfs install
   ```

2. **Track Files**:
   
   You need to tell Git LFS which files to track. This is done using the `git lfs track` command. For example, to track all `.pkl` files, you'd do:
   
   ```bash
   git lfs track "*.pkl"
   ```

   This command updates the `.gitattributes` file, indicating which file patterns should be managed by LFS.

3. **Add the Files**:
   
   Now, add the files to your repository like you would with standard Git. 

   ```bash
   git add .
   ```

   Note: This will add all changes. If you want to add specific files, replace the `.` with the specific file paths.

4. **Commit and Push**:
   
   Commit your changes:

   ```bash
   git commit -m "Add large files with Git LFS"
   ```

   Then push to your remote repository:

   ```bash
   git push origin main
   ```

Remember, each time you add a new type of file that you want to be managed by Git LFS, you need to use the `git lfs track` command with the appropriate file pattern. The `git lfs install` command, however, only needs to be run once per repository.

---

## Data Explorer on Kaggle

### Overview

Kaggle is a renowned platform for data science competitions, public datasets, and knowledge sharing. One such invaluable dataset hosted on Kaggle is related to the Internet Computer Protocol NNS Proposals. The dataset can be accessed via the following link: [ICP NNS Proposals Dataset](https://www.kaggle.com/datasets/sunshineluyaozhang/icp-nns-proposals).

### File Formats

The ICP NNS Proposals data is available in three primary file formats, catering to various analysis and computational needs:

1. **Pickle**:
    - **Description**: Pickle is a Python-specific binary serialization format. It's efficient for storing Python objects, especially data frames in pandas, but can't be easily read with other programming languages.
    - **How to Use**: In Python, you can load a pickle file using the pandas library.
      ```python
      import pandas as pd
      data = pd.read_pickle("path_to_file.pkl")
      ```

2. **JSON (JavaScript Object Notation)**:
    - **Description**: JSON is a lightweight data-interchange format that is easy for humans to read and write. It's commonly used for configuration files and data exchange between languages with different data structures.
    - **How to Use**: In Python, the `json` module can be used to load JSON files.
      ```python
      import json
      with open('path_to_file.json', 'r') as file:
          data = json.load(file)
      ```

3. **CSV (Comma Separated Values)**:
    - **Description**: CSV is a plain-text format used for structured data. It's straightforward and supported by many data processing tools, databases, and spreadsheet applications.
    - **How to Use**: In Python, the CSV can be loaded using the pandas library.
      ```python
      import pandas as pd
      data = pd.read_csv("path_to_file.csv")
      ```

### Exploring the Data

To dive deep into the dataset and explore its potential, visit the provided Kaggle link. Kaggle offers an interactive environment, called Kaggle Kernels, which allows for in-browser data analysis. This feature is especially handy for those who want to explore the data without downloading it or setting up a local environment. We also provide a demo notebook that can be used as a starting point for your analysis using kaggle kernels [Notebook URL](https://www.kaggle.com/code/sunshineluyaozhang/ic-nns-db-demo).
