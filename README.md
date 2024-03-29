# Internet Computer Protocol NNS Governance System Database
<table width="100%" border="1" cellspacing="0" cellpadding="10">
    <tr>
        <td align="center">
            <img src="icp-nns-db.drawio.png" alt="ICP NNS DB Diagram" width="50%" />
        </td>
    </tr>
    <tr>
        <td>
            The <b>Internet Computer Protocol NNS Governance System Database</b> repository offers a holistic framework for establishing and managing a database-centric development environment. Inside the code folder, users can find tools to seamlessly set up their local environment, fetch data from the Internet Computer blockchain, handle automatic data updates and potential query failures, save data in various standard formats, and establish databases using diverse systems like SQLite, MySQL, and PostgreSQL. Additionally, the data folder contains both raw and processed data files in formats such as CSV, pickle, and JSON, all managed efficiently through Git Large File Storage (LFS). This repository not only provides guidance on setting up using <code>pipenv</code> and various database options but also places a spotlight on leveraging Git LFS and a dedicated section on Kaggle's Data Explorer for the Internet Computer Protocol NNS Proposals dataset, complete with a demo notebook to jumpstart data analysis projects.
        </td>
    </tr>
</table>

## Acknowledgments:
We also thank the DFINITY Foundation for their support and guidance throughout the project. We extend our heartfelt gratitude to Zesen Zhuang, whose invaluable contributions during the exploratory phases of this project, particularly in data querying and visualizations. 

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

## Environment Setup

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
# Data Dictionary for ICP NNS Governance System Dataset

## About the Dataset
The Internet Computer Protocol (ICP) operates under a decentralized governance system known as the Network Nervous System (NNS). This dataset provides a comprehensive account of proposals within the NNS, capturing the democratic governance process of the Internet Computer.

## Dataset Variables

| Variable | Definition | Description | Frequency | Range | Unit | Type | Sample Observations |
|----------|------------|-------------|-----------|-------|------|------|---------------------|
| `action` | Type of action | Indicates the intent of the proposal (propose, reject, execute) | Per proposal | - | - | String | "ExecuteNnsFunction" |
| `action_nns_function` | Specific NNS function | Identifies the exact NNS function addressed by the proposal | Per proposal | - | - | String | "NnsCanisterUpgrade" |
| `deadline_timestamp_seconds` | Voting deadline | Timestamp for the end of the voting period | Per proposal | - | Seconds | Integer | 1620340878 |
| `decided_timestamp_seconds` | Decision time | Timestamp when the decision on the proposal was made | Per proposal | - | Seconds | Float | 1620340878.0 |
| `executed_timestamp_seconds` | Execution time | Timestamp when the proposal was executed | Per proposal | - | Seconds | Integer | 0 |
| `failed_timestamp_seconds` | Failure time | Timestamp when the proposal was deemed unsuccessful | Per proposal | - | Seconds | Integer | 1 |
| `id` | Proposal identifier | Unique ID for each proposal | Per proposal | 0-104331 | - | Integer | 3 |
| `known_neurons_ballots` | Voting neurons | Record of neurons that voted | Per proposal | - | - | JSON | `[]` |
| `latest_tally` | Vote tally | Most recent vote count | Per proposal | - | - | JSON | `{'no': 0, 'yes': 31539577669890139}` |
| `payload` | Proposal details | Detailed JSON object of the proposal | Per proposal | - | - | JSON | `{...}` |
| `proposal_id` | Designated proposal ID | ID for the proposal | Per proposal | 0-104331 | - | Integer | 3 |
| `proposal_timestamp_seconds` | Proposal creation time | Timestamp for the inception of the proposal | Per proposal | - | Seconds | Integer | 1620339017 |
| `proposer` | Proposer address | Canister address that presented the proposal | Per proposal | - | - | String | "35.0" |
| `reject_cost_e8s` | Rejection cost | Expense linked to a proposal's rejection | Per proposal | - | e8 ICP units | Integer | 100000000 |
| `reward_status` | Reward status | Current state of the proposal's reward | Per proposal | - | - | String | "SETTLED" |
| `settled_at` | Conclusion time | Timestamp marking the proposal's conclusion | Per proposal | - | Date & Time | String | "2021-05-06 16:00:00" |
| `status` | Proposal status | Current standing of the proposal | Per proposal | - | - | String | "EXECUTED" |
| `summary` | Proposal overview | Concise overview of the proposal | Per proposal | - | - | String | "Upgrade ledger canister..." |
| `title` | Proposal title | Headline of the proposal | Per proposal | - | - | String | "Upgrade ledger canister to git commit 8a560f9..." |
| `topic` | Proposal topic | Primary theme or subject | Per proposal | - | - | String | "TOPIC_NETWORK_CANISTER_MANAGEMENT" |
| `updated_at` | Last update time | Last moment the proposal received modifications | Per proposal | - | Date & Time | String | "2021-08-05 15:50:43.155180" |
| `url` | Proposal link | Direct web link to the proposal | Per proposal | - | - | String | "[GitHub Link](https://github.com/dfinity/nns-proposals/...)" |

For detailed information on data generation and updates, visit our GitHub repository which also includes auto-update scheduling provisions for this dataset.

