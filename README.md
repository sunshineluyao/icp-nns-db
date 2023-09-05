# Internet Computer Protocol NNS Governance System Database

## Environment Setup

### Prerequisites

This project utilizes [`pipenv`](https://pipenv.pypa.io/en/latest/) for package management. Ensure you have it installed and set up correctly by following the steps below. 

> **Tip**: We recommend using the ChatGPT code interpreter for debugging purposes.

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
        - **DB Browser for SQLite**: A high-quality, visual tool to create, design, and edit SQLite database files.
        - **SQLiteStudio**: A SQLite database manager with intuitive interface, all tools and features bundled together.
    - **Cloud Hosting Options**: Given SQLite's serverless and embedded nature, it is less common to see dedicated cloud-hosting solutions. Instead, SQLite databases are typically embedded within applications hosted on cloud platforms like AWS, Azure, or Google Cloud.

2. **MySQL**:
    - **Description**: MySQL is an open-source relational database system known for its speed and reliability.
    - **Use Cases**: Suitable for a wide range of applications, especially web applications.
    - **Local Management Tools**:
        - **MySQL Workbench**: A unified visual tool for database architects, developers, and DBAs, providing SQL development, data modeling, and comprehensive administration tools.
        - **phpMyAdmin**: A free software tool written in PHP, offering a web interface for MySQL administration.
    - **Cloud Hosting Options**:
        - **Amazon RDS (MySQL)**: Managed relational database service by AWS that supports MySQL.
        - **Google Cloud SQL for MySQL**: Fully-managed MySQL service by Google Cloud.
        - **Azure Database for MySQL**: Managed MySQL services provided by Microsoft Azure.

3. **PostgreSQL**:
    - **Description**: PostgreSQL is an open-source relational database that focuses on extensibility and compliance with SQL standards.
    - **Use Cases**: Ideal for complex applications requiring advanced data types or geospatial support.
    - **Local Management Tools**:
        - **pgAdmin**: The most popular administration and management tool for the PostgreSQL database.
        - **DBeaver**: Free multi-platform database tool for developers and database administrators that supports PostgreSQL.
    - **Cloud Hosting Options**:
        - **Amazon RDS (PostgreSQL)**: AWS's managed service that makes it easy to set up, operate, and scale PostgreSQL deployments.
        - **Google Cloud SQL for PostgreSQL**: Managed PostgreSQL service offered by Google Cloud.
        - **Azure Database for PostgreSQL**: Fully managed, enterprise-ready PostgreSQL database service provided by Azure.
    - **Advanced Options**:
        - **GraphQL Integration**:
            - **Description**: Transform your PostgreSQL database into a GraphQL API without manually defining all resolvers.
            - **Tools**:
                - **Hasura**: Automatically generates a GraphQL API based on your PostgreSQL schema. Allows for real-time data, remote schemas, and role-based data access.
                - **PostGraphile**: Instant, highly-performant GraphQL API for your PostgreSQL database. Supports plugins and can handle complex schemas.
