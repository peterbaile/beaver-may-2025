# 🦫 BEAVER: An Enterprise Benchmark for Text-to-SQL (`BEAVER-MAY-2025` version)

### Updates
- 05/20/2026: The latest version of our benchmark is available at [https://beaverbench.github.io/](https://beaverbench.github.io/), featuring 8000 queries, a full leaderboard, and the evaluation code.
- 03/01/2025
  - Expanded DW queries so that in total there are 209 queries.
  - For a streamlined and rapid setup, we've translated all DW queries from Oracle SQL to MySQL dialect. A MySQL version of the DW database is also available in Google Drive. Please refer to [Setup](#setup) for more information.
  - Each DW query comes with a SQL statement in both Oracle and MySQL dialects, allowing for benchmarking tasks such as SQL dialect translation.
  - We are planning to release more queries and databases from a new source in the coming weeks.
- 01/19/2025: 191 queries and 463 tables across 6 databases are all available.
- 10/28/2024: A subset of 49 queries and 99 tables is available.

If you find our data or the paper helpful, please cite the paper
```
@article{chen2024beaver,
  title={BEAVER: an enterprise benchmark for text-to-sql},
  author={Chen, Peter Baile and Wenz, Fabian and Zhang, Yi and Yang, Devin and Choi, Justin and Tatbul, Nesime and Cafarella, Michael and Demiralp, {\c{C}}a{\u{g}}atay and Stonebraker, Michael},
  journal={arXiv preprint arXiv:2409.02038},
  year={2024}
}
```

### Datasets
Queries and databases are collected from two sources: `DW` and `NW`.
- `dev_xx.json` includes
  - natural language question, gold SQL statement
  - tables and join keys used in the gold SQL statement
  - column mappings from topics mentioned in the user question to columns used in the gold SQL statement.
  - SQLs in `dev_dw.json` include both MySQL and Oracle versions, making them useful for benchmarking tasks like dialect translation.
- `dev_tables.json` includes the table schema, and key-foreign-key relationships.
  - join keys for tables in database `dw` can be found in `dw_join_keys.json`.
- [Google drive folder](https://drive.google.com/drive/folders/19bRoRxgWQLcJN3LTxwgev0xTahunjPIR?usp=drive_link) contains the anonymized database content, provided in both CSV format and as a MySQL dump..
  - `NW` folder includes data for each non-`DW` database.

### Setup
We have created a unified MySQL version for our dataset. A free MySQL installation can be found [here](https://dev.mysql.com/downloads/mysql/). After the installation, import the MySQL dump files from the google drive to your local MySQL databases using

```
mysql -u root -p < `xxx.sql`
```

To execute a SQL statement, you can either log in to the MySQL interface or you can do it via [mysql-connector-python](https://pypi.org/project/mysql-connector-python/).

If you want to use the Oracle version of `DW` queries, you can download the free oracle database and import the CSVs.

### Contact
Your support in improving this dataset is greatly appreciated! If you have any questions or feedback, please send an email to peterbc@mit.edu or create an Issue.