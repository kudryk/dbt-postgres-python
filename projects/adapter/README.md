# Welcome to dbt-postgres-python 👋 do more with dbt

dbt-postgres-python adapter is the ✨easiest✨ way to run your [dbt Python models](https://docs.getdbt.com/docs/building-a-dbt-project/building-models/python-models).

Starting with dbt v1.3, you can now build your dbt models in Python. This leads to some cool use cases that was once difficult to build with SQL alone. Some examples are:

- Using Python stats libraries to calculate stats
- Building forecasts
- Building other predictive models such as classification and clustering

This is fantastic! BUT, there is still one issue though! There is no Python support for Postgres.

dbt-postgres-python provides the best environment to run your Python models that works with Postgres! With dbt-postgres-python, you can:

- Build and test your models locally
- Isolate each model to run in its own environment with its own dependencies

**NB**: This project is based off the archived [dbt-fal](https://github.com/fal-ai/dbt-fal) project, which initially supported other platforms. This project
will only support the postgres adaptor. Support for the FAL CLI is dropped as well.

## Getting Started

### 1. Install dbt-postgres-python
`pip install dbt-postgres-python`

### 2. Update your `profiles.yml` and add the fal adapter

```yaml
jaffle_shop:
  target: dev_with_fal
  outputs:
    dev_with_fal:
      type: fal  # "fal" type is kept for backwards compatibility
      db_profile: dev_postgres # This points to your main adapter
    dev_postgres:
      type: postgres
      ...
```

Don't forget to point to your main adapter with the `db_profile` attribute. This is how the fal adapter knows how to connect to your data warehouse.

### 3. `dbt run`!
That is it! It is really that simple 😊
