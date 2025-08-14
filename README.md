# Querying MongoDB Atlas from Google Colab (PyMongo)

This project shows how to connect a Google Colab notebook to a MongoDB Atlas cluster and run common queries (CRUD, filtering, aggregation, indexing, and pagination).

---

## Contents
- `notebooks/colab_mongodb.ipynb` – Colab notebook (example code below)
- `src/` – optional Python helpers (if you add them)
- `.env` – **NOT COMMITTED**; holds your `MONGODB_URI`

---

## Quick Start (5–10 mins)

### 1) Prerequisites
- A **MongoDB Atlas** account + free cluster
- A **Database User** with username & password
- Your **Connection String** (Atlas → *Connect* → *Drivers* → choose **Python**)
  - It looks like:  
    `mongodb+srv://<username>:<password>@<cluster>/<db>?retryWrites=true&w=majority&appName=<appname>`

> **Colab IP allowlist tip:** Atlas needs to allow the (changing) IP from Colab. In Atlas → **Network Access**, you can temporarily choose **“Allow Access from Anywhere (0.0.0.0/0)”**. This is convenient for demos but **not recommended for production**. Remove it when you’re done.

### 2) Create a database & collection (optional)
In Atlas, create (or let code create) a database, e.g. `AltSch_db`, and a collection, e.g. `students`.

### 3) Open the notebook in Google Colab
- Upload your `.ipynb` or start a new one at https://colab.research.google.com  
- Install dependencies in the first cell:

```python
!pip install pymongo python-dotenv

