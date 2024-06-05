# dbt-postgres-python: do more with dbt

dbt-postgres-python is the easiest way to run Python with your [dbt](https://www.getdbt.com/) project.

# Introduction - 📖 [README](./projects/adapter)

dbt-postgres-python is only supporting the adapter originally developed by
[dbt-fal](https://github.com/fal-ai/dbt-fal) going forward (i.e. CLI will be dropped) and only for Postgres.

## Python Adapter

With the Python adapter, you can:

- Enable a developer-friendly Python environment for Postgres.
- Use Python libraries such as [`sklearn`](https://scikit-learn.org/) or [`prophet`](https://facebook.github.io/prophet/) to build more complex `dbt` models including ML models.

# Why are continuing to maintain this?

My work team has been using `dbt-fal` and have found it very useful. The [FAL](https://github.com/fal-ai) team in
April, 2024 chose to stop maintaining `dbt-fal` -- thank you very much for starting this effort. I've decided to pick it
up to try to keep it current with DBT itself, but only for the functionality my team needs.
