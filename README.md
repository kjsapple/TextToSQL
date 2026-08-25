# Prerequsites

python >= 3.11
docker for running local test database

# Getting started

### Create virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install .
```

### Set-up LLM

1. open `descriptors/default/t2sql_descriptor.json` with any text editor
2. set litellm settings to [router_model_list](https://docs.litellm.ai/docs/routing#quick-start)


# Run streamlit application

```bash
docker-compose up -d
streamlit run main.py
```

In the app: open "Documentation" tab and click on "Run schema indexing" - this will create the semantic layer of the database
You can start asking question right after it's finished.

# Connecting to your database

open descriptors/default/t2sql_descriptor.json with any text editor
set access to your database "db" object
in case if you needd to use ssh tunnel, add ssh_tunnel to your descriptor:

```json
"ssh_tunnel": {
    "username": "",
    "private_key_path": "",    
}
```

You can provide the documentation in the "documentation" tab or click on "Run schema indexing" - this will create the semantic layer of the database.

You can start using app just right after that.
