# <div align="center">Langchain Services</div>

## Table of Contents

- [About](#about)
- [Structure](#structure)
- [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Usage](#usage)
    - [`app.py`](#apppy)
   

## About

In this article, I  build an application on RAG (Retrieval Augmented Generation)to answer academic questions using the source of scientific papers that we have collected (in pdf file format), using the LangChain library. In general, the pipeline of the project is as follows:

![alt text](image.png)


## Structure

```structure
├── chat_histories
├── data_source
│   ├── generative_ai
│   └── machine_learning
├── src
│   ├── app.py
│   ├── base
│   ├── chat
│   └── rag
└── test
```

This source directories are as follows:

**Executable Files in `app.py`:**

- **`app.py`** - Code file used to initialize API.

**Source Directories:**

- **data_source** - Directory used to store documents for building vector database systems.
- **src** - Includes all helper functions for the above executable files.
    - **base** - The code file used to declare the function that initializes the large language model.
    - **rag** - Folder used to store code related to RAG construction

## Getting Started

### Installation

1. Clone project repo

    ```
    git clone https://github.com/phatnguyen1510/langchain_rag.git
    ```


2. Donwload data

Require **wget** and **gdown** package

    ```
    $ pip install wget gdown
    $ cd data_source/generative_ai && python download.py
    $ cd ../machine_learning && python download.py
    ```

3. Run service

```
pip install -r dev_requirements.txt
uvicorn src.app:app --host "0.0.0.0" --port 5000 --reload
```

