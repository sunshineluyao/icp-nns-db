# Internet Computer Governance Data Visualization

- [Internet Computer Governance Data Visualization](#internet-computer-governance-data-visualization)
  - [Environment Setup](#environment-setup)
  - [Folders](#folders)

## Environment Setup

Prerequesites:

- [Python](https://www.python.org/downloads/)
- [Pipenv](https://pipenv.pypa.io/en/latest/)

This project use `pipenv` for package management. Following the steps to create the environment
- install the package and confirm the version
```shell
pip install pipenv 
pipenv --version
```
- Add to the path
 ```shell 
pip show pipenv | grep Location
export PATH="$PATH:/path_to_site-packages/pipenv"
```
- create the environment
```shell 
pipenv shell
```

## Folders

| Folder  | Description                                                                     |
| ------- | ------------------------------------------------------------------------------- |
| code    | Jupyter notebooks containing code for fetching, processing and visualizing data |
| fonts   | Fonts file used in figures                                                      |
| figures | Figure produced from the code                                                   |
| data    | Auxiliary data files created by the code                                        |
